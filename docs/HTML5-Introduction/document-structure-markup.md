---
id: document-structure
title: Document Structure
sidebar_position: 1
description: Document Structure
---

# Document Structure

HTML is the [HyperText Markup Language](https://en.wikipedia.org/wiki/HTML). It allows us to write _content_ in a document, just as we would in a file created by a word processor. Unlike a regular text file, it also includes structural and layout information about this content. We literally _mark up_ the text of our document with extra information.

## Terminology

When talking about HTML's markup, we'll often refer to the following terms:

- content: any text content you want to include can usually be written as-is.

- [tag](https://developer.mozilla.org/en-US/docs/Glossary/Tag): separated from regular content, tags are special text (names) wrapped in `<` and `>` characters, for example the paragraph tab `<p>` or the image tag `<img>`.

- [element](https://developer.mozilla.org/en-US/docs/Glossary/Element): everything from the beginning of an opening tag to the closing tag, for example: `<h1>Chapter 1</h1>`. Here an element is made up of an `<h1>` tag (i.e., opening Heading 1 tag), the text content `Chapter 1`, and a closing `</h1>` tag. These three components taken together create an `h1` element in the document.

- [attribute](https://developer.mozilla.org/en-US/docs/Glossary/Attribute): optional characteristics of an element defined using the style `name` or `name="value"`, for example `<p id="error-message" hidden>There was an error downloading the file</p>`. Here two attributes are included with the `p` element: an `id` with value `"error-message"` (in quotes), and the `hidden` attribute (note: not all attributes need to have a value). [Full list of common attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes).

- [entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity): special text that should not be confused for HTML markup. Entities begin with `&` and end with `;`. For example, if you need to use the `<` character in your document, you need to use `&lt;` instead, since `<` would be interpreted as part of an HTML tag. `&nbsp;` is a single whitespace and `&amp;` is the `&` symbol. [Full list of named entities](https://dev.w3.org/html5/html-author/charref).

## HTML Documents

The first [HTML page ever created](http://info.cern.ch/hypertext/WWW/TheProject.html) was
built by [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) on August 6, 1991.

Since then, the web has gone through many versions:

- HTML - created in 1990 and standardized in 1997 as HTML 4

- xHTML - a rewrite of HTML using XML in 2000

- [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) - the current standard.

### Basic HTML5 Document

Here's a basic HTML5 web page:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>My Web Page</title>
  </head>

  <body>
    <!-- This is a comment -->
    <h1>Hello World!</h1>
  </body>
</html>
```

Let's break this down and look at what's happening.

1. [`<!doctype html>`](https://developer.mozilla.org/en-US/docs/Glossary/Doctype) tells the browser what kind of document this is (HTML5), and how to interpret/render it

2. [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) the root element of our document: all other elements will be included within `<html>...</html>`.

3. [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) provides various information _about_ the document as opposed to providing its content. This is metadata that describes the document to search engines, web browsers, and other tools.

4. [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) an example of metadata, in this case defining the [character set](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#Attributes) used in the document: [utf-8](https://en.wikipedia.org/wiki/UTF-8)

5. [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) an example of a specific (named) metadata element: the document's title, shown in the browser's title bar. There are a number of specific named metadata elements like this.

6. [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) the content of the document is contained within `<body>...</body>`.

7. `<!-- ... -->` a comment, similar to using `/* ... */` in C or JavaScript

8. [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) a heading element (there are headings 1 through 6), which is a title or sub-title in a document.

### On the Server

During the last couple of classes we learned how to create a simple web server using [Node.js](https://nodejs.org/en/) with the [Express.js](https://expressjs.com/) module. We will be using this code once again to create a local web server, which will be responsible for returning requests for our HTML document on the default route, ie "/".

> **NOTE:** Try to familiarize yourself with these steps, as we will be doing this over and over in class, every time we wish to create a new web server. A more detailed guide can be found as a part of the [Simple Web Server using Express.js](/Web-Server-Introduction/simple-web-server-using-expressjs) documentation.

1. Make a directory on your computer called `test-server`
2. Open Visual Studio Code and choose **File &gt; Open** to open your newly created `test-server` folder
3. Create a new file called `server.js`
4. Open the Integrated terminal useing the keyboard shortcut (ctrl + `` ` ``) or select "View" -> "integrated terminal" from the top menu.
5. Run the **npm init** command to generate your `package.json` file (you can choose all of the defaults)
6. Run the command `npm install express`
7. Enter the following code for your `server.js` file

   ```javascript
   const express = require("express");
   const app = express();
   const HTTP_PORT = process.env.PORT || 8080;

   const path = require("path");

   // setup a 'route' to listen on the default url path
   app.get("/", (req, res) => {
       res.sendFile(path.join(__dirname,"/views/hello.html"));
   });

   // setup http server to listen on HTTP_PORT
   app.listen(HTTP_PORT, function(){ console.log(`server listening on: ${HTTP_PORT} )});
   ```

8. Create a new folder in `test-server` named `views`
9. Within the `views` folder, create a file called `hello.html`
10. Open the newly created `hello.html` file and paste the html code from above and save the file
11. Go back to the Integrated terminal and type the command `node server.js`. You should see the message: "server listening on: 8080"
12. Open your web browser (Chrome, Firefox, etc) and enter `http://localhost:8080` in the URL bar
13. Make sure you can see a new page with "Hello World!" in black text.

#### Updating your Document

1. Go back to your editor and change the `hello.html` file so that instead of "Hello World!" you have "This is my web page."

2. Save your `hello.html` file.

3. Go back to your browser and hit the **Refresh** button.

4. Make sure your web page now says "This is my web page."

Every time we update anything in our web page, we have to refresh the web page in our browser.
The web server will serve the most recent version of the file on disk when it is
requested.
