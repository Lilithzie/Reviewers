# jQuery & Node.js: Complete Study Guide & Reviewer

> A comprehensive reference for beginners to intermediate developers — covering definitions, use cases, code examples, and quizzes with answer keys.

---

## Table of Contents

### Part 1 — jQuery
1. [What is jQuery?](#1-what-is-jquery)
2. [Setting Up jQuery](#2-setting-up-jquery)
3. [jQuery Selectors](#3-jquery-selectors)
4. [jQuery DOM Manipulation](#4-jquery-dom-manipulation)
5. [jQuery Events](#5-jquery-events)
6. [jQuery Effects & Animations](#6-jquery-effects--animations)
7. [jQuery AJAX](#7-jquery-ajax)
8. [jQuery Traversal & Filtering](#8-jquery-traversal--filtering)
9. [jQuery Chaining](#9-jquery-chaining)
10. [jQuery Plugins](#10-jquery-plugins)

### Part 2 — Node.js
11. [What is Node.js?](#11-what-is-nodejs)
12. [Setting Up Node.js](#12-setting-up-nodejs)
13. [Node.js Modules (CommonJS & ES Modules)](#13-nodejs-modules)
14. [Node.js Core Modules](#14-nodejs-core-modules)
15. [npm & package.json](#15-npm--packagejson)
16. [File System (fs module)](#16-file-system-fs-module)
17. [HTTP Module & Creating a Server](#17-http-module--creating-a-server)
18. [Events & EventEmitter](#18-events--eventemitter)
19. [Streams & Buffers](#19-streams--buffers)
20. [Asynchronous Programming (Callbacks, Promises, Async/Await)](#20-asynchronous-programming)
21. [Express.js Basics](#21-expressjs-basics)
22. [Middleware in Express](#22-middleware-in-express)
23. [RESTful APIs with Express](#23-restful-apis-with-express)
24. [Working with Databases (MongoDB / MySQL basics)](#24-working-with-databases)
25. [Environment Variables & dotenv](#25-environment-variables--dotenv)
26. [Error Handling in Node.js](#26-error-handling-in-nodejs)
27. [Node.js Security Basics](#27-nodejs-security-basics)
28. [Deployment Basics](#28-deployment-basics)

### Part 3 — Quizzes & Answer Keys
- [jQuery Quiz](#jquery-quiz)
- [Node.js Quiz](#nodejs-quiz)

---

# Part 1 — jQuery

---

## 1. What is jQuery?

### Definition
jQuery is a **fast, small, and feature-rich JavaScript library** designed to simplify HTML document traversal and manipulation, event handling, animation, and AJAX interactions. It wraps complex JavaScript operations into concise, easy-to-read method calls using the `$()` function.

**Created by:** John Resig in 2006  
**Current Version:** jQuery 3.x  
**License:** MIT

### Where It Is Used
- Simplifying DOM manipulation (adding/removing elements, changing styles)
- Handling browser events (clicks, form submissions, hover)
- Creating animations and visual effects
- Making AJAX calls to fetch or send data without page reload
- Legacy web applications and WordPress themes
- Rapid prototyping

### Core Concept
```javascript
// Plain JavaScript
document.getElementById("btn").addEventListener("click", function() {
  document.getElementById("box").style.display = "none";
});

// jQuery equivalent — much shorter
$("#btn").click(function() {
  $("#box").hide();
});
```

### The `$` Function
The `$` (or `jQuery`) function is the entry point for everything in jQuery.
```javascript
$(selector)         // Select elements
$(function() {})    // Document ready shorthand
$.ajax({})          // Static AJAX method
```

---

## 2. Setting Up jQuery

### Definition
Setting up jQuery means loading the library into your HTML page so its methods become available in your scripts.

### Where It Is Used
Any HTML page that wants to use jQuery functionality.

### Methods

**Method 1: CDN (Content Delivery Network)**
```html
<!-- In the <head> or before closing </body> -->
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script>
  // Your jQuery code here
</script>
```

**Method 2: Download and host locally**
```html
<script src="js/jquery-3.7.1.min.js"></script>
```

**Method 3: npm (for build tools like Webpack)**
```bash
npm install jquery
```
```javascript
import $ from 'jquery';
```

### Document Ready
Always wrap your jQuery code inside a "document ready" handler so it runs only after the DOM is fully loaded.
```javascript
// Full form
$(document).ready(function() {
  // safe to use jQuery here
});

// Shorthand (preferred)
$(function() {
  // safe to use jQuery here
});
```

---

## 3. jQuery Selectors

### Definition
jQuery selectors allow you to **find and select HTML elements** based on their name, id, class, attribute, type, and more. They mirror CSS selectors, making them intuitive.

### Where It Is Used
- Before any DOM manipulation — you must first select the element
- Filtering groups of elements
- Targeting specific elements within a hierarchy

### Selector Types

| Selector | Syntax | Description |
|---|---|---|
| Element | `$("p")` | All `<p>` elements |
| ID | `$("#myId")` | Element with `id="myId"` |
| Class | `$(".myClass")` | All elements with `class="myClass"` |
| All | `$("*")` | All elements |
| Multiple | `$("h1, p, .box")` | All h1, p, and .box elements |
| Child | `$("ul > li")` | Direct `<li>` children of `<ul>` |
| Descendant | `$("div p")` | All `<p>` inside any `<div>` |
| First | `$("li:first")` | First `<li>` element |
| Last | `$("li:last")` | Last `<li>` element |
| Even | `$("tr:even")` | Even-indexed rows |
| Odd | `$("tr:odd")` | Odd-indexed rows |
| Attribute | `$("[href]")` | Elements with an href attribute |
| Attr value | `$("[type='text']")` | Elements where type equals text |

### Examples
```javascript
$("p").css("color", "blue");           // All paragraphs → blue text
$("#header").hide();                    // Hide element with id="header"
$(".card").addClass("active");          // Add class to all .card elements
$("input[type='submit']").click(...);   // Target submit buttons only
$("table tr:nth-child(2)").css(...);    // Target second row
```

---

## 4. jQuery DOM Manipulation

### Definition
DOM (Document Object Model) manipulation refers to **dynamically adding, removing, or modifying HTML elements and their content or attributes** using jQuery methods.

### Where It Is Used
- Updating page content without reloading (e.g., live search results)
- Building dynamic UI components
- Showing/hiding sections based on user interaction
- Form validation feedback

### Content Methods

```javascript
// Get/Set inner HTML
$("#box").html();               // Get HTML content
$("#box").html("<b>New!</b>"); // Set HTML content

// Get/Set text only (no HTML)
$("#box").text();               // Get text
$("#box").text("Hello");        // Set text

// Get/Set form input value
$("input").val();               // Get value
$("input").val("default");      // Set value
```

### Attribute Methods

```javascript
$("img").attr("src");                  // Get src attribute
$("img").attr("src", "new.jpg");       // Set src attribute
$("a").attr("href", "https://...");    // Change link href
$("input").removeAttr("disabled");     // Remove an attribute
```

### Class Manipulation

```javascript
$("div").addClass("highlight");         // Add class
$("div").removeClass("highlight");      // Remove class
$("div").toggleClass("highlight");      // Toggle class on/off
$("div").hasClass("highlight");         // Returns true/false
```

### Adding/Removing Elements

```javascript
// Append inside (at end)
$("ul").append("<li>New Item</li>");

// Prepend inside (at beginning)
$("ul").prepend("<li>First Item</li>");

// Insert before/after an element
$("h2").before("<p>Before heading</p>");
$("h2").after("<p>After heading</p>");

// Wrap an element
$("p").wrap("<div class='wrapper'></div>");

// Remove elements
$("p").remove();              // Remove element and its children
$("p").empty();               // Remove children only, keep the element

// Clone an element
var copy = $(".card").clone();
$("body").append(copy);
```

### CSS Manipulation

```javascript
$("p").css("color", "red");                         // Set one property
$("p").css({ "color": "red", "font-size": "18px" }); // Set multiple
$("p").css("color");                                 // Get value
```

---

## 5. jQuery Events

### Definition
jQuery events are **actions or occurrences** (user interactions or browser-triggered) that jQuery can "listen" for and respond to with a handler function.

### Where It Is Used
- Button clicks, form submissions, keyboard input
- Mouse movement, hover effects
- Page load and scroll events
- Custom event systems

### Common Event Methods

```javascript
// Click
$("button").click(function() {
  alert("Clicked!");
});

// Double-click
$("button").dblclick(function() { ... });

// Hover (mouseenter + mouseleave)
$("div").hover(
  function() { $(this).addClass("hovered"); },    // on enter
  function() { $(this).removeClass("hovered"); }  // on leave
);

// Mouse enter / leave separately
$("div").mouseenter(function() { ... });
$("div").mouseleave(function() { ... });

// Keypress events
$("input").keyup(function() {
  console.log($(this).val()); // value after key is released
});
$("input").keydown(function(e) {
  console.log(e.key); // which key was pressed
});

// Form events
$("form").submit(function(e) {
  e.preventDefault();  // Prevent page reload
  // handle form data
});

$("input").change(function() { ... });  // Value changed
$("input").focus(function() { ... });   // Input focused
$("input").blur(function() { ... });    // Input lost focus

// Window / Document events
$(window).scroll(function() { ... });
$(window).resize(function() { ... });
```

### The `.on()` Method (Preferred)
`.on()` is the modern, flexible way to bind events — it also supports **event delegation**.

```javascript
// Basic usage
$("button").on("click", function() { ... });

// Multiple events
$("input").on("focus blur", function() { ... });

// Event delegation — works for dynamically added elements
$("ul").on("click", "li", function() {
  $(this).toggleClass("done");
});
```

### Removing Events

```javascript
$("button").off("click");        // Remove click handler
$("button").off();               // Remove all handlers
```

### The Event Object

```javascript
$("a").on("click", function(event) {
  event.preventDefault();       // Stop default behavior (e.g., following link)
  event.stopPropagation();      // Stop event from bubbling up
  console.log(event.target);   // The element that triggered the event
  console.log(event.type);     // "click"
});
```

---

## 6. jQuery Effects & Animations

### Definition
jQuery effects are **built-in methods** that let you show/hide elements, fade them in and out, slide them up and down, or create custom animations — all with configurable speeds.

### Where It Is Used
- Accordion menus (slide up/down)
- Modal dialogs (fade in/out)
- Loading spinners
- Notification banners
- Image galleries

### Show / Hide / Toggle

```javascript
$("div").hide();                   // Instantly hide
$("div").show();                   // Instantly show
$("div").toggle();                 // Toggle show/hide

// With speed ("slow", "fast", or milliseconds)
$("div").hide("slow");
$("div").show(500);                // 500ms
$("div").toggle(300, function() {
  // Callback: runs when animation completes
  console.log("done!");
});
```

### Fade

```javascript
$("div").fadeIn(400);
$("div").fadeOut("slow");
$("div").fadeToggle(300);
$("div").fadeTo(500, 0.5);        // Fade to 50% opacity over 500ms
```

### Slide

```javascript
$("div").slideDown(400);          // Reveal downward
$("div").slideUp("fast");         // Collapse upward
$("div").slideToggle(300);        // Toggle slide
```

### Custom Animation with `.animate()`

```javascript
$("div").animate({
  width: "300px",
  opacity: 0.5,
  marginLeft: "50px"
}, 1000);   // Duration: 1 second

// Chained animations (run in sequence)
$("div")
  .animate({ left: "200px" }, 500)
  .animate({ top: "100px" }, 500)
  .fadeOut(300);
```

### Stop & Delay

```javascript
$("div").stop();                   // Stop the current animation
$("div").stop(true, true);         // Stop all queued, jump to end
$("div").delay(800).fadeIn(400);   // Wait 800ms, then fade in
```

---

## 7. jQuery AJAX

### Definition
AJAX (Asynchronous JavaScript and XML) allows you to **send and receive data from a server without reloading the page**. jQuery wraps the native XMLHttpRequest into simpler, readable methods.

### Where It Is Used
- Loading dynamic content (e.g., news feeds, comments)
- Form submission without page reload
- Auto-complete search boxes
- Real-time updates (scores, notifications)

### `$.ajax()` — The Core Method

```javascript
$.ajax({
  url: "https://api.example.com/users",
  method: "GET",                          // or POST, PUT, DELETE
  dataType: "json",                       // Expected response format
  data: { page: 1, limit: 10 },          // Query parameters
  success: function(response) {
    console.log(response);
  },
  error: function(xhr, status, error) {
    console.error("Error:", error);
  },
  complete: function() {
    console.log("Request finished (success or error)");
  }
});
```

### Shorthand Methods

```javascript
// GET request
$.get("https://api.example.com/data", function(data) {
  console.log(data);
});

// POST request
$.post("https://api.example.com/users", { name: "Ana", age: 25 }, function(res) {
  console.log(res);
});

// Load HTML into an element
$("#content").load("partial.html #section");

// Get JSON
$.getJSON("data.json", function(json) {
  console.log(json);
});
```

### Using Promises (Deferred)

```javascript
$.get("https://api.example.com/posts")
  .done(function(data) { console.log("Success:", data); })
  .fail(function(err) { console.log("Failed:", err); })
  .always(function() { console.log("Always runs"); });
```

### Sending JSON

```javascript
$.ajax({
  url: "/api/save",
  method: "POST",
  contentType: "application/json",
  data: JSON.stringify({ name: "Maria", score: 95 }),
  success: function(res) { console.log(res); }
});
```

---

## 8. jQuery Traversal & Filtering

### Definition
Traversal methods allow you to **navigate through the DOM tree** — moving up to parents, down to children, or sideways to siblings — starting from a selected element.

### Where It Is Used
- Finding a specific ancestor or descendant dynamically
- Selecting the next or previous sibling after an action
- Filtering a large group of elements to a subset

### Hierarchy Traversal

```javascript
// Moving DOWN (to descendants)
$("div").children();              // Direct children only
$("div").children("p");          // Direct children that are <p>
$("div").find("p");              // All <p> descendants (any depth)

// Moving UP (to ancestors)
$("span").parent();              // Direct parent
$("span").parents("div");        // All ancestor <div>s
$("span").closest("section");    // Nearest ancestor matching selector

// Moving SIDEWAYS (to siblings)
$("li").siblings();              // All siblings
$("li").next();                  // Immediately following sibling
$("li").nextAll();               // All following siblings
$("li").prev();                  // Immediately preceding sibling
$("li").prevAll();               // All preceding siblings
```

### Filtering

```javascript
$("li").first()                  // First element in set
$("li").last()                   // Last element in set
$("li").eq(2)                    // Element at index 2 (0-based)
$("li").filter(".active")        // Keep only .active elements
$("li").not(".disabled")         // Exclude .disabled elements
$("li").has("a")                 // Elements that contain an <a>
$("li").slice(1, 4)              // Elements at index 1–3
```

### Practical Example

```javascript
// When a button is clicked, find the closest form and reset it
$("button.cancel").on("click", function() {
  $(this).closest("form").trigger("reset");
});

// Highlight the next sibling of an active item
$("li.active").next().css("background", "yellow");
```

---

## 9. jQuery Chaining

### Definition
Chaining allows you to **run multiple jQuery methods on the same set of elements in a single statement**, by appending method calls one after another. Each method returns the jQuery object, enabling the next call.

### Where It Is Used
- Writing concise, readable jQuery code
- Applying multiple transformations or events to the same element
- Animating in sequence

### Examples

```javascript
// Without chaining (verbose)
$("p").css("color", "blue");
$("p").slideUp(300);
$("p").slideDown(300);

// With chaining (concise)
$("p").css("color", "blue").slideUp(300).slideDown(300);

// Multi-line chaining (still one statement)
$("#box")
  .css("width", "200px")
  .css("background", "lightblue")
  .addClass("visible")
  .fadeIn(500)
  .delay(1000)
  .fadeOut(500);
```

### `.end()` — Breaking the Chain Context

```javascript
// Find children, do something, then return to parent
$("ul")
  .find("li.active")
    .css("font-weight", "bold")
  .end()                         // Back to the <ul>
  .css("border", "1px solid red");
```

---

## 10. jQuery Plugins

### Definition
jQuery plugins are **extensions written as reusable jQuery methods** that add extra functionality to the jQuery library. You attach them to `$.fn` (jQuery's prototype).

### Where It Is Used
- Adding features not in jQuery core (date pickers, sliders, data tables)
- Encapsulating reusable behavior (e.g., a tooltip plugin)
- Third-party plugins: jQuery UI, Select2, DataTables, Slick Slider

### Using a Plugin

```html
<!-- 1. Include jQuery first -->
<script src="jquery.min.js"></script>
<!-- 2. Include the plugin -->
<script src="jquery.plugin.min.js"></script>
<script>
  // 3. Initialize the plugin
  $(".datepicker").datepicker();
  $("table").DataTable();
</script>
```

### Writing a Basic Plugin

```javascript
// Attach to $.fn to create the plugin
$.fn.highlight = function(color) {
  color = color || "yellow";         // Default color
  return this.each(function() {      // Loop each matched element
    $(this).css("background-color", color);
  });
};

// Usage
$("p").highlight();
$("h1").highlight("lightblue");
$("span").highlight("pink").fadeIn(); // Chainable because we return `this`
```

---

# Part 2 — Node.js

---

## 11. What is Node.js?

### Definition
Node.js is an **open-source, cross-platform JavaScript runtime environment** built on Chrome's V8 JavaScript engine. It allows developers to run JavaScript on the **server side** — outside the browser.

**Created by:** Ryan Dahl in 2009  
**License:** MIT  
**Key characteristic:** Non-blocking, event-driven I/O model

### Where It Is Used
- Web servers and REST APIs
- Real-time applications (chat apps, online games)
- CLI (Command Line Interface) tools
- Microservices
- Streaming applications (Netflix, Twitch)
- Build tools (Webpack, Vite, ESLint)

### Why Node.js?

| Feature | Description |
|---|---|
| Single-threaded | Uses one thread with an event loop (no blocking) |
| Non-blocking I/O | Doesn't wait for tasks to finish before moving on |
| Fast | V8 engine compiles JS to native machine code |
| NPM | Largest package ecosystem in the world |
| JavaScript everywhere | Same language on frontend and backend |

---

## 12. Setting Up Node.js

### Definition
Installing Node.js provides both the **`node` runtime** (to execute JS files) and **`npm`** (Node Package Manager, to install libraries).

### Where It Is Used
Any machine where you want to run server-side JavaScript.

### Installation

1. Download from [https://nodejs.org](https://nodejs.org) (LTS version recommended)
2. Verify installation:
```bash
node --version      # e.g., v20.11.0
npm --version       # e.g., 10.2.4
```

### Running a Script

```bash
# Create a file
echo "console.log('Hello, Node!')" > app.js

# Run it
node app.js
# Output: Hello, Node!
```

### Interactive REPL (Read-Eval-Print Loop)

```bash
node           # Opens the REPL
> 2 + 2        # 4
> .exit        # Exit REPL
```

---

## 13. Node.js Modules

### Definition
A module is a **self-contained block of code** in its own file. Node.js uses modules to organize code and share functionality between files. Node.js supports two module systems:

- **CommonJS (CJS)** — the original Node.js module system using `require()`
- **ES Modules (ESM)** — the modern standard using `import/export`

### Where It Is Used
- Every Node.js project uses modules to split code into logical files
- Importing third-party packages from npm
- Exporting utility functions for reuse

### CommonJS (CJS)

```javascript
// math.js — exporting
function add(a, b) { return a + b; }
function subtract(a, b) { return a - b; }

module.exports = { add, subtract };
// or: exports.add = add;

// app.js — importing
const { add, subtract } = require('./math');
console.log(add(5, 3));        // 8
console.log(subtract(10, 4));  // 6
```

### ES Modules (ESM)

```javascript
// math.mjs (or set "type": "module" in package.json)
export function add(a, b) { return a + b; }
export const PI = 3.14159;
export default function greet(name) { return `Hello, ${name}`; }

// app.mjs — importing
import greet, { add, PI } from './math.mjs';
console.log(greet("Maria"));   // Hello, Maria
console.log(add(2, 3));        // 5
```

### Key Difference

| Feature | CommonJS | ES Modules |
|---|---|---|
| Syntax | `require()` / `module.exports` | `import` / `export` |
| Loading | Synchronous | Asynchronous |
| Default in Node.js | Yes (until ESM enabled) | Requires `.mjs` or `"type":"module"` |
| Tree-shaking | No | Yes (bundlers can remove unused code) |

---

## 14. Node.js Core Modules

### Definition
Core modules are **built-in modules** that come with Node.js — no installation needed. They provide fundamental capabilities like file access, networking, paths, and more.

### Where It Is Used
Nearly every Node.js project uses at least one core module.

### Commonly Used Core Modules

| Module | Purpose |
|---|---|
| `fs` | File system (read/write files) |
| `path` | File path utilities |
| `http` | Create web servers |
| `https` | Secure HTTP |
| `os` | Operating system info |
| `events` | EventEmitter class |
| `stream` | Readable/writable streams |
| `crypto` | Encryption and hashing |
| `url` | URL parsing |
| `util` | Utility functions |
| `child_process` | Spawn subprocesses |
| `buffer` | Binary data handling |

### Examples

```javascript
const path = require('path');
console.log(path.join(__dirname, 'files', 'data.txt'));
// e.g., /home/user/project/files/data.txt

console.log(path.extname('photo.jpg'));   // .jpg
console.log(path.basename('/a/b/c.js')); // c.js

const os = require('os');
console.log(os.platform());   // linux, darwin, win32
console.log(os.totalmem());   // total RAM in bytes
console.log(os.homedir());    // /home/username
```

---

## 15. npm & package.json

### Definition
**npm** (Node Package Manager) is the default package manager for Node.js. It lets you install, share, and manage third-party libraries (packages). **`package.json`** is the configuration file for a Node.js project — it records the project name, version, scripts, and all dependencies.

### Where It Is Used
- Every Node.js project should have a `package.json`
- Installing libraries (Express, Axios, Mongoose, etc.)
- Defining run scripts (start, test, build)

### Initializing a Project

```bash
npm init          # Interactive setup
npm init -y       # Auto-generate with defaults
```

### package.json Structure

```json
{
  "name": "my-app",
  "version": "1.0.0",
  "description": "A simple Node.js app",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "jest"
  },
  "dependencies": {
    "express": "^4.18.2",
    "mongoose": "^8.0.0"
  },
  "devDependencies": {
    "nodemon": "^3.0.0",
    "jest": "^29.0.0"
  }
}
```

### Common npm Commands

```bash
npm install express             # Install a package (adds to dependencies)
npm install --save-dev nodemon  # Install dev-only package
npm install                     # Install all packages from package.json
npm uninstall express           # Remove a package
npm update                      # Update all packages
npm run start                   # Run the "start" script
npm list                        # List installed packages
npm outdated                    # Show outdated packages
```

### `node_modules` & `.gitignore`

```
# Always add to .gitignore:
node_modules/
```

`node_modules/` can be regenerated from `package.json` at any time with `npm install`.

---

## 16. File System (fs module)

### Definition
The `fs` (File System) module provides an API to **interact with the file system** — reading, writing, updating, and deleting files and directories. It supports both synchronous (blocking) and asynchronous (non-blocking) methods.

### Where It Is Used
- Reading config files or templates
- Writing logs
- Processing uploaded files
- Generating reports

### Async (Non-blocking) — Preferred

```javascript
const fs = require('fs');

// Read file
fs.readFile('data.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});

// Write file (overwrites)
fs.writeFile('output.txt', 'Hello, World!', (err) => {
  if (err) throw err;
  console.log('File written!');
});

// Append to file
fs.appendFile('log.txt', 'New log entry\n', (err) => {
  if (err) throw err;
});

// Delete file
fs.unlink('temp.txt', (err) => {
  if (err) throw err;
  console.log('Deleted!');
});

// Check if file exists
fs.access('config.json', fs.constants.F_OK, (err) => {
  console.log(err ? 'Does not exist' : 'Exists');
});
```

### Promises API (Modern, Recommended)

```javascript
const fs = require('fs').promises;
// or: const { readFile, writeFile } = require('fs/promises');

async function readConfig() {
  try {
    const data = await fs.readFile('config.json', 'utf8');
    return JSON.parse(data);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}
```

### Directory Operations

```javascript
fs.mkdir('new-folder', { recursive: true }, (err) => { ... });
fs.readdir('./', (err, files) => { console.log(files); });
fs.rmdir('old-folder', (err) => { ... });
```

---

## 17. HTTP Module & Creating a Server

### Definition
The `http` (and `https`) core module allows you to **create web servers** that listen for incoming requests and send back responses — the foundation of any Node.js web application.

### Where It Is Used
- Building lightweight APIs without frameworks
- Understanding how Express.js works under the hood
- Proxying or forwarding requests

### Basic HTTP Server

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  // req = IncomingMessage (request data)
  // res = ServerResponse (what we send back)

  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write('<h1>Hello from Node.js!</h1>');
  res.end();
});

server.listen(3000, () => {
  console.log('Server running at http://localhost:3000');
});
```

### Routing

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  const { url, method } = req;

  if (url === '/' && method === 'GET') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('Home Page');
  } else if (url === '/about') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('About Page');
  } else {
    res.writeHead(404, { 'Content-Type': 'text/plain' });
    res.end('404 Not Found');
  }
});

server.listen(3000);
```

### Sending JSON

```javascript
const server = http.createServer((req, res) => {
  const data = { name: "Maria", age: 22 };
  res.writeHead(200, { 'Content-Type': 'application/json' });
  res.end(JSON.stringify(data));
});
```

---

## 18. Events & EventEmitter

### Definition
The `events` module provides the **`EventEmitter` class**, which allows objects to emit named events and register listener functions that respond to those events. This is the backbone of Node.js's event-driven architecture.

### Where It Is Used
- Custom event systems in your application
- Streams (which extend EventEmitter)
- HTTP servers (which emit `request` events)
- Real-time features like chat notifications

### Basic Usage

```javascript
const EventEmitter = require('events');
const emitter = new EventEmitter();

// Register a listener
emitter.on('greet', (name) => {
  console.log(`Hello, ${name}!`);
});

// Emit the event
emitter.emit('greet', 'Maria');   // Hello, Maria!
emitter.emit('greet', 'Juan');    // Hello, Juan!
```

### Once Listener

```javascript
// Fires only once, then auto-removes
emitter.once('connected', () => {
  console.log('Connected to server');
});
```

### Removing Listeners

```javascript
function handler() { console.log('Event!'); }
emitter.on('data', handler);
emitter.off('data', handler);          // or: emitter.removeListener('data', handler)
emitter.removeAllListeners('data');    // Remove all listeners for 'data'
```

### Extending EventEmitter (Custom Class)

```javascript
const EventEmitter = require('events');

class Store extends EventEmitter {
  constructor() {
    super();
    this.items = [];
  }
  addItem(item) {
    this.items.push(item);
    this.emit('itemAdded', item);
  }
}

const store = new Store();
store.on('itemAdded', (item) => console.log(`Added: ${item}`));
store.addItem('Apple');    // Added: Apple
```

---

## 19. Streams & Buffers

### Definition
**Streams** are objects that let you **read or write data continuously** in chunks, rather than loading everything into memory at once. **Buffers** are temporary memory storage for raw binary data (when dealing with streams of data that arrive faster or slower than it can be processed).

### Where It Is Used
- Reading large files without memory overload
- Piping data from one source to another (file to HTTP response)
- Video/audio streaming
- Network communication

### Types of Streams

| Type | Description | Example |
|---|---|---|
| Readable | Data can be read from it | `fs.createReadStream()` |
| Writable | Data can be written to it | `fs.createWriteStream()` |
| Duplex | Both readable and writable | TCP socket |
| Transform | Modifies data as it passes through | `zlib.createGzip()` |

### Reading a File with Streams

```javascript
const fs = require('fs');

const readStream = fs.createReadStream('large-file.txt', 'utf8');

readStream.on('data', (chunk) => {
  console.log('Received chunk:', chunk.length, 'bytes');
});

readStream.on('end', () => {
  console.log('Done reading');
});

readStream.on('error', (err) => {
  console.error('Error:', err);
});
```

### Piping Streams

```javascript
// Pipe a readable directly into a writable
const fs = require('fs');
const readStream = fs.createReadStream('input.txt');
const writeStream = fs.createWriteStream('output.txt');

readStream.pipe(writeStream);
```

### Serving a File via HTTP Using Streams

```javascript
const http = require('http');
const fs = require('fs');

http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  fs.createReadStream('bigfile.txt').pipe(res);
}).listen(3000);
```

### Buffers

```javascript
// Create a buffer
const buf = Buffer.from('Hello');
console.log(buf);           // <Buffer 48 65 6c 6c 6f>
console.log(buf.toString()); // Hello

// Buffer of fixed size
const b2 = Buffer.alloc(5);   // 5 bytes filled with 0
b2.write('Hi');
console.log(b2.toString());   // Hi
```

---

## 20. Asynchronous Programming

### Definition
Asynchronous programming in Node.js means **operations don't block the main thread** while waiting for slow tasks (file I/O, network requests, timers). Node.js provides three patterns: **Callbacks**, **Promises**, and **Async/Await**.

### Where It Is Used
- Any I/O operation: reading files, querying databases, making API calls
- Timers (`setTimeout`, `setInterval`)
- HTTP requests

### 1. Callbacks (Legacy Pattern)

```javascript
fs.readFile('file.txt', 'utf8', function(err, data) {
  if (err) return console.error(err);
  console.log(data);
});
// Continues here WITHOUT waiting for readFile to finish
console.log("This runs first!");
```

**Callback Hell** — deep nesting of callbacks:
```javascript
getUser(id, (err, user) => {
  getPosts(user, (err, posts) => {
    getComments(posts[0], (err, comments) => {
      // Three levels deep — hard to read!
    });
  });
});
```

### 2. Promises

```javascript
const fs = require('fs').promises;

fs.readFile('file.txt', 'utf8')
  .then(data => console.log(data))
  .catch(err => console.error(err))
  .finally(() => console.log('Done'));

// Chaining
fetchUser(id)
  .then(user => fetchPosts(user))
  .then(posts => fetchComments(posts[0]))
  .catch(err => console.error(err));
```

### 3. Async/Await (Modern, Preferred)

```javascript
const fs = require('fs').promises;

async function readConfig() {
  try {
    const data = await fs.readFile('config.json', 'utf8');
    const config = JSON.parse(data);
    return config;
  } catch (err) {
    console.error('Failed to read config:', err);
  }
}

readConfig().then(config => console.log(config));
```

### Running Multiple Async Operations

```javascript
// Sequential (one after another)
const userA = await getUser(1);
const userB = await getUser(2);

// Parallel (all at once — faster)
const [userA, userB] = await Promise.all([getUser(1), getUser(2)]);

// First one to resolve wins
const result = await Promise.race([fetchA(), fetchB()]);
```

---

## 21. Express.js Basics

### Definition
**Express.js** is the most popular **web framework for Node.js**. It simplifies the creation of web servers and APIs by providing a thin layer of abstractions over Node's `http` module — routing, middleware, template rendering, and more.

### Where It Is Used
- Building REST APIs
- Server-side rendered web apps
- Backend for Single Page Applications (React, Vue, Angular)
- Microservices

### Installation & Setup

```bash
npm install express
```

```javascript
const express = require('express');
const app = express();

// Middleware to parse JSON bodies
app.use(express.json());

// Route handler
app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

### Route Methods

```javascript
app.get('/users', (req, res) => { ... });       // GET
app.post('/users', (req, res) => { ... });      // POST
app.put('/users/:id', (req, res) => { ... });   // PUT
app.patch('/users/:id', (req, res) => { ... }); // PATCH
app.delete('/users/:id', (req, res) => { ... });// DELETE
```

### Route Parameters & Query Strings

```javascript
// Route parameter: /users/42
app.get('/users/:id', (req, res) => {
  const { id } = req.params;
  res.send(`User ID: ${id}`);
});

// Query string: /search?name=Maria&age=22
app.get('/search', (req, res) => {
  const { name, age } = req.query;
  res.json({ name, age });
});
```

### Response Methods

```javascript
res.send('Text or HTML');
res.json({ key: 'value' });         // Sets Content-Type: application/json
res.status(201).json({ created: true });
res.status(404).send('Not Found');
res.redirect('/new-page');
res.sendFile('/absolute/path/to/file.html');
```

### Express Router (Modular Routes)

```javascript
// routes/users.js
const router = require('express').Router();

router.get('/', (req, res) => res.json({ users: [] }));
router.post('/', (req, res) => res.status(201).json({ created: true }));

module.exports = router;

// app.js
const usersRouter = require('./routes/users');
app.use('/api/users', usersRouter);
```

---

## 22. Middleware in Express

### Definition
Middleware are **functions that execute during the request-response cycle**, between receiving a request and sending a response. They have access to `req`, `res`, and `next()` — calling `next()` passes control to the next middleware.

### Where It Is Used
- Logging requests
- Parsing request bodies (JSON, form data)
- Authentication and authorization
- Error handling
- CORS headers

### Middleware Signature

```javascript
function myMiddleware(req, res, next) {
  // Do something
  console.log(`${req.method} ${req.url}`);
  next();  // MUST call next() or the request will hang!
}
```

### Types of Middleware

**Application-level middleware:**
```javascript
app.use(myMiddleware);                    // Runs for all routes
app.use('/api', myMiddleware);            // Runs only for /api routes
app.use(express.json());                  // Built-in: parse JSON body
app.use(express.urlencoded({ extended: true })); // Parse form data
app.use(express.static('public'));        // Serve static files
```

**Route-level middleware:**
```javascript
app.get('/dashboard', authMiddleware, (req, res) => {
  res.send('Dashboard');
});
```

**Third-party middleware:**
```bash
npm install cors morgan helmet
```
```javascript
const cors = require('cors');
const morgan = require('morgan');
const helmet = require('helmet');

app.use(cors());            // Enable Cross-Origin Resource Sharing
app.use(morgan('dev'));     // Log HTTP requests
app.use(helmet());          // Set security HTTP headers
```

**Error-handling middleware** (4 parameters — MUST have `err` first):
```javascript
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({ error: 'Something went wrong' });
});
```

---

## 23. RESTful APIs with Express

### Definition
A **REST API** (Representational State Transfer) is an architectural style for designing networked applications. It uses standard HTTP methods to perform CRUD operations on **resources** identified by URLs.

### REST Principles

| HTTP Method | Action | Example |
|---|---|---|
| GET | Read | `GET /api/users` or `GET /api/users/1` |
| POST | Create | `POST /api/users` |
| PUT | Full Update | `PUT /api/users/1` |
| PATCH | Partial Update | `PATCH /api/users/1` |
| DELETE | Delete | `DELETE /api/users/1` |

### Where It Is Used
- Building APIs consumed by frontend apps, mobile apps, or third-party services

### Full CRUD Example

```javascript
const express = require('express');
const app = express();
app.use(express.json());

let users = [
  { id: 1, name: 'Maria', email: 'maria@email.com' },
  { id: 2, name: 'Juan', email: 'juan@email.com' }
];

// GET all users
app.get('/api/users', (req, res) => {
  res.json(users);
});

// GET one user
app.get('/api/users/:id', (req, res) => {
  const user = users.find(u => u.id === parseInt(req.params.id));
  if (!user) return res.status(404).json({ error: 'User not found' });
  res.json(user);
});

// POST — create user
app.post('/api/users', (req, res) => {
  const { name, email } = req.body;
  const newUser = { id: users.length + 1, name, email };
  users.push(newUser);
  res.status(201).json(newUser);
});

// PUT — update user
app.put('/api/users/:id', (req, res) => {
  const user = users.find(u => u.id === parseInt(req.params.id));
  if (!user) return res.status(404).json({ error: 'Not found' });
  user.name = req.body.name || user.name;
  user.email = req.body.email || user.email;
  res.json(user);
});

// DELETE
app.delete('/api/users/:id', (req, res) => {
  const index = users.findIndex(u => u.id === parseInt(req.params.id));
  if (index === -1) return res.status(404).json({ error: 'Not found' });
  users.splice(index, 1);
  res.status(204).end();
});

app.listen(3000);
```

---

## 24. Working with Databases

### Definition
Databases store persistent data for your application. Node.js applications commonly use **MongoDB** (NoSQL, document-based) with Mongoose ODM, or **MySQL/PostgreSQL** (SQL, relational) with libraries like `mysql2` or `pg`.

### Where It Is Used
- Storing user accounts, posts, orders, etc.
- Querying and filtering application data

### MongoDB with Mongoose

```bash
npm install mongoose
```

```javascript
const mongoose = require('mongoose');

// Connect
mongoose.connect('mongodb://localhost:27017/mydb');

// Define Schema
const userSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  age: Number,
  createdAt: { type: Date, default: Date.now }
});

// Create Model
const User = mongoose.model('User', userSchema);

// Create
const newUser = new User({ name: 'Maria', email: 'maria@email.com', age: 22 });
await newUser.save();

// Read
const users = await User.find();
const user = await User.findById('64abc123...');
const active = await User.find({ age: { $gte: 18 } });

// Update
await User.findByIdAndUpdate('64abc...', { age: 23 }, { new: true });

// Delete
await User.findByIdAndDelete('64abc...');
```

### MySQL with mysql2

```bash
npm install mysql2
```

```javascript
const mysql = require('mysql2/promise');

const pool = mysql.createPool({
  host: 'localhost', user: 'root',
  password: 'secret', database: 'mydb'
});

// Query
const [rows] = await pool.query('SELECT * FROM users WHERE age > ?', [18]);
console.log(rows);

// Insert
await pool.query('INSERT INTO users (name, email) VALUES (?, ?)', ['Maria', 'maria@email.com']);
```

---

## 25. Environment Variables & dotenv

### Definition
**Environment variables** are key-value pairs stored in the operating system or a `.env` file, used to **store sensitive configuration** (database credentials, API keys, port numbers) outside your source code.

**`dotenv`** is a popular npm package that loads variables from a `.env` file into `process.env`.

### Where It Is Used
- Storing database connection strings
- API keys and secrets
- Port numbers
- Feature flags for different environments (development, production)

### Setup

```bash
npm install dotenv
```

```
# .env file (NEVER commit this to Git!)
PORT=3000
DB_URI=mongodb://localhost:27017/mydb
JWT_SECRET=supersecretkey123
NODE_ENV=development
```

```javascript
// At the very top of your entry file (e.g., app.js)
require('dotenv').config();

const port = process.env.PORT || 3000;
const dbUri = process.env.DB_URI;

console.log(`Running on port ${port}`);
mongoose.connect(dbUri);
```

Always add `.env` to `.gitignore`:
```
.env
node_modules/
```

---

## 26. Error Handling in Node.js

### Definition
Error handling is the practice of **catching, logging, and responding to errors gracefully** instead of letting them crash your application or leak sensitive details to users.

### Where It Is Used
- Anywhere async operations can fail (DB queries, file reads, API calls)
- Express route handlers
- Uncaught exceptions at process level

### Types of Errors

```javascript
// Operational errors (expected): network timeout, invalid input, file not found
// Programmer errors (bugs): undefined variable, type mismatch
```

### Try/Catch (Async/Await)

```javascript
app.get('/users/:id', async (req, res, next) => {
  try {
    const user = await User.findById(req.params.id);
    if (!user) return res.status(404).json({ error: 'Not found' });
    res.json(user);
  } catch (err) {
    next(err);  // Pass to error middleware
  }
});
```

### Custom Error Class

```javascript
class AppError extends Error {
  constructor(message, statusCode) {
    super(message);
    this.statusCode = statusCode;
    this.isOperational = true;
  }
}

// Usage
throw new AppError('User not found', 404);
```

### Global Error Handler (Express)

```javascript
// Must be defined AFTER all routes
app.use((err, req, res, next) => {
  const statusCode = err.statusCode || 500;
  res.status(statusCode).json({
    status: 'error',
    message: err.message || 'Internal Server Error'
  });
});
```

### Process-level Error Handling

```javascript
process.on('uncaughtException', (err) => {
  console.error('Uncaught Exception:', err);
  process.exit(1);  // Restart via process manager
});

process.on('unhandledRejection', (reason, promise) => {
  console.error('Unhandled Rejection at:', promise, 'reason:', reason);
});
```

---

## 27. Node.js Security Basics

### Definition
Security in Node.js means **protecting your application and users** from common vulnerabilities like injection attacks, unauthorized access, and data exposure.

### Where It Is Used
- All production Node.js/Express applications

### Key Security Practices

**1. Use `helmet` for HTTP security headers**
```javascript
const helmet = require('helmet');
app.use(helmet());  // Sets X-Frame-Options, Content-Security-Policy, etc.
```

**2. Validate and sanitize user input**
```bash
npm install express-validator
```
```javascript
const { body, validationResult } = require('express-validator');

app.post('/users', [
  body('email').isEmail(),
  body('password').isLength({ min: 8 })
], (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) return res.status(400).json({ errors: errors.array() });
  // ...
});
```

**3. Use bcrypt to hash passwords**
```bash
npm install bcrypt
```
```javascript
const bcrypt = require('bcrypt');
const hashed = await bcrypt.hash('plaintext', 12);
const match = await bcrypt.compare('plaintext', hashed); // true
```

**4. JWT for Authentication**
```bash
npm install jsonwebtoken
```
```javascript
const jwt = require('jsonwebtoken');
const token = jwt.sign({ userId: 123 }, process.env.JWT_SECRET, { expiresIn: '1h' });
const decoded = jwt.verify(token, process.env.JWT_SECRET);
```

**5. Rate limiting**
```bash
npm install express-rate-limit
```
```javascript
const rateLimit = require('express-rate-limit');
app.use(rateLimit({ windowMs: 15 * 60 * 1000, max: 100 })); // 100 requests per 15 min
```

**6. Prevent NoSQL Injection (MongoDB)**
```javascript
// Never do this:
User.findOne({ username: req.body.username }); // Could inject { $ne: null }

// Use validation/sanitization libraries like express-validator or joi
```

---

## 28. Deployment Basics

### Definition
Deployment is the process of **making your Node.js application available on a server** so users can access it over the internet.

### Where It Is Used
Any application that needs to be accessible beyond your local machine.

### Common Deployment Targets

| Platform | Description |
|---|---|
| Heroku | PaaS, easy for beginners |
| Railway | Modern Heroku alternative |
| Render | Simple, free tier available |
| DigitalOcean / Linode | VPS, more control |
| AWS / GCP / Azure | Enterprise cloud |
| Vercel | Great for serverless Node |

### Using PM2 (Process Manager)

```bash
npm install -g pm2

pm2 start app.js --name "my-app"
pm2 restart my-app
pm2 stop my-app
pm2 logs my-app
pm2 startup          # Auto-start on server reboot
```

### Environment Setup for Production

```javascript
// Detect environment
if (process.env.NODE_ENV === 'production') {
  // Enable production-only configs
}

// Set in shell before running:
NODE_ENV=production node app.js
```

### Basic Checklist Before Deploying

- [ ] `NODE_ENV=production` set
- [ ] `.env` file is NOT committed; environment variables set on server
- [ ] `node_modules/` in `.gitignore`
- [ ] Input validation and error handling in place
- [ ] HTTPS enforced (via reverse proxy like Nginx or Heroku's built-in SSL)
- [ ] Logging configured
- [ ] PM2 or similar process manager running

---

# Part 3 — Quizzes & Answer Keys

---

## jQuery Quiz

### Section A — Multiple Choice

**Q1.** Which symbol is the shorthand for the jQuery function?

a) `#`  
b) `@`  
c) `$`  
d) `&`

---

**Q2.** What does `$(document).ready()` do?

a) Loads the jQuery library  
b) Sends an AJAX request to the server  
c) Executes code only after the full HTML document is loaded in the DOM  
d) Creates a new HTML document

---

**Q3.** Which selector targets all elements with the class `highlight`?

a) `$("highlight")`  
b) `$("#highlight")`  
c) `$(".highlight")`  
d) `$("[highlight]")`

---

**Q4.** What is the correct way to change the text of a `<p>` element to "Hello" in jQuery?

a) `$("p").html = "Hello";`  
b) `$("p").text("Hello");`  
c) `$("p").value("Hello");`  
d) `$("p").set("Hello");`

---

**Q5.** What does `$("ul").append("<li>Item</li>")` do?

a) Replaces the `<ul>` contents with one item  
b) Adds a new `<li>` before the `<ul>`  
c) Adds a new `<li>` as the last child inside the `<ul>`  
d) Creates a new unordered list

---

**Q6.** Which method binds an event listener in the modern jQuery way, supporting event delegation?

a) `.click()`  
b) `.bind()`  
c) `.live()`  
d) `.on()`

---

**Q7.** What does `event.preventDefault()` do in a jQuery event handler?

a) Stops the event from firing entirely  
b) Prevents the default browser behavior for the event (e.g., stops a link from navigating)  
c) Removes the event listener  
d) Reloads the page

