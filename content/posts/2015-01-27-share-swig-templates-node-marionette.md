---
date: 2015-01-27 22:46:00+05:00
layout: post
permalink: share-swig-templates-node-marionette
title: Sharing Swig templates between Node and Marionette.js
---
If you’ve got a few Backbone/Marionette or Ember projects under your belt you’ll know that it’s often necessary to render HTML server-side that might later become dynamic. This is so that the user sees some kind of content before the Javascript loads (or if they have it turned off) and search engines see some content when they crawl your site.

This can mean having to maintain two sets of templates - one for the back-end and one for the front-end. This is not ideal because those two sets of templates can easily diverge, causing a mismatch between what appears on page load and what appears when your front-end application kicks in. You may even have two different template languages, which is a headache for all involved.

Fortunately, it’s not too hard to set up a workflow that lets us share a single set of templates between server and browser. I’ll be showing you how to do this for Marionette with Swig templates, but most of it applies to other front-end frameworks and template languages, as long as they are supported by the server and the browser. A lot of the legwork will be done by Grunt, and assumes you already have a working knowledge of Grunt and a Gruntfile set up. If you aren’t familiar with Grunt, read up on it [here](http://gruntjs.com/).

## Copying template files

Using Grunt, we’re going to define which templates we want to share with the Marionette application.

Because you probably don’t want all your template files to get loaded into the browser, we’ll copy the ones we want into a temp folder using `grunt-contrib-copy`

Install this with npm using `npm install grunt-contrib-copy`

In your Gruntfile, add a new config:

```javascript
grunt.config.set('copy', {
  templates: {
    files: [{
      src: [
        'app/views/comment/inline.html'
      ],
      expand: true,
      flatten: true,
      dest: '.tmp/templates/comment'
    }, {
      src: [
        'app/views/post/new.html',
        'app/views/post/show.html'
      ],
      expand: true,
      flatten: true,
      dest: '.tmp/templates/post'
    }
  }
});
grunt.loadNpmTasks('grunt-contrib-copy');
```

Notice that we’re writing two copy actions here to keep templates for different entities in separate directories. This will come in handy. Write one block for each directory of views in `app/views` that you wish to share with Marionette (or wherever your application's views are kept).

## Precompiling templates for the browser

Using jsttojs, we can precompile the templates to strings inside single Javascript object. This lets us easily access the templates we want in the browser.

First install the jsttojs Grunt plugin with `npm install grunt-jsttojs`.

Then declare the following configuration in your Gruntfile.

```javascript
grunt.config.set('jsttojs', {
  root: '.tmp/templates',
  output: 'assets/js/prod/templates.js',
  ext: 'html',
  removebreak: true,
  requirements: ['swig'],
  name: 'MyApp.templates'
});

grunt.loadNpmTasks('grunt-jsttojs');
```

This will save all the templates to a global Javsacript object within our app namespace called `MyApp.templates`, though you can declare anything here, eg. `window.templates`.

Each template will be named as `$directory/$file` in a way that mirrors our original app/views directory, so for example `app/views/comment/inline.html` becomes `comment/inline`.

## Set up a watch task

We will now set up a watch task to update our template object every time we edit the original template files, ensuring they stay in sync with the back-end.

Install grunt-contrib-watch with `npm install grunt-contrib-watch`, then add the following config.

```javascript
grunt.config.set('watch', {
  templates: {
   files: ['app/views/**/*.html'],
   tasks: ['copy:templates', 'jsttojs']
  },
});
grunt.loadNpmTasks('grunt-contrib-watch');
```

Now run `grunt copy:templates && grunt jsttojs && grunt watch` to copy, compile and watch the templates.

## Modifying the rendering engine

By default, the Marionette renderer is configured to render Underscore templates. We will need to override it to render Swig instead.

Download marionette-swig with `bower install marionette-swig`, and include it in your vendors file (`bower_components/marionette-swig/src/backbone.marionette.swig.js`).

## Modifying the template cache

Finally, we need to tell Marionette to look in our templates object (`MyApp.templates`) for the templates we declare in our views. To do this we will override the template cache built into Marionette.

```javascript
Backbone.Marionette.TemplateCache.prototype.loadTemplate= function(templateId){

  var template, charZero;

  charZero = templateId.charAt(0);
 
  if(charZero == '#' || charZero == '|'){
   
    // If we request the template by providing a jQuery selector, behave as usual
    template = Backbone.Marionette.$(templateId).html();
  }
  else{

    template = MyApp.templates[templateId];
  }

  if (!template || template.length === 0){
   
    errorMessage = 'Could not find template: \'' + templateId + '\'';
    console.error(errorMessage, 'NoTemplateError');
  }

  return template;
};
```

## Declaring templates in views

Now we can simply declare our templates within our views by matching their path within `app/views`. Eg

```javascript
MyApp.InlineComment = Marionette.ItemView.extend({
 template: 'comment/inline',
 // ...
});
```

And there you have it. Just add new templates to your Gruntfile's copy config, and ensure they get copied and precompiled before you use them in the browser.
