---
date: 2014-05-29 22:46:00+05:00
layout: post
permalink: media-queries-in-sass
title: Tasty media queries in Sass
---

Writing and maintaining media queries has become a snap since version 3.2 of Sass. This was the release that debuted `@content`, which lets us pass custom styles to mixin inclusions.

This made writing media queries much easier because we could define mixins for smaller-than-n and larger-than-n. These mixins act as filters that let us easily add width, height or resolution specific styles to definitions. The mixin accepts any styles defined within the content of the `@include` and adds them into a media query based on the value specified in the argument. For example, with the following mixins:

```scss
@mixin smaller-than($width) {
  @media (max-width: $width) {
    @content;
  }
}

@mixin larger-than($width) {
  @media (min-width: $width) {
    @content;
  }
}
```

We could write

```scss
.heading {
  font-size: 2em;
  @include smaller-than(300px) {
    font-size: 1.5em;
  }
  @include larger-than(768px) {
    font-size: 3em;
  }
}
```

Which outputs this CSS

```css
.heading {
  font-size: 2em;
}
@media (max-width: 300px) {
  .heading {
    font-size: 1.5em;
  }
}
@media (min-width: 768px) {
  .heading {
    font-size: 3em;
  }
}
```

We could take this one step further and use variables for each device breakpoint, making our code more DRY-friendly.

```scss
$mobile-width: 300px;
$tablet-width: 768px;

@mixin smaller-than($device) {
  @if $device == mobile {
    @media (max-width: $mobile-width) {
      @content;
    }
  }
  @else if $device == tablet {
    @media (max-width: $tablet-width) {
      @content;
    } 
  }

  // ... Etc for each device
}
```

(You can read more about this technique on the <a href="http://thesassway.com/intermediate/responsive-web-design-in-sass-using-media-queries-in-sass-32" target="_blank">Sass blog</a>)

The problem is, until now we’ve had to define our `smaller-than` and `larger-than` mixins with a set of if/else if statements to transform our device argument into a value that Sass can use to create a media query. This quickly gets unwieldy, as each new breakpoint means updating both our mixins with a new statement.

The good news is Sass 3.3 includes full support for maps (aka hashes or data objects), which makes writing media queries even easier. Now we can declare all our breakpoints in one variable:

```scss
$mqs: (
  mobile_portrait: 300px,
  mobile_landscape: 500px,
  tablet_portrait: 768px,
  tablet_landscape: 1024px,
  desktop: 1280px
);
```

And use the new `map-get` function to access the values. That lets us whittle our mixins down to

```scss
@mixin smaller-than($device) {

  $width: map-get($mqs, $device);
  @media (max-width: $width) {
    @content;
  }
}

@mixin larger-than($device) {

  $width: map-get($mqs, $device);
  @media (min-width: $width) {
    @content;
  }
}
```

We can even write a ‘between’ mixin

```scss
@mixin between($smallest, $largest) {

  $min-width: map-get($mqs, $smallest);
  $max-width: map-get($mqs, $largest);
  @media (min-width: $min-width) and (max-width: $max-width) {
    @content;
  }
}
```

Which makes our media queries highly readable

```scss
.heading {
  font-size: 2em;
  @include between(mobile_portrait, mobile_landscape) {
    font-size: 1.5em;
  }
}
```

By separating values and mixins using the above technique you can easily add, remove and edit breakpoints in one place. Your code becomes more readable and more maintainable as a result, and you go home with some serious internet points.