---

**Q8.** Which jQuery method makes an element gradually disappear?

a) `.hide()`  
b) `.remove()`  
c) `.fadeOut()`  
d) `.slideUp()`

---

**Q9.** What does `$.ajax()` primarily do?

a) Animates elements on the page  
b) Selects multiple DOM elements  
c) Sends asynchronous HTTP requests to a server  
d) Loads the jQuery library dynamically

---

**Q10.** What does the following code do?
```javascript
$("div").find("p").css("color", "red").end().css("border", "1px solid black");
```

a) Sets all `<p>` to red and all `<div>` to have a border  
b) Only sets `<p>` to red  
c) Only sets `<div>` border  
d) Throws an error

---

### Section B — True or False

**Q11.** jQuery can be used without including it from a CDN or local file.

**Q12.** `$("p").html()` with no arguments gets the inner HTML of the first matched `<p>` element.

**Q13.** `.on("click", "li", handler)` will work for `<li>` elements added to the DOM after the listener is registered.

**Q14.** The `.animate()` method can animate any CSS property, including color.

**Q15.** Chaining in jQuery allows you to call multiple methods on the same set of elements in one statement.

---

### Section C — Fill in the Blank

**Q16.** To remove an element from the DOM in jQuery, you use the `________()` method.

**Q17.** To get the value of a form input field in jQuery, you use `________()`.

