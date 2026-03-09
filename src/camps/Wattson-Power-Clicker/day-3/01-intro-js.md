---
layout: note.njk
title: Getting Started with JavaScript
tags: wpc-d3-notes
order: 1
parentName: Day 3
---

## What is JavaScript?

If HTML is the **skeleton** of your website (the structure), and CSS is the **clothes** (the style), then JavaScript (JS) is the **brain**.

JavaScript is a programming language used to make websites dynamic and interactive. Without it, our Clicker Game is just a pretty picture. With it, we can calculate scores, buy upgrades, and make the game play itself!

## Getting Started with JavaScript (The Sandbox)

To get started with JS, you don't need any special software at first—just a web browser like Firefox, Chrome, Microsoft Edge, or Safari. Every modern browser has a JavaScript engine built right into it.

### Opening the Console

Before we write permanent code in our project files, we can test things out in the browser's "sandbox," known as the Developer Tools.

To open it, right-click anywhere on a webpage and select **Inspect**.

![Image to opening dev tools on Chrome](/images/opening-dev-tools.png)

At the top of the window that pops up, select the **Console** tab.

![Console in Chrome](/images/chrome-console.png)

You can now type JavaScript code directly into the browser and press Enter to run it! Try typing this:

```js
console.log("Hello World");
```

**`console.log()`** is a command that prints a message onto the console. We use this constantly to check if our code is working or to see the value of a score. If you've done some programming before, this is exactly like the `print()` function in Python!

## Connecting a JS Script to our HTML Code

Typing in the console is fun, but there's a big problem: **when you refresh the page, all your code disappears!**

To make our game permanent, we need to write our JavaScript inside VS Code, just like we did with our HTML and CSS. But before we link our new `.js` file, we need to understand how the browser reads files.

### The Loading Problem

Remember the Client-Server model? When your browser (the Client) loads a website, it reads the HTML file from top to bottom.

By default, if the browser is reading your HTML and suddenly hits a JavaScript file, it panics. It completely **stops reading the HTML**, downloads the JS, and executes the JS immediately.

This causes a massive bug for us. If your JS says, _"Find the Clicker Button and add a point,"_ but the browser hasn't finished reading the HTML to actually build the button yet, your game will crash!

### The Solution: The `defer` Keyword

There are a few ways to fix this, but the modern and preferred way is to use the **`defer`** keyword.

In English, to "defer" something means to put it off until later. When we add this keyword to our script tag, it tells the browser: _"Go ahead and download this JS file in the background to save time, but **wait** to execute it until all the HTML is fully built and ready on the screen."_

![Comparison of different JS loading methods](/images/js-loading.png)

### Writing the Code

To connect your JavaScript file to your HTML safely, go to your `index.html` file. Inside the `<head>` section (right near where you linked your CSS), add this line:

```html
<!-- The 'defer' keyword is the secret to making sure our game doesn't crash! -->
<script src="script.js" defer></script>
```

Now, your HTML, CSS, and JavaScript are all perfectly connected and ready to work as a team!

```

```
