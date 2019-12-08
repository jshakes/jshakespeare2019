---
author: jshakes
comments: true
date: 2013-03-19 07:09:40+00:00
layout: post
permalink: the-dire-state-of-wordpress
title: The dire state of Wordpress
wordpress_id: 1007
---

Wordpress powers a massive tranche of the world's websites - [17.4% of them](http://en.wordpress.com/stats/) in fact, at the time of writing. Over the years its huge community and ease-of-use as a CMS has won it favour with web developers looking for out-of-the-box solutions to homogeneous client briefs. The admin is friendly and clients tend to get to grips with it quickly, making it a good choice for agency environments where the customer may not be savvy enough to wrap their heads around a bespoke but hokey UI.

Its weakness lies in how it has evolved, or rather mutated, from a blogging platform to pseudo-framework in a highly inelegant way. Functionality has been added along the road to accommodate WP's growing use as a CMS: custom post types, custom menus etc - but really these are just hacks to a platform that fundamentally still behaves like blogging software.

When you learn PHP from Wordpress as I (and probably many other people) did, you just assume that all the idiosyncrasies and illogicalities are par for the course when building a CMS-driven site. It's taken me several years to realise that it doesn't have to be like this. In fact, it wasn't really until I started learning more about OO principles and working with frameworks that I started looking at WP in a different light. Why _is_ every instance of every model treated like a post? Why can't I extend the functionality of a post type without writing a whole mess of hooks, filters and functional code into a file that isn't semantically related to that post in any way?

These may sound like the gripes of someone whose needs will never be met by something like Wordpress, but the lack of fundamental logic that gives rise to the above issues is what makes Wordpress problematic for developers at all levels. And because the crossover on the venn diagram of 'people who know good application development practises' and 'people who build sites in Wordpress' is such a thin sliver, it just trundles along in its current hokey state, baffling both the unseasoned and the proficient developer alike.

Before leaving my last job I had to hand over several codebases to PHP developers who work mainly in Symfony. If I'd had a penny for every raised eyebrow when I was talking them through it I could have retired there and then. I'd also just spent a few weeks with a junior employee getting him up and running with WP sites. Trying to describe how code works on a platform that has the kind of fundamental logic that Wordpress does is like trying to teach a language that doesn't have an alphabet. I would discourage anyone from learning it until they’re more au fait with a platform that operates on better principles. Basically, Wordpress isn't a platform suited to anyone except those unlucky enough to have somehow become Wordpress developers.

If you think I'm exaggerating or being deliberately hyperbolic to prove a point, take a look at [Twenty Twelve](https://github.com/WordPress/WordPress/tree/master/wp-content/themes/twentytwelve ), currently the default theme for WP and developed by Automattic. (Why is it in a directory called 'wp-content' when it's actually a bunch of views? Who knows). Click through to [functions.php](https://github.com/WordPress/WordPress/blob/master/wp-content/themes/twentytwelve/functions.php) - one file to manage ALL the extraneous functionality specified by the theme. This file contains functions for customising registration page layouts, comment handling, printing post meta and so on. HTML snippets sit fragmented between ifs and elses, loops and comment blocks that make Tolstoy look like Dr Seuss. It’s just an ugly, unreadable, unscalable mess of spaghetti code.

I'm not going to list all the things that make WP at odds with best practises, but here are the brass tacks:

	
  * Views, controllers and data are mangled together in a way that makes even the most well-written themes hard to maintain.

	
  * Helper functions are [inconsistent](http://lorib.me/code/dont-get-the-permalink/ )

	
  * There are no rules or best practices for theme development, so inheriting legacy code is a nightmare.

	
  * Designers and front-end developers struggle to make changes because their files are full of functional code

	
  * PHP developers struggle to make changes because their files are full of template code

	
  * It's not optimised for speed of development or speed of operation.

	
  * There are about fifty ways to perform any given operation in Wordpress, but determining which way is best pretty much depends who you talk to. Even the [documentation](http://codex.wordpress.org/Function_Reference/query_posts) is chock full of caveats about obscure scenarios in which you should and shouldn’t use certain functions




## Why is all this a problem?


Wordpress' growth isn't going to stop. For agencies and designers it's becoming a de facto platform for cookie-cutter websites with a development time of roughly 10-100 hours. This isn't necessarily a problem if you're a competent developer and know the ins and outs of WP, but undoubtedly anyone working in this field will inherit legacy WP code from time to time. And because Wordpress doesn't insist on any kind of template structure beyond a basic naming convention, codebase inheritance requires an unsustainable investment of time to figure just what the hell is going on. Even a fairly tidy theme probably won’t look remotely like any of yours.


## Why not just use something else?


Because Wordpress is still far and away the best off-the-shelf platform for small to medium size websites. It has arguably the best UI, a ton of features that come for free, a huge community of developers and all of the benefits that come with being a hugely popular piece of software. These things are much harder to come by than a decent codebase.


## What should be done?


Wordpress needs more rules. People treat it like a framework and largely it is, but it lacks the scalability and rules that make frameworks worth using. Instead of forcing front-end developers and back-end developers to share the same resources there needs to be some separation of design and functionality. Having more rules would make inheriting code and working in a team easier. It would mean developers with framework-agnostic coding principles would be able to quickly get up and running within Wordpress sites without having to learn a backwards and entirely domain-specific vernacular.


## Wordpress is OSS, why don't you shut up and do it yourself?


The kind of rewrite I'm talking about would require a fundamental rethink of the entire platform. We're talking thousands of man-hours for no direct financial reward. If Automattic were to do this it would require a shakeup of their business model, given they don't make any money directly from the Wordpress codebase.

But this doesn't mean it couldn't or shouldn't be attempted. If Wordpress is going to continue to power the world's highest traffic websites then it's in the interest of a vast number of developers to refactor it into a logical, scaleable, easily inheritable platform. As I see it, the solution would be to migrate the functional aspects of Wordpress to a PHP MVC framework, much like Drupal has recently done by incorporating Symfony 2. However, one cannot simply be melded into the other, and a lot of cherry picking would be required to avoid bloat.

So consider this post to be the start of a [discussion](https://news.ycombinator.com/item?id=5407879) about how this can happen. I ain't quittin' you yet, Wordpress.