**Q18.** `$("li").________()` returns the last element in the matched set.

**Q19.** In jQuery, `________` is used to navigate from a child element to its direct parent.

**Q20.** To prevent a form from reloading the page on submission, you call `event.________()` inside the submit handler.

---

### Section D — Code Output / Short Answer

**Q21.** What will the following code print in the browser console?
```javascript
$("button").on("click", function() {
  console.log($(this).text());
});
// HTML: <button>Click Me</button>
```

**Q22.** Write jQuery code to fade in a `<div id="banner">` over 600 milliseconds when the page loads.

**Q23.** Write jQuery code to make an AJAX GET request to `/api/data` and log the response to the console.

**Q24.** What is wrong with this code?
```javascript
$.fn.myPlugin = function() {
  this.css("color", "red");
};
```

**Q25.** Write jQuery code to select all `<input>` elements inside a `<form id="signup">` and disable them.

---

## jQuery Quiz — Answer Key

**Q1.** **c) `$`**  
The dollar sign `$` is the alias for the `jQuery` function.

**Q2.** **c) Executes code only after the full HTML document is loaded in the DOM**  
This ensures your jQuery code can safely access and manipulate DOM elements.

**Q3.** **c) `$(".highlight")`**  
Class selectors use a `.` prefix, just like in CSS.

