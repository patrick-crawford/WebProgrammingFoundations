---
id: units-properties
title: Units & Properties
sidebar_position: 2
description: Units & Properties
---

# Units & Properties

Many CSS values require units to be specified, for example, font sizes, widths, heights, etc.
At first you might think that we should specify things in pixels; however, browsers need to work
on such a wide variety of hardware and render to so many different displays (watches to billboards),
we need more options. It's also important to be able to specify sizes using relative units vs. fixed,
for layouts that need to adapt to changing conditions and still retain the correct proportions.

There is one exception, and that is for `0` (i.e., zero), which never needs a unit (i.e., `0px` is the
same as `0%`, etc).

## CSS Units

The most common units we use in CSS are:

```
1em = 12pt = 16px = 100%
```

Let's look at each of these in turn:

- `em` (the width of the capital letter `M`) - a scalable unit that is used in web media, and is equal to the current `font-size`. If the `font-size` is `12pt`, `1em` is the same as `12pt`. If the `font-size` is changed, `1em` changes to match. We can also use multiples: `2em` is twice the `font-size`, and `.5em` is half. Using `em` for sizes is popular on the web, since things have to scale on mobile vs. desktop (i.e., fixed unit sizes don't work as the screen shrinks/expands).

- `pt` - a fixed-size _Point_ unit that comes from print media, where `1pt` equals `1/72` of an inch.

- `px` - pixels are fixed size units for web media (screens), and `1px` is equal to one dot on a computer display. We use `px` on the web when we need "pixel perfect" sizing (e.g., image sizes).

- `%` - the percent unit is similar to `em` in that it scales with the size of the display. `100%` is the same as the current `font-size`.

- `vw`, `vh` - the viewport width and height units are percentages of the visible space in the viewport (the part of the page you can see, the window's width and height). `1vw` is the same as `1%` of the width of the viewport, and `80vh` is the same as `80%` of the visible height.

You will also sometimes encounter other ways of measurement that use full words: `xx-small, x-small, small, medium, large, x-large, xx-large, smaller, larger, thin, medium, thick`

Here's an example that uses a number of the units mentioned above:

```html
<style>
  html,
  body {
    height: 100vh;
  }

  .box {
    margin: 10px;
    font-size: 2em;
    height: 150px;
    border: medium solid black;
  }
</style>
<div class="box"></div>
```

## CSS Colours (`color`)

CSS allows us to define colour values for many declarations. We do so by specifying
a colour using one of the following notations:

- Hexadecimal Red, Green, Blue: written using 3 double-digit hex numbers, and starting with a `#` sign. Each of the 3 pairs represents a value between 0 and 255 for Red, Green, and Blue: `#000000` is pure Black and `#ffffff` is pure White, and `#ffd700` is Gold.

- RGB or RGBA notation: here the red, green, blue, and sometimes alpha (i.e., opacity) are defined in decimal notation: `#ffffff` is the same as `rgb(255, 255, 255)` and `#ffd700` is the same as `rgb(255, 215, 0)`. If we want to define how see-through the colour is (by default you can't see through a colour), we add an alpha value: `rgba(0, 191, 0, 0.5)` means that the colour will be 50% see through.

- Named colours: some colours are so common that they have their own [name defined in the CSS standard](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords). For example: `white`, `black`, `green`, `red`, but also `chocolate`, `darkorange`, `peru`, etc.

The easiest way to understand this is using a [Colour Picker tool](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool), which lets you visually see the difference in changing values.

## CSS Properties and Values

A _property_ is assigned to a selector in order to manipulate its style. The [CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) are defined as part of the CSS standard.
When you want to know how one of them works, or which values you can assign, you can look at the documentation
on MDN. For example:

- [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)
- [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
- [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

There are hundreds of properties we can tweak as web developers, and it's a good idea to explore
what's available, and to look at how other web sites use them via the developer tools.

A property can have one or more values. A the possible values a property can have also comes
from the standard. For example:

```css
p {
  text-decoration: underline;
}

.spelling-error {
  text-decoration: red wavy underline;
}
```

The [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property is defined
to take one of a number of values, each of which is also defined in the standard.

## Exploring CSS Properties and Values in the Dev Tools

By far the best way to learn about CSS is to look at how other sites use it. When you find
something on the web that you think looks interesting, open your browser's dev tools and inspect
the CSS Styles:

![Inspect CSS styles](/img/inspect-css.gif)

You can look at the specific properties specified for an element, or see all the _computed_ styles
(i.e., everything, including all default values). You can also try toggling these on and off, or
double-click the values to enter your own.

## CSS `text` Properties

There are [dozens of properties that affect how text is rendered](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals). These include
things like the color, spacing, margins, font characteristics, etc.

```css
h2 {
  color: red;
  text-align: center;
  text-decoration: underline;
  text-transform: uppercase;
}

p {
  color: #0000ff;
  text-indent: 100px;
}
```

### `font` Properties

We can use the `font-family` property to specify a font, or list of fonts, for the
browser to apply to an element. The font must be available on the user's computer,
otherwise the next font in the list will be tried until one is found that is installed,
or a default font will be used.

In general it is safe to assume that the following fonts are available:

- `Helvetica, Arial, Verdana, sans-serif` - sans-serif fonts
- `"Courier New", Courier, monospace` - monospace fonts
- `Georgia, "Times New Roman", Times, serif` - serif fonts

You can see a [list of the fonts, and OS support here](https://www.cssfontstack.com/).

```css
h3 {
  font-family: Arial;
}

h4 {
  font-family: 'Times New Roman', Times, serif;
}

h5 {
  font-size: 18pt;
  font-style: italic;
  font-weight: 500;
}
```

### Web Fonts - `@font-face`

Modern browsers also allow [custom fonts to be included](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts#Web_fonts) as external files, and downloaded
as needed by the web site. This is often the preferred method for designers, who don't
want to be limited to the set of fonts available on _all_ operating systems.

A font is a file that describes the curves and lines needed to generate characters at
different scales. There are various formats, from `OTF` (OpenType Format) to
`TTF` (TrueType Format) to `WOFF` (Web Open Font Format), etc. In order for
the browser to use a new font, it has to be downloadable via one or more URLs.
We then tell the browser which font files to download in our CSS via the
`@font-face` property:

```css
@font-face {
    font-family: "FontName"
    src: url(font.woff2) format('woff2'),
         url(font.ttf) format('truetype');
}

body {
    font-family: "FontName";
}
```

Many fonts have to be purchased, but there are some good sources of high quality,
freely available fonts for your sites:

- [Font Squirrel](https://www.fontsquirrel.com/)
- [dafont.com](https://www.dafont.com/)
- [Google Fonts](https://fonts.google.com/)

For example, we can use the popular [`"Lobster"`](https://fonts.google.com/specimen/Lobster) font
from Google by doing the following in our CSS:

<!-- prettier-ignore-start -->
```css
@import url(https://fonts.googleapis.com/css?family=Lobster); 

p {
  font-family: 'Lobster';
}
```
<!-- prettier-ignore-end -->

### `font-size` property

Using the [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) property, font sizes
can be given in fixed or relative units, depending on how we want our text to scale on different devices:

```css
h1 {
  font-size: 250%; /* scaled to 250% of regular font size */
}

p {
  font-size: 20pt; /* size in points -- 20/72 of an inch */
}

.quote {
  font-size: smaller; /* smaller than normal size */
}

.bigger {
  font-size: 1.5em; /* 1.5 times larger than the 'M' in normal font size */
}
```

### Text Effects

There are numerous effects that can be added to text (or any element), many beyond
the scope of this initial exploration of CSS. Here are a few simple examples to
give you an idea

[`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) allows a
shadow to be added to text, giving it a 3-D style appearance. The value includes a colour,
`x` and `y` offsets that determine the distance of the shadow from the text. Finally, we
can also add a `blur-radius`, indicating how much to blur the shadow.

```css
.shadow-text {
  text-shadow: 1px 1px 2px pink;
}
```

[`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) can be used
to determine what the browser should do when the amount of text exceeds the available space
in a container (e.g. in a `<div>` or `<p>` that isn't wide enough). For example, we can specify
that we want to `clip` the contents and not show any more, or we can automatically display `...`,
the `ellipsis`.

```html
<style>
  .movie-title {
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
</style>
<p class="movie-title">Pirates of the Caribbean: The Curse of the Black Pearl</p>
```

## `background` Properties

Every element has a background that we can modify. We might, for example, want to
specify that the background be a certain colour; or we might want to use an image,
or even tile an image multiple times (like wallpaper to create a pattern); or we
might want to create a gradient, from one colour to another. All of these options
and more are possible using the [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
property.

```css
div.error {
  background: red;
}

div.wallpaper {
  background: url('pattern.jpg') repeat;
}
```

## Styling Links

We can control the way that links (i.e., `<a>`) appear in our document. By default
they will have a solid blue underline, and when visited, a purple solid underline.
If you want to remove the underline, or change it's colour to match the theme of a page,
we can do that using CSS [`pseudo-classes`](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes).

With _pseudo-classes_ we can specify certain states for the elements in our selector,
for example:

- `a:link` - a normal, unvisited link (normally blue underline)
- `a:visited` - a link the user has visited previously (normally purple underline)
- `a:hover` - a link when hovered with the mouse
- `a:active` - a link when it is clicked (i.e., while the mouse button is pressed)

:::info
Pseudo-classes can be used with any element, but we mention them here in relation to styling links, since we often need them to deal with different states for a link.
:::

Let's alter our links so that they use blue text, with no underline. However, when hovered,
add back the underline:

```css
a:link,
a:visited {
  text-decoration: none;
}

a:hover,
a:active {
  text-decoration: underline;
}
```
