---
id: box-model
title: Box Model
sidebar_position: 3
description: Box Model
---

# Box Model

All elements can be considered to be a box. The [Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model)
is a specification for how all the various attributes of an element's sizing
relate to each other. A "box" is made up of four distinct parts:

- margin - area (whitespace) between this element and other surrounding elements
- border - a line (or lines) surrounding this element
- padding - area (whitespace) between the border and the inner content of the element
- content - the actual content of the element (e.g., text)

The easiest way to visual this is using your browser's dev tools, which have
[tools for viewing and altering](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_and_edit_the_box_model) each of these parts.

![Box Model View in Firefox Dev Tools](https://firefox-source-docs.mozilla.org/_images/box-model.png)

## CSS "Box" Properties

The sizes (and style) of each of these can be controlled through CSS properties:

- [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) / ([`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top), [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right), [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) and [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left))

- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

  - [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) / ([`border-top-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-style), [`border-right-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-style), [`border-bottom-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style) and [`border-left-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-style))

  - [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) / [`border-top-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width), [`border-right-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width), [`border-bottom-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width) and [`border-left-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width)

  - [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color) / [`border-top-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color), [`border-right-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-color), [`border-bottom-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color) and [`border-left-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color)

- [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) / [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top), [`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right), [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom) and [`padding-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left)

Each of these is a [shorthand property](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties) that lets you
specify multiple CSS properties at the same time. For example, the following
are equivalent:

```css
/* Use separate properties for all aspects */
.example1 {
  border-width: 1px;
  border-style: solid;
  border-color: #000;

  margin-top: 5px;
  margin-right: 10px;
  margin-bottom: 15px;
  margin-left: 20px;
}

/* Use shorthand properties to do everything at once */
.example2 {
  border: 1px solid #000;
  margin: 5px 10px 15px 20px;
}
```

In the code above for `margin`, notice how the the different portions of the
`margin` get translated into a single line. The order we use follows the same
order as a clockface, the numbers begin at the `top` and go _clockwise_ around:

```css
.example2 {
  /*      top right bottom left */
  margin: 5px 10px 15px 20px;
}
```

We often shorten our lists when multiple properties share the same values:

```css
.example3 {
  /* Everything is different, specify them all */
  margin: 10px 5px 15px 20px;
}

.example4 {
  /* Top and bottom are both 10px, right and left are both 5px */
  margin: 10px 5px;
}

.example5 {
  /* Top, bottom, left, and right are all 5px */
  margin: 5px;
}
```

When two elements that specify a `margin` at the top and bottom are stacked, the
browser will _collapse_ (i.e., combine) the two into a single margin, whose size is
the largest of the two. Consider the following CSS:

```html
<style>
  h1 {
    margin-bottom: 25px;
  }

  p {
    margin-top: 20px;
  }
</style>
<h1>Heading</h1>
<p>Paragraph</p>
```

Here the stylesheet calls for a `<p>` element to have `20px` of whitespace above it.
However, since the `<h1>` has `25px` of whitespace below it, when the two are placed
one after the other, the distance between them will be `25px` vs. `45px`
(i.e., the browser won't apply both margins, but just make sure that both margins are
honoured).

## "Displaying" an Element

CSS lets us control how an element gets displayed. This is a large
topic, and we'll give an overview of some of the most common display types. Further
study is required to fully appreciate the subtleties of each layout method.

Perhaps the easiest way to get started understanding display types is to look at
what `display: none;` does:

```html
<style>
  .hidden {
    display: none;
  }

  .error-msg {
    /* styles for error message UI */
  }
</style>

<div class="hidden error-msg">
  <h1>Error!</h1>
  <p>There was an error completing your request.</p>
</div>
```

When an element uses a display type of `none`, nothing will be painted to the screen.
This includes the element itself, but also any of its children.

If elements don't have a display type of `none`, they get included in the render
tree and eventually painted to the screen. If we don't specify a display type, the default is `inline` for inline elements (like `<a>` and `<span>`) and `block` for block-level elements (like `<p>` and `<div>`).

With `inline`, boxes are laid out horizontally (typically left to right, unless
we are doing [rtl](https://developer.mozilla.org/en-US/docs/Web/CSS/direction)), starting
at the top corner of the parent.

We can also specify that an element should be `display: block;`, which will layout
blocks in a vertical way, using `margin` to determine the space between them. To
understand the difference, try this using this snippet of code an HTML page, and
change the `display` from `block` to `inline`:

```html
<style>
  h1 {
    display: block; /* try changing to `inline` */
  }
</style>
<h1>One</h1>
<h1>Two</h1>
<h1>Three3</h1>
```

We can also control the way that elements are laid out _within_ an element (i.e.,
its children). Some of the display types for inside layout options include:

- [`table`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Table) - make elements behave as though they were part of a `<table>`
- [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Display#display_flex) - lays out the contents according to the [flexbox model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [`grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Display#display_grid) - lays out the contents according to the [grid model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)

A great way to learn a bit about the latter two is to work through the following
online CSS learning games:

- [Flexbox Froggy](https://flexboxfroggy.com/)
- [Flexbox Defense](http://www.flexboxdefense.com/)
- [Grid Garden](http://cssgridgarden.com/)

## "Positioning" an Element

Many web interface designs require more sophisticated element positioning than
simply allowing everything to flow. Sometimes we need very precise control
over where things end up, and how the page reacts to scrolling or movement.

To accomplish this kind of [positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning) we can
use the CSS [`position` property](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
to override the defaults provided by the browser.

- [`static`](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#Static_positioning) - the default, where elements are positioned according to the normal flow of the document

- [`relative`](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#Relative_positioning) - elements are positioned according to the normal flow, but with extra offsets (`top, bottom, left, right`), allowing content to overlap

- [`absolute`](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#Absolute_positioning) - elements are positioned separate from normal flow, in their own "layer" relative to their ancestor element, and don't affect other elements. Useful for things like popups, dialog boxes, etc.

- [`fixed`](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#Fixed_positioning) - elements are positioned separate from normal flow, and get positioned relative to the viewport.

- [`sticky`](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#position_sticky) - a hybrid of `relative` and `fixed`, allowing an element to be positioned relatively, but then "stick" when scrolling or resizing the viewport. This is often used for headings, which can be scrolled up, but then stay in place as you continue down into the document.

### `z-index` Property

In addition to controlling how elements are positioned in the X and Y planes,
we can also _stack_ elements on top of each other in different layers. We achieve
this through the use of the [`z-index` property](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index).

The `z-index` is a value positive or negative integer, indicting which stack
level the element should be placed within. The default stack level is `0`, so
using a `z-index` higher than `0` will place the content on top of anything below it.

The `z-index` is often used with `position` to place content in arbitrary positions
overtop of other content. For example, a [modal window](https://getbootstrap.com/docs/5.3/components/modal/#live-demo) that appears as a dialog box, over the site's content.

### `overflow` Property

When the contents on an element are too large to be displayed, we have options
as to how the browser will display the overflowing content. To do this, we
work with the [`overflow`, `overflow-x`, `overflow-y`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) properties

- `visible` - default. No scroll bars provided, content is not clipped.
- `scroll` - always include scroll bars, content is clipped and and scroll if required
- `auto` - only include scroll bars when necessary, content is clipped and and scroll if required
- `hidden` - content is clipped, no scroll bars provided.

## Validating CSS

If you recall from last week, we introduced an online validator to check your HTML code for errors. There are similar tools for CSS, for example:

- [https://jigsaw.w3.org/css-validator/](https://jigsaw.w3.org/css-validator/)

The above allows you to enter a URL to an existing web page, or enter CSS directly in a text field. It
will then attempt to parse your CSS and report back on any errors or warnings.