**Q4.** **b) `$("p").text("Hello");`**  
`.text()` sets the text content. `.html()` would also work but allows HTML tags.

**Q5.** **c) Adds a new `<li>` as the last child inside the `<ul>`**  
`.append()` inserts content at the end of the matched element's children.

**Q6.** **d) `.on()`**  
`.on()` is the preferred modern method and supports event delegation for dynamically added elements.

**Q7.** **b) Prevents the default browser behavior for the event**  
For example, stopping a link from navigating or a form from submitting normally.

**Q8.** **c) `.fadeOut()`**  
`.fadeOut()` gradually decreases opacity to 0. `.hide()` is instant. `.slideUp()` collapses height. `.remove()` deletes the element.

**Q9.** **c) Sends asynchronous HTTP requests to a server**  
`$.ajax()` is jQuery's core method for making AJAX requests.

**Q10.** **a) Sets all `<p>` to red and all `<div>` to have a border**  
`.find("p")` narrows the selection to `<p>` elements; `.end()` returns the selection back to the `<div>`, so the border applies to the `<div>`.

**Q11.** **False** — jQuery must be loaded from a CDN, npm package, or local file before it can be used.

**Q12.** **True** — `.html()` with no arguments returns the inner HTML of the first matched element.

**Q13.** **True** — Event delegation via `.on("click", "li", handler)` listens on the parent element so it catches events from dynamically added children.

