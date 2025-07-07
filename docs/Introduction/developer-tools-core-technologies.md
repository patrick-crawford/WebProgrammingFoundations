---
id: developer-tools-core-technologies
title: Developer Tools & Core Technologies
sidebar_position: 2
description: Developer Tools & Core Technologies
---

# Developer Tools & Core Technologies

Throughout this course, we will be working almost exclusively in the following environments:

## Visual Studio Code

[![Visual_Studio_2012_logo_and_wordmark](/img/Visual_Studio_2012_logo_and_wordmark-300x51.png)](http://code.visualstudio.com)

“Visual Studio Code is an open-source (free) streamlined code editor with support for development operations like debugging, task running and version control. It aims to provide just the tools a developer needs for a quick code-build-debug cycle and leaves more complex workflows to fuller featured IDEs”. Visual Studio Code also runs on Mac OS X, Linux and Windows operating systems, which will provide the class with a single unified environment to work in regardless of a student’s choice of laptop or home computer. Some of the noteworthy features of Visual Studio Code Include:

### Integrated Terminal

“In Visual Studio Code, you can open an integrated terminal, initially starting at the root of your workspace. This can be very convenient as you don’t have to switch windows or alter the state of an existing terminal to perform a quick command line task”.

To open the terminal:

- Use the keyboard shortcut **Ctrl + `**
- Use the **View** \| **Toggle Integrated Terminal menu command.**

### Smart Editing

VS Code comes with a built-in JavaScript language service so you get JavaScript code intelligence out-of-the-box. Language services provide the code understanding necessary for features like:

- IntelliSense: (suggestions)
- smart code navigation (Go to Definition, Find All References, Rename Symbol)

### File & Folder Based

Since VS Code is file and folder based – you can get started immediately by simply opening a file or folder in VS Code.

“On top of this, VS Code can read and take advantage of a variety of project files defined by different frameworks and platforms. For example, if the folder you opened in VS Code contains one or more package.json (which we will be making extensive use of during the semester), project.json, tsconfig.json, or .NET Core Visual Studio solution and project files, VS Code will read these files and use them to provide additional functionality, such as rich IntelliSense in the editor”.

### Version Control

Visual Studio Code has integrated [Git](https://git-scm.com) support for some of the most common commands, making it easy to verify and commit code changes (see ["Git"](#git) below).

## Modern Web Browser

[![Chrome Logo](/img/chrome-logo.png)](https://www.google.com/chrome/browser) [![Firefox Logo](/img/firefox-logo.png)](https://www.mozilla.org/en-US/firefox/new/)  
A modern web browser such as Google Chrome or Mozilla Firefox will be used regularly throughout this course. Microsoft Edge will work as well, as it supports a similar set of development tools, however due to it’s lack of plugins / addons and cross-platform support it’s not as highly recommended. All screenshots and development examples used throughout this course have been taken in Google Chrome.

### Browser Developer Toolbar

Before starting this course, students should have at least a basic understanding of the Developer Tools built into a modern web browser. Typically, pressing the F12 Key (Windows) will open the bar, however there are alternate ways of opening it. For Google chrome:

- Open the Chrome menu at the top-right of your browser window, then select Tools > Developer Tools.
- Right-click on any page element and select Inspect.

This will bring up the Chrome “Developer Toolbar”, as seen below :

![Dev Toolbar](/img/dev-tools2.png)

We will be working with many of these panels throughout the semester. A quick list of their functionality (from left to right, starting at the top left corner) is as follows:

<!-- prettier-ignore-start -->

| Icon                                                                 | Description |
|----------------------------------------------------------------------|-------------|
| ![Element Inspector](/img/dev-tools-1.png)                           | **Element Inspector:** Select an element in the page to inspect it; this will cause the Developer Tools (Devtools) to switch to the “Elements” panel and highlight the rendered source code (HTML) responsible for displaying the item. This will also cause the “Styles” panel (on the right) to highlight all current CSS applied to the element. |
| ![Device Toolbar Toggle](/img/dev-tools-2.jpg)                       | **Device Toolbar Toggle:** Toggles the “device toolbar” on and off. This allows the developer to select a device and manually enter the pixel dimensions of the screen and scale of the page. This is useful for ensuring that the page looks correct on a variety of devices. |
| ![Elements Panel](/img/dev-tools-3.jpg)                              | **Elements Panel:** Shows a view of the current page’s Document Object Model (DOM) tree as HTML. Selecting a given node (element) will highlight it in the page and show it’s applied CSS in the “Styles” panel. Developers can also modify this element and corresponding CSS (“Styles” panel) live and see the results directly in the browser. **Important Note:** The HTML shown in this panel isn’t necessarily the source code of the page, as it will show elements and attributes that have been dynamically added after the page is loaded. Changes to the HTML/CSS/JavaScript in this mode will not save to the source file. |
| ![Sources Panel](/img/dev-tools-5.jpg)                               | **Sources Panel:** Shows a list of all items included in the page (i.e., all images, CSS, JavaScript, etc.) and their corresponding locations of origin. Developers can click on an item to show its contents in the middle (preview) panel. If the selected item is a JavaScript file, developers can (in the “debugger” panel) set breakpoints and watch variables to help identify and debug a misbehaving piece of JavaScript code. |
| ![Console Panel](/img/dev-tools-4.jpg)                               | **Console Panel:** Shows a JavaScript console pane. JavaScript calls to `console.log()` will show the resultant text in this window. Additionally, all JavaScript errors will show up in this location in red. Developers can also write small JavaScript code snippets to be executed immediately within the context of the page. |
| ![Network Panel](/img/dev-tools-6.jpg)                               | **Network Panel:** Is used to get additional insights into requested and downloaded resources. Developers can view a log that tracks all resources loaded including their corresponding status code, type, time (latency), size of the resource and the initiator of the request. |
| ![Performance Panel](/img/performance-tab-4.png)                     | **Performance Panel:** Enables a tool that allows developers to record and analyze all the activity in their applications as they run. It’s the best place to start investigating perceived performance issues. This is done by recording a timeline of every event that occurs after a page loads and analyzing the corresponding FPS, CPU, and network requests. |
| ![Memory Panel](/img/memory-tab.png)                                 | **Memory Panel:** Provides more detailed debugging information than the timeline by enabling developers to record detailed CPU/Memory profiles such as a “Heap Snapshot”, “Allocation instrumentation on timeline", and “Allocation sampling". |
| ![Application Panel](/img/dev-tools-9.jpg)                           | **Application Panel:** Allows developers to inspect and manage client-side storage, caches, and resources. This includes: key-value pairs stored in “Local Storage”, access to IndexedDB Data (a JavaScript-based object-oriented database used to store data locally), a “Web SQL” explorer (deprecated in favor of IndexedDB), as well as access to stored cookies and cache data. This is very useful in verifying that your application is storing data correctly on the client side. |
| ![Security Panel](/img/dev-tools-10.jpg)                             | **Security Panel:** Gives an overview of a page from a security standpoint including: Certificate verification (indicating whether the site has proven its identity with a TLS certificate), Transport Layer Security (TLS) connection (Note: TLS is often referred to by the name of its predecessor, SSL), and Subresource security (indicating whether the site loads insecure HTTP subresources – i.e., “mixed content”). |
| ![Error Icon](/img/dev-tools-12.jpg)                                 | **Error Icon:** Displays the number of errors present in the “Console Pane”. To review the errors, simply switch over to the Console pane and locate the items highlighted in red. |
| ![Customize Icon](/img/dev-tools-13.jpg)                             | **Customize Icon:** Controls where the Developer Toolbar should be placed relative to the browser, as well as a collection of all related settings and preferences for the tool set. |
| ![Close Icon](/img/dev-tools-14.jpg)                                 | **Close Icon:** Closes the Developer Toolbar. |

<!-- prettier-ignore-end -->

## Core Technologies

Additionally, we will cover a number of topics surrounding the following technologies (in no particular order):

### JavaScript (ECMAScript)

![Javascript Logo](/img/javascript-logo.png)

A huge focus of this course will be on JavaScript. In fact – JavaScript will be the only official programming language that we will be studying in this course. While we will be interacting with HTML5 and CSS3, neither is considered a “programming language” in the same way that C, C++ or JavaScript is. HTML5 and CSS3 are instead considered markup languages and style sheet languages respectfully – that is, they describe presentation, whereas programming languages describe function. Regardless, we will be focusing exclusively on JavaScript and how a number of very sophisticated tools and frameworks can help us create efficient and functional web applications.

**ECMAScript**

Back in 1996 the JavaScript language specification was taken to Ecma (European Computer Manufacturers Association) International to develop a formal standardized specification, which other browser vendors and companies could implement and expand upon. This standardized JavaScript was dubbed “ECMAScript” and specific vendor versions of the specification were known as “dialects”, the most popular of which being “JavaScript”. When we refer to “JavaScript” we’re really referring to a dialect of ECMAScript that has been implemented in the engine / runtime environment that is running our JavaScript formatted code. For example, this includes JavaScript engines like SpiderMonkey in Firefox and v8 in Chrome.

In 2015, ECMAScript 6 was released and many important features were introduced, such as:

- [Arrow Functions](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Class Definitions](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes)
- [Block Scoped Variables](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/let)
- [Promises](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Binary & Octal literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar)
- [Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
- [and many more…](https://www.w3schools.com/js/js_es6.asp)

Since then, development of ECMAScript has continued and new versions are [released yearly](https://webreference.com/javascript/basics/versions). For a comprehensive list of which features are supported in specific browsers, environments and runtimes, see:

- [ECMAScript Compatibility Table](https://compat-table.github.io/compat-table/es2016plus/)

### Node.js

[![Node Logo](/img/node-logo.jpg)](https://nodejs.dev/en/)

At it’s core, Node.js is an open-source, cross-platform JavaScript runtime environment built on Chrome’s V8 JavaScript engine. It is typically used for developing server-side and networking applications and has exploded as the go-to application framework for many real-time web applications. This is largely due to it’s event-driven, non-blocking I/O model which ensures that the main thread of execution is not kept waiting for slow I/O operations (ie: stopping and waiting for a database query to complete). Some major companies using it include Paypal, eBay, GoDaddy, Microsoft, Shutterstock, Uber, Wikia just to name a few.

Node.js also has an expansive package ecosystem accessible via it’s Node Package Manager (NPM) utility. We will leverage this by experimenting with a number of popular, open-source modules including:

- [Express.js](https://www.npmjs.com/package/express) ([http://expressjs.com](http://expressjs.com))
- [EJS](https://www.npmjs.com/package/ejs) ([https://ejs.co](https://ejs.co))
- [Multer](https://www.npmjs.com/package/multer) ([https://github.com/expressjs/multer](https://github.com/expressjs/multer))
- [Sequelize](https://www.npmjs.com/package/sequelize) ([https://sequelize.org](https://sequelize.org))
- [Helmet](https://www.npmjs.com/package/helmet) ([https://helmetjs.github.io](https://helmetjs.github.io/))

### Git

[![Git Logo](/img/git-logo.png)](https://git-scm.com/)

We will be using Git: a command-line tool which serves as a version control system used for tracking changes to your source code and making it available for collaboration with other developers (by leveraging online tools such as [Github](https://github.com/) or [GitLab](https://about.gitlab.com/)). Additionally, there are many online services that connect to your published code to 3rd party cloud platforms such as [Render](https://render.com/) or [Netlify](https://www.netlify.com/) which can build your code and host your web application. For this class, we will be using [Vercel](https://vercel.com/) - please see the [Vercel Guide](/Resources/vercel-guide) for more information.

There is a ton of information online on how to get started using Git / GitHub, such as:

- [An Intro to Git and GitHub for Beginners (Tutorial)](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
- [Pro Git (eBook)](https://git-scm.com/book/en/v2)
- [Git and GitHub learning resources](https://docs.github.com/en/get-started/quickstart/git-and-github-learning-resources)

### PostgreSQL

[![PostgreSQL Logo](/img/postgres-sql-image.png)](https://www.postgresql.org/)

From the PostgreSQL site, [postgresql.org](https://www.postgresql.org):

> “PostgreSQL (also known as “Postgres”) is a powerful, open source object-relational database system. It has more than 15 years of active development and a proven architecture that has earned it a strong reputation for reliability, data integrity, and correctness. It runs on all major operating systems, including Linux, UNIX (AIX, BSD, HP-UX, SGI IRIX, macOS, Solaris, Tru64), and Windows. It is fully [ACID compliant](https://en.wikipedia.org/wiki/ACID), has full support for foreign keys, joins, views, triggers, and stored procedures (in multiple languages). It includes most SQL:2008 data types, including INTEGER, NUMERIC, BOOLEAN, CHAR, VARCHAR, DATE, INTERVAL, and TIMESTAMP. It also supports storage of binary large objects, including pictures, sounds, or video. It has native programming interfaces for C/C++, Java, .Net, Perl, Python, Ruby, Tcl, ODBC, among others, and [exceptional documentation](https://www.postgresql.org/docs/manuals/).
