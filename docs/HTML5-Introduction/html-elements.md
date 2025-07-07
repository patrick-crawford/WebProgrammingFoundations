---
id: html-elements
title: HTML Elements
sidebar_position: 2
description: HTML Elements
---

# HTML Elements

As we have seen from our discussion on basic HTML ["Document Structure"](/HTML5-Introduction/document-structure), HTML consists primarily of "Elements" such as [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head), [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body), [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title), [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements), etc. Elements serve as the foundation of HTML documents, providing structure and meaning to the content. In the following sections, we will delve deeper into a subset of these elements to better understand their roles and uses.

> **NOTE:** While there are [more than 100](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) HTML elements, our current focus is on introducing common, widely used elements to enable you to quickly create a functional, standards-compliant user interface. Elements such as ["form"](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form), etc will be discussed later on in the ["Working with Forms"](/Working-With-Forms/html-form-elements-overview) section.
>
> For a comprehensive list of all HTML elements, see the ["HTML Element Reference"](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) available on [MDN](https://developer.mozilla.org/en-US/).

## Metadata

Information _about_ the document itself (not the document's actual content) goes in various [metadata elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Document_metadata). These types of elements _must_ be included within the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) element:

- [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) - links from this document to external resources, such as CSS stylesheets
- [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) - metadata that can't be included via other elements
- [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) - the document's title

## Element Types (Block vs. Inline)

Before we discuss some of the main visual HTML elements, we must introduce two important distinctions:

1. [Block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements): create a "block" of content in a page, with an empty line before and after them. Block elements expand to fill the width of their parent element. Block elements can contain other block elements, inline elements, or text.

1. [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements): creates "inline" content, which is part of the containing block. Inline elements can contain other inline elements or text.

Consider the following HTML content:

```html
<body>
  <p>The <em>cow</em> jumped over the <strong>moon</strong>.</p>
</body>
```

Here we have a `<p>` paragraph element. Because it is a block-level element, this paragraph will
fill its container (in this case the `<body>` element). It will also have empty space (margins) added above and below it.

Within this block, we also encounter a number of other inline elements. First, we have simple text.
However, we also see the `<em>` and `<strong>` elements being used. These will affect their content, but not
create a new block; rather, they will continue to flow inline in their container (the `<p>` element).

### Content Sections (Block)

The following is a short list of some of the more commonly used "block-level" elements. Again, these are used to provide structure and meaning to the content:

- **[`<h1> - <h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)** - renders six levels of section headings in "bold" text. `<h1>` is the highest section level (rendered by default as the largest header size) and `<h6>` is the lowest (rendered by default as the smallest header size).

- **[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)** - represents a paragraph. Paragraphs are usually represented in visual media as blocks of text separated from adjacent blocks by blank lines and/or first-line indentation, but HTML paragraphs can be any structural grouping of related content, such as images or form fields.

- **[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)** - serves as a "generic" container for content. Unlike the previous block level elements, it does not have any style applied to it (ie: no margins, font size changes, etc).

- **[`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)**, **[`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)**, **[`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)**, **[`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)**, **[`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)**, **[`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)** - these elements are similar to the above `<div>` element, however they describe the purpose of the element and the type of content it contains. These types of elements are known as ["Semantic Elements"](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html). For example, the `<nav>` element specifically indicates a section of a webpage that contains navigation links, guiding browsers and assistive technologies to treat this part differently from other content.

### Text (Inline)

The following are some examples of common "inline" elements. Unlike "block-level" elements, these only occupy as much width on the page as required for their content (ie: they do not expand to fill the width of their parent element):

- **[`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em)** - used to "emphasize" a section of text. By default, this will render the text using an _italic_ font style.

- **[`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)** - this element is also used to emphasize a section of text, however in this case the text will be rendered using a **bold** font style.

- **[`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code)** - if your text contains a fragment of computer code (like the html snippets on this page), a common way to indicate this is with the `<code>` element. By default it will render the text using the client's default [monospace font](https://en.wikipedia.org/wiki/Monospaced_font).

- **[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)** - like the `<div>` element, this serves as a "generic" container for content (it does not have any style applied to it). However, unlike `<div>`, it only occupies as much width as required for the content.

- **[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)** - this element, also known as the anchor element, is used to create hyperlinks, which are clickable links that navigate to other resources. These resources can be webpages, files, email addresses, or any URL. Common attributes include:

  - href: Specifies the URL of the page the link goes to. This can be an absolute URL, a relative URL, or a local link. For local links within the same page, use the "#" symbol followed by the id of the target element. For example, href="#section1" will link to an element with id="section1" on the same page.

  - target: Specifies where to open the linked document. For example, "\_blank" opens the document in a new tab or window.

  - rel: Specifies the relationship between the current document and the linked document. Common values include ["noopener"](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/noopener) and ["noreferrer"](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/noreferrer).

  ```html
  <a href="https://www.google.ca/" target="_blank" rel="noreferrer">Visit Google.ca</a>
  ```

## Void (Empty) Elements

Many of the elements we've seen so far begin with an opening tag, and end with a closing tag: `<body></body>`.
However, not all elements need to be closed. Some elements have no _content_, and therefore don't need
to have a closing tag. We call these [void elements](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).

An example is the [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) line break element.
We use a `<br>` when we want to tell the browser to insert a newline (similar to using `\n` in C):

```html
<p>Knock, Knock<br />Who's there?</p>
```

Other examples of void elements include `<hr>` (for a horizontal line), `<meta>` for including metadata
in the `<head>`, and [a dozen others](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).

## Lists

In HTML, lists are used to organize content in a structured and easily readable format, similar to how lists are used in Microsoft Word. To achieve this, we use the following elements:

- [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) - the top level ("root") element of the list - it is this element that contains the "list items". `<ol>` signifies that this is an "Ordered List" and will render the containing "list items" using numbers.

- [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) - this element functions exactly the same way as the above `<ol>` element, except that it indicates an "Unordered List". This will cause the containing "list items" to render using bullet points by default instead of numbers

We define list items themselves using the following:

- [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) - this is the element that is used within either an "ordered" or "unordered" list to indicate the elements of the list. Each element of the list will be contained within one `<li>` or "list item".

The following is an example of an "unordered" list of items, contained within an "ordered" list (specifically the first item)

```html
<ol>
  <li>
    First Item
    <ul>
      <li>Subitem 1</li>
      <li>Subitem 2</li>
      <li>Subitem 3</li>
    </ul>
  </li>
  <li>Second Item</li>
  <li>Third Item</li>
</ol>
```

## Tables

Sometimes our data is tabular in nature, and we need to present it in a grid. A number of elements are used to create them:

- [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) - the root of a table in HTML

- [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) - the optional title (or caption) of the table

- [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) - row(s) at the top of the table (header row or rows)

- [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) - rows that form the main body of the table (the table's content rows)

- [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) - row(s) at the bottom of the table (footer row or rows)

We define rows and columns of data within the above using the following:

- [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) - a single row in a table

- [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) - a single cell (row/column intersection) that contains table data

- [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) - a header (e.g., a title for a column)

We can use the `rowspan` and `colspan` attributes to extend table elements beyond their usual bounds,
for example: have an element span three columns (`colspan="3"`) or have a heading span 3 rows (`rowspan="3")`.

```html
<table>
  <caption>
    Order Information
  </caption>

  <thead>
    <tr>
      <th></th>
      <th>Quantity</th>
      <th>Colour</th>
      <th>Price (CAD)</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <th rowspan="3">Products</th>
      <td>1</td>
      <td>Red</td>
      <td>$5.60</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Blue</td>
      <td>$3.00</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Blue</td>
      <td>$1.50</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <th colspan="3">Total</th>
      <th>$26.60</th>
    </tr>
  </tfoot>
</table>
```

## Multimedia

HTML5 provides built-in support for incorporating images, videos, and audio directly into pages, enhancing multimedia experiences. The following are examples of how to use three of the most commonly used elements: `<img>`, `<video>`, and `<audio>`.

### Image

To begin, we will discuss the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element - used for embedding images into the content of your page. The attributes available are:

- **src** - this is required, and contains the path to the image you want to embed.

- **alt** - used to specify alternate text for an image - providing alternative information if the image cannot be displayed due to reasons such as slow internet connections, errors in the src attribute, or when the user relies on a screen reader. This attribute is crucial for accessibility, as it allows screen readers to convey the meaning of the image.

```html
<!-- External image URL, use full width of browser window -->
<img
  src="https://images.unsplash.com/photo-1502720433255-614171a1835e?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=344dfca9dc8cb137a4b1c2c711752bc5"
  alt="Toronto Sign (text)"
/>

<!-- Local file cat.jpg, limit to 400 pixels wide -->
<img src="cat.jpg" alt="Picture of a cat" width="400" />
```

HTML5 has also recently added the [`<picture>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)
, to allow for an optimal image type to be chosen from amongst a list of several options.

### Audio

Now that we have covered the `<img>` element, let's move on to another important multimedia element in HTML: the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element. This element is used to embed sound content, such as music or audio clips, into your page.

Here are some of the key attributes available for the `<audio>` element:

- **src** - this attribute specifies the path to the audio file you want to embed. Similar to the `<img>` element, the src attribute is required if you are not using nested `<source>` elements to define multiple audio formats.

- **controls** - by adding this attribute, you enable built-in controls for the audio player, such as play, pause, and volume. This attribute ensures that users can interact with the audio easily.

- **autoplay** - when this attribute is present, the audio will begin playing automatically as soon as it is ready. However, you should use this feature sparingly, as autoplaying audio can be intrusive / unpleasant for users.

- **loop** - this attribute causes the audio to restart from the beginning once it has finished playing, creating a continuous loop.

- **muted** - this attribute mutes the audio - useful if you want the audio to be initially silent.

- **preload** - This attribute provides a hint to the browser about whether the audio file should be preloaded. The possible values are "auto" (default), "metadata" (only preload metadata), and "none" (do not preload the audio).

```html
<!-- Audio with controls showing, only MP3 source provided -->
<audio src="https://samplelib.com/lib/preview/mp3/sample-15s.mp3" controls></audio>

<!-- Audio with controls showing, multiple formats available -->
<audio controls>
  <source src="song.mp3" type="audio/mp3" />
  <source src="song.ogg" type="audio/ogg" />
  <p>
    Sorry, your browser doesn't support HTML5 audio. Here is a
    <a href="song.mp3">link to the audio</a> instead
  </p>
  .
</audio>
```

### Video

Finally, let's discuss the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element. Similar to the `<audio>` element, this element allows us to embed media content directly into our pages, providing an integrated player for video content.

Key attributes of the `<video>` element include:

- **src** - specifies the URL of the video file. Like the `<audio>` element, the src attribute is required if you are not using nested `<source>` elements to define multiple video formats.

- **controls** - when present, this attribute enables the default video controls such as play, pause, and volume.

- **autoplay** - if set, the video will start playing as soon as it is ready, without waiting for user interaction.

- **loop** - makes the video start over again, every time it is finished.

- **muted** - mutes the audio of the video.

- **poster** - specifies an image to be shown while the video is downloading or until the user hits the play button.

- **width** and **height** - define the dimensions of the video player.

```html
<!-- External Video File, MP4 file format, show controls -->
<video
  src="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
  controls
></video>

<!-- Local video file in various formats, show with controls -->
<video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <p>Sorry, your browser doesn't support HTML5 video</p>
</video>
```

> **NOTE:** the `<audio>` and `<video>` elements must use source URLs that point to actual audio or video files
> and not to a YouTube URL or some other source that is actually an HTML page.

## Validating HTML

It's clear that learning to write proper and correct HTML is going to take practice. There are
lots of elements to get used to, and learn to use in conjunction. Also each has various attributes
that have to be taken into account.

Browsers are fairly liberal in what they will accept in the way of HTML. Even if an HTML file isn't
100% perfect, a browser can often still render something. That said, it's best if we do our best
to provide valid HTML.

In order to make sure that your HTML is valid, you can use an HTML Validator. There are a few available online:

- [https://html5.validator.nu/](https://html5.validator.nu/)
- [https://validator.w3.org/](https://validator.w3.org/)

Both allow you to enter a URL to an existing page, or enter HTML directly in a text field. They
will then attempt to parse your HTML and report back on any errors or warnings, for example: an element missing
a closing tag.