**Q14.** **False** — `.animate()` cannot animate color by default. You need the jQuery UI library or a plugin for color animation.

**Q15.** **True** — Chaining works because most jQuery methods return the jQuery object itself.

**Q16.** `.remove()`

**Q17.** `.val()`

**Q18.** `.last()`

**Q19.** `.parent()`

**Q20.** `preventDefault`

**Q21.** When the button is clicked, it logs **"Click Me"** — the text content of the clicked button.

**Q22.**
```javascript
$(function() {
  $("#banner").fadeIn(600);
});
```

**Q23.**
```javascript
$.get('/api/data', function(response) {
  console.log(response);
});
// OR using $.ajax:
$.ajax({ url: '/api/data', method: 'GET', success: (data) => console.log(data) });
```

**Q24.** The plugin does not return `this`, making it **un-chainable**. It should be:
```javascript
$.fn.myPlugin = function() {
  return this.css("color", "red"); // return this!
};
```

**Q25.**
```javascript
$("#signup input").prop("disabled", true);
```

---

## Node.js Quiz

### Section A — Multiple Choice

**Q1.** Node.js runs JavaScript on which engine?

a) SpiderMonkey  
b) Chakra  
c) V8  
d) JavaScriptCore

---

**Q2.** Which command initializes a new Node.js project and creates a `package.json`?

