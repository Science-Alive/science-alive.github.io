---
layout: note.njk
title: Event Handling
tags: wpc-d3-notes
order: 4
parentName: Day 3
---

## The DOM (Document Object Model)

Now let's get to the fun stuff: using JavaScript to interact with our website! Before we can dive into that, we must talk about a very important concept called the **Document Object Model (DOM)**.

By itself, JavaScript doesn't know what HTML is. It needs a translator or a bridge to help it see the webpage.

The **DOM** is that bridge. When the browser loads your HTML file, it converts all your tags into a "Family Tree" structure that JavaScript can read and modify.

![Diagram of the document object model tree](/images/dom-tree.png)

Thanks to the DOM, JavaScript can reach into the webpage, grab an element (like our Wattson mascot), and change its color, size, or text on the fly!

## Selecting Elements

As the "D" in DOM suggests, there is a master object called the `document`. This represents your entire webpage. We can ask the `document` to search the tree and find specific HTML elements for us.

### Using getElementById

If you gave your HTML element an `id`, this is the fastest way to grab it.

```html
<!-- In your HTML -->
<button id="click-btn">Click Me!</button>
```

```js
// In your JavaScript
// We find the button and store it in a variable (a box)
const clickBtn = document.getElementById("click-btn");
```

### Using querySelector

You can also use `document.querySelector()`. This method is incredibly powerful because it allows you to search using **CSS Selectors**. Just like in your CSS file, you use **`#` for IDs** and **`.` for Classes**!

```js
const clickBtn = document.querySelector("#click-btn");
const shopItem = document.querySelector(".buy-btn");
```

## Events

An **Event** is anything that happens in the browser, usually caused by the player. An event can be a mouse click, typing on the keyboard, scrolling down, or even resizing the window.

Right now, if a player clicks our mascot, nothing happens. In order to make the game interactive, we need to tell JavaScript to _listen_ for that specific event and then run some code when it happens.

## Event Listeners

To connect our HTML button to our JavaScript logic, we use an **Event Listener**.

Continuing from our example above:

```html
<button id="click-btn">Click Me!</button>
```

```js
const clickBtn = document.getElementById("click-btn");

// We wire the button up to listen for a click!
clickBtn.addEventListener("click", function () {
  console.log("Button was clicked!");
});
```

The `addEventListener` method is a built-in tool that requires **2 arguments** to work:

1. **The Event Type (The Trigger):** There are many event types (like `hover`, `keydown`, `scroll`), but for our buttons, we want to listen for the `"click"` event. Notice that it must be inside quotes!
2. **The Listener Function (The Action):** The second argument is the actual code you want to run when the trigger happens.

### What is a "Callback" Function?

You might notice the second argument looks a little strange because we are writing a function _inside_ of another function's parentheses: `function () { ... }`.

This is called a **Callback Function**.

We don't want the `console.log` to run immediately when the page loads. Instead, we are giving the button a "recipe" and saying: _"Hold onto this recipe. Do not cook it yet. Wait until the player clicks you, and **then** call this function back!"_
