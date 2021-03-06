# Sass

> By writing modular code with a component approach, I do not feel the need for Sass's map and loop feature - cssnext

**Warning**: Avoid Sass nesting. Nesting with preprocessor is a false economy. It makes selectors more specific and creates location dependency and more work for the browser.

Use Sass only for its variable, mixin and imports. Avoid nesting and extend.

* [Sass doesn't create bad code. Bad coders do.](http://thesassway.com/editorial/sass-doesnt-create-bad-code-bad-coders-do)
* [The problem with CSS pre-processors](http://blog.millermedeiros.com/the-problem-with-css-pre-processors)
* [Beware the SASS import](http://blog.teamtreehouse.com/tale-front-end-sanity-beware-sass-import)
* [**SCUT: Sass utilities for the front-end**](https://davidtheclark.github.io/scut/)
* [**Sass Guideline - READ THIS FIRST!**](http://sass-guidelin.es/)
* [**A vision for Sass**](http://alistapart.com/article/a-vision-for-our-sass)
* [**An auto-enforceable SCSS styleguide**](http://davidtheclark.com/scss-lint-styleguide/)
* [Scalable CSS reading list](https://github.com/davidtheclark/scalable-css-reading-list)
* [**15 essential SASS mixins**](http://www.developerdrive.com/2014/11/15-essential-sass-mixins/)
* [When to use extend and when to use a mixin](http://csswizardry.com/2014/11/when-to-use-extend-when-to-use-a-mixin/)
* [**Useful SASS mixins**](https://github.com/gillesbertaux/andy)
* [SassDoc](https://github.com/SassDoc/sassdoc)
* [Are we getting too sassy](http://ashleynolan.co.uk/blog/are-we-getting-too-sassy)
* [Utility CSS](https://github.com/seegno/ucss)
* [**Tips**](http://csspre.com/)
* [Understanding SASS lists](http://hugogiraudel.com/2013/07/15/understanding-sass-lists/)
* [A SASS type toolkit](http://ianrose.me/typesettings/)
* [Error handling in SASS](http://webdesign.tutsplus.com/tutorials/an-introduction-to-error-handling-in-sass--cms-19996)
* [Removing duplication using SASS maps](http://robots.thoughtbot.com/removing-sass-duplication)
* [Quite some tips on Sass](http://www.alwaystwisted.com/)
* [Out CSS/Sass Project Architecture and Styleguide](http://blog.groupbuddies.com/posts/32-our-css-sass-project-architecture-and-styleguide)
* [DRY Sass mixins](http://alistapart.com/article/dry-ing-out-your-sass-mixins)
* [Bourbon 4](https://news.layervault.com/stories/21801-bourbon-4-differences)
* [Sass and partials](http://zurb.com/university/library/35)
* [Organizing z-index](http://jonsuh.com/blog/organizing-z-index-with-sass/)
* [Inverse trigonometric function with Sass](http://thesassway.com/advanced/inverse-trigonometric-functions-with-sass)
* [List-maps](https://www.codefellows.org/blog/so-you-want-to-play-with-list-maps)
* [Mini Sass mixins](http://codepen.io/chriscoyier/blog/some-mini-sass-mixins-i-like)
* [A Sass component in 10 minutes](http://www.sitepoint.com/sass-component-10-minutes/)
* [Handy Sass mixins](http://web-design-weekly.com/2013/05/12/handy-sass-mixins/)
* [Ampersand](http://www.joeloliveira.com/2011/06/28/the-ampersand-a-killer-sass-feature/)
* [Sass tooltips](http://hackingui.com/front-end/scss-tooltips/)
* [Increasing SASS compiling performance](https://www.devbridge.com/articles/increasing-sass-compiling-performance-or-when-every-second-counts/)
* [Useful Sass mixins](http://hmphry.com/useful-sass-mixins)

## Folders

```
/base
  - reset
  - normalize
  - element
/layout
  - grid
  - navigation
  - drawer
  - sidebar
  - inspector
  - header
  - footer
/modules or /components
  - buttons
  - loader
  - widgets
  - slider
  - media
  - carousel
/utils
  - variables
  - helpers
  - functions
  - mixins
/pages
/vendors
/vendors-extension
```

You can also split variables into `base/_typography.scss`, `base/_colors.scss`

## Color

* [Name that color](http://chir.ag/projects/name-that-color/#CA4ED4)
* [Sass color variables that don't suck](http://davidwalsh.name/sass-color-variables-dont-suck)
* [How to programmatically go from one color to another](http://thesassway.com/advanced/how-to-programtically-go-from-one-color-to-another-in-sass)
* [Using Sass maps to manage color schemes](http://now.violet.is/color-scheming)
* [Google Material Design colors???](https://github.com/nickpfisterer/quantum-colors)
* [It's fine, carry on defining blacks](https://medium.com/@corinrules/sass-it-s-fine-carry-on-defining-blacks-67e0d0ced433)

## Placeholder

* [Mixin or Placeholder](http://www.sitepoint.com/sass-mixin-placeholder/)
* [Cross-media query @extend directives in Sass](http://www.sitepoint.com/cross-media-query-extend-sass/)

```
@mixin center { display: block; margin-left: auto; margin-right: auto; }

.container { @include center; }
.image-cover { @include center; }

// Using mixin will result in duplicate styles! We should use placeholder instead
.container {
	display: block; margin-left: auto; margin-right: auto;}

.image-cover {
	display: block; margin-left: auto; margin-right: auto;}
```

A good example of using `@extend` together with `%placeholder` is when we have a base style but can't find a reasonable functional name for it.

```css
%blue-box {
  background: #bac3d6;
  border: 1px solid #3f2adf;
}

.contact-box {
  @extend %blue-box;
  ...
}
.references-box {
  @extend %blue-box;
  ...
}

/* => Output */
.contact-box,
.references-box {
  background: #bac3d6;
  border: 1px solid #3f2adf;
}
```

This approach cuts references in our HTML to presentational class names, but it still lets us use them in our Sass files in a descriptive way. Trying to devise functional names for common styles can have us reaching for terms like `base-box`, which is far less meaningful here.



## Lists

Sass equivalent of arrays.

* [Understanding Sass Lists](http://hugogiraudel.com/2013/07/15/understanding-sass-lists/)

```
$empty: (); // Braces is not what create lists FYI

nth($list, 1); // Indexes start from 1

$variable: "Sass is awesome"; // A list with length=1
$variable: Sass is awesome; // A list with length=3
```

## Map

* [Play with list-maps](http://anotheruiguy.roughdraft.io/10302472-so-you-want-to-play-with-list-maps)
* [Using lists with maps in Sass 3.3](http://benfrain.com/using-lists-with-maps-in-sass-3-3/)


```
$message-types: (
	error: #b94a48,
	valid: #468847) !default;

@each $type, $color in $message-types {
	.message-#{$type} {
		@include message($color);	}}
```

## Tips

* [5 Sass mixins](http://www.andrewhoule.me/blog/5-sass-mixins-i-use-on-nearly-every-project/)

```css
/* Tire of writing width and height? */
@mixin size($width, $height: $width) {
	width: $width;
	height: $height;}
```

**Trangle**


```css
@mixin triangle($direction, $size: 0.375rem, $color: #222){
  content: '';
  display: block;
  position: absolute;
  height: 0; width: 0;
  @if ($direction == 'up') {
    border-bottom: $size solid $color;
    border-left: $size solid transparent;
    border-right: $size solid transparent;
  }
  @else if ($direction == 'down') {
    border-top: $size solid $color;
    border-left: $size solid transparent;
    border-right: $size solid transparent;
  }
  @else if ($direction == 'left') {
    border-top: $size solid transparent;
    border-bottom: $size solid transparent;
    border-right: $size solid $color;
  }
  @else if ($direction == 'right') {
    border-top: $size solid transparent;
    border-bottom: $size solid transparent;
    border-left: $size solid $color;
  }
}
```

**Variables for various font-weight**

```
$hairline-weight: 100;
$thin-weight:     200;
$light-weight:    300;
$normal-weight:   400;
$medium-weight:   500;
$semibold-weight: 600;
$bold-weight:     700;
$xbold-weight:    800;
$black-weight:    900;
```

**z-index organisation**

```
$z-index: (
  modal:      200,
  navigation: 100,
  triangle:   60
);

@function z-index($key) {
	@return map-get($z-index, $key)}

@mixin z-index($key) {
	z-index: z-index($key);}

.navigation {
	@include z-index(navigation);}
```

```
percentage(target/context)
```

**Interpolation**

```scss
// Remember to use #{}, and not `calc(100% - $sidebar-width)`
.main {
  width: calc(100% - #{$sidebar-width});
}

// But not needed in @media
@media (max-width: $value) {}

// Needed in custom selector
selector-#{$value} {}
```