a) `node init`  
b) `npm start`  
c) `npm init -y`  
d) `npm create`

---

**Q3.** In CommonJS, how do you export a function called `greet` from a module?

a) `export greet;`  
b) `module.exports = greet;`  
c) `exports default greet;`  
d) `return greet;`

---

**Q4.** What does `require('path')` return?

a) A file path string  
b) The current file's directory  
c) A built-in Node.js module for working with file paths  
d) The `package.json` configuration

---

**Q5.** What is the purpose of `node_modules/`?

a) To store your application's source code  
b) To hold installed npm packages and their dependencies  
c) To store environment variables  
d) To keep log files

---

**Q6.** Which `fs` method reads a file without blocking the event loop?

a) `fs.readFileSync()`  
b) `fs.openFile()`  
c) `fs.readFile()`  
d) `fs.getFile()`

---

**Q7.** What does `next()` do in Express middleware?

a) Sends the HTTP response  
b) Cancels the request  
c) Passes control to the next middleware function in the stack  
d) Moves to the next route file

---

**Q8.** Which HTTP method is used to completely replace an existing resource?

a) GET  
b) POST  
c) PATCH  
d) PUT

---

**Q9.** In Express, how do you access query parameters from a URL like `/search?name=Maria`?

a) `req.params.name`  
b) `req.body.name`  
c) `req.query.name`  
d) `req.headers.name`

