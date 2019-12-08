---
date: 2014-03-09 18:22:56+05:00
layout: post
permalink: easy-icomoon-icons-with-sass
title: Easy Icomoon icons with Sass
---

Using icons on the web has become exactly 9000% better since the arrival of <a href="http://icomoon.io/" target="_blank">Icomoon</a>, a web app that lets you easily create icon fonts from vector files.

Trouble is, implementing the icons that Icomoon gives you is still a bit of a pain. It requires adding the `.icon` and `.icon-fontname` classes to your elements, which is non-semantic and not DRY-friendly. Modification of the icon requires more CSS that targets specifically the `:before` pseudo-element, which means a load of rules that aren’t bound explicitly to the icon itself. Furthermore, if you want to display the icon `:after` the element content, or replace the content entirely, you have a lot more hassle on your hands.

Wouldn’t it be nice if you could just include icons, positioned exactly how you want them, in your existing CSS classes with one line?

Using this Sass mixin, you can:

```scss
@mixin icomoon($icon, $position: "before", $replace: false) {
  // If we're replacing the text, set font-size to 0
  @if $replace {
    font-size: 0;
  }
  // Pseudo-element properties
  &:#{$position} {
    @extend .icon-#{$icon};
    font-family: 'icomoon';
    speak: none;
    font-style: normal;
    font-weight: normal;
    font-variant: normal;
    text-transform: none;
    line-height: 1;
    @if $replace {
      font-size: 1rem;
    }
    @content;
  }
}
```

The mixin assumes two things:

* You have already declared the ‘icomoon’ font-family using `@font-face` (grab this from Icomoon’s style.css).
* You have classes assigned to each unicode character in your font file (this is more or less what Icomoon gives you in style.css, minus the `:before`), like this:
```scss
.icon-search {
  content: "\e602";
}
.icon-fb {
  content: "\e605";
}
.icon-email {
  content: "\e606";
}
// ...
```

## Usage

To use the mixin, just call:

```scss
@include icomoon("myIcon");
```

The first argument, `$icon`, accepts the icon name, minus the "icon-" prefix used to define the class.

For the second argument, `$position`, you can provide “before” or “after”, depending on where you want the icon to be placed relative to the contents of the element. 

The `$replace` argument is a bool that sets the font-size of the element's immediate contents to 0 when true. Note that while the mixin will attempt to restore the font-size of the icon to `1rem`, you should pass in a pixel-based font size value to the content block to reliably set the size of the icon.

```scss
// Visually replace the contents of the element with the search icon
@include icomoon("search", "before", true) {
  font-size: 20px;
}
```

Replacing text in this way is a good idea because it means the text is still there as a fallback for screen-readers or in case your stylesheet fails to load.

Hopefully this will make managing your icons a little easier.