---

**Q10.** What is the purpose of `dotenv` and `.env` files?

a) To define TypeScript types  
b) To store and load environment-specific configuration outside of source code  
c) To set up CSS variables for the frontend  
d) To declare global JavaScript variables

---

**Q11.** Which of the following correctly creates an Express error-handling middleware?

a) `app.use(function(req, res) { ... })`  
b) `app.use(function(err, req, res, next) { ... })`  
c) `app.error(function(err, res) { ... })`  
d) `app.catch(function(err) { ... })`

---

**Q12.** What does `Promise.all([p1, p2, p3])` do?

a) Runs promises one after another sequentially  
b) Returns the first promise to settle  
c) Waits for ALL promises to resolve (or rejects if any one fails)  
d) Cancels all pending promises

---

### Section B — True or False

**Q13.** Node.js is multi-threaded by default, using one thread per HTTP request.

**Q14.** `process.env` is a built-in Node.js object that holds environment variables.

**Q15.** `async/await` is syntactic sugar built on top of Promises.

**Q16.** The `devDependencies` in `package.json` are included in production builds by default when running `npm install --production`.

**Q17.** `EventEmitter.once()` registers a listener that automatically removes itself after firing once.

**Q18.** Streams in Node.js require all data to be loaded into memory before processing begins.

---

### Section C — Fill in the Blank

**Q19.** In Express, `req.________` holds URL route parameters (e.g., from `/users/:id`).

**Q20.** The npm command to install a package only for development is `npm install --________`.

**Q21.** `________` is the built-in Node.js module used to create an HTTP server.

**Q22.** To hash a password securely in Node.js, a commonly used package is `________`.

**Q23.** In an async function, the `________` keyword is used before a Promise to wait for its result.

**Q24.** The Express method `________` is used to serve static files from a directory.

---

### Section D — Code Reading / Short Answer

**Q25.** What does this code do?
```javascript
const emitter = new EventEmitter();
emitter.once('launch', () => console.log('Launched!'));
emitter.emit('launch');
emitter.emit('launch');
```

**Q26.** What will the following code output, and in what order?
```javascript
console.log('Start');
setTimeout(() => console.log('Timeout'), 0);
console.log('End');
```

**Q27.** Write Express code to create a `GET /api/products` route that responds with a JSON array of two products.

**Q28.** What is wrong with the following code, and how would you fix it?
```javascript
app.get('/user/:id', async (req, res) => {
  const user = await User.findById(req.params.id);
  res.json(user);
});
```

**Q29.** Explain the difference between `req.params`, `req.query`, and `req.body` in Express.

**Q30.** Write code using `fs.promises` to read a file called `notes.txt` and log its contents using async/await.

---

## Node.js Quiz — Answer Key

**Q1.** **c) V8**  
Node.js uses Google's V8 engine (the same one in Chrome) to execute JavaScript.

**Q2.** **c) `npm init -y`**  
`-y` auto-answers all prompts with defaults, creating `package.json` instantly.

**Q3.** **b) `module.exports = greet;`**  
In CommonJS, you export using `module.exports`. ES Modules use `export`.

**Q4.** **c) A built-in Node.js module for working with file paths**  
`path` provides utilities like `path.join()`, `path.extname()`, `path.resolve()`.

**Q5.** **b) To hold installed npm packages and their dependencies**  
It should always be in `.gitignore` since it can be regenerated with `npm install`.

**Q6.** **c) `fs.readFile()`**  
`fs.readFile()` is asynchronous (non-blocking). `fs.readFileSync()` blocks the event loop.

**Q7.** **c) Passes control to the next middleware function in the stack**  
Without calling `next()`, the request will hang and never get a response.

**Q8.** **d) PUT**  
PUT replaces the entire resource. PATCH is for partial updates only.

**Q9.** **c) `req.query.name`**  
Query string parameters are in `req.query`. Route parameters are in `req.params`. POST body is in `req.body`.

**Q10.** **b) To store and load environment-specific configuration outside of source code**  
This keeps secrets (API keys, passwords) out of your codebase.

**Q11.** **b) `app.use(function(err, req, res, next) { ... })`**  
Error-handling middleware MUST have exactly 4 parameters — Express detects the `err` as the first argument.

**Q12.** **c) Waits for ALL promises to resolve (or rejects if any one fails)**  
`Promise.all()` runs promises in parallel and resolves when all are done.

**Q13.** **False** — Node.js is **single-threaded**, using an event loop with non-blocking I/O to handle concurrency.

**Q14.** **True** — `process.env` is a global object in Node.js that contains all environment variables.

**Q15.** **True** — `async/await` is syntactic sugar over Promises, making asynchronous code read like synchronous code.

**Q16.** **False** — `devDependencies` are **NOT** installed when running `npm install --production`. They are only for development tools.

**Q17.** **True** — `.once()` registers a one-time listener that is automatically removed after it fires once.

**Q18.** **False** — Streams process data in **chunks** without loading everything into memory — that is precisely their advantage.

**Q19.** `params` → `req.params`

**Q20.** `save-dev` → `npm install --save-dev`

**Q21.** `http` (the `http` core module)

**Q22.** `bcrypt`

**Q23.** `await`

**Q24.** `express.static()` → `app.use(express.static('public'))`

**Q25.** 
- First `emit('launch')` → logs `"Launched!"`
- Second `emit('launch')` → **nothing happens** because `.once()` auto-removed the listener after it fired the first time.

**Q26.** Output order:
```
Start
End
Timeout
```
`console.log` runs synchronously. `setTimeout` with 0ms delay is still asynchronous — it goes into the callback queue and runs after the synchronous code finishes.

**Q27.**
```javascript
app.get('/api/products', (req, res) => {
  const products = [
    { id: 1, name: 'Laptop', price: 999 },
    { id: 2, name: 'Mouse', price: 25 }
  ];
  res.json(products);
});
```

**Q28.** The code is **missing error handling**. If `User.findById()` throws (e.g., invalid ID format or DB error), the error will be unhandled and may crash the server. Fix:
```javascript
app.get('/user/:id', async (req, res, next) => {
  try {
    const user = await User.findById(req.params.id);
    if (!user) return res.status(404).json({ error: 'Not found' });
    res.json(user);
  } catch (err) {
    next(err);  // Pass to Express error handler
  }
});
```

**Q29.**

| Property | Source | Example URL / Request |
|---|---|---|
| `req.params` | URL route parameters (`:id`) | `/users/42` → `req.params.id = "42"` |
| `req.query` | URL query string | `/search?name=Maria` → `req.query.name = "Maria"` |
| `req.body` | Request body (POST/PUT) | JSON or form data sent in the body |

**Q30.**
```javascript
const fs = require('fs').promises;

async function readNotes() {
  try {
    const content = await fs.readFile('notes.txt', 'utf8');
    console.log(content);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}

readNotes();
```

---

## Quick Reference Cheat Sheet

### jQuery One-Liners
```javascript
$("#id").hide()                     // Hide by ID
$(".cls").css("color","red")        // Style by class
$("form").on("submit", fn)          // Form submit
$.get("/url", fn)                   // GET request
$("ul").append("<li>Item</li>")     // Add list item
$(this).closest("form").reset()     // Find nearest form
```

### Node.js / Express One-Liners
```javascript
require('dotenv').config()          // Load .env
app.use(express.json())             // Parse JSON bodies
app.use(cors())                     // Enable CORS
res.status(201).json(data)          // 201 Created response
const { id } = req.params           // Get route param
await Model.find({ active: true })  // Mongoose query
```

---

