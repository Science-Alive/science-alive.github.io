---
layout: note.njk
title: Functions
tags: wpc-d3-notes
order: 3
parentName: Day 3
---

## What are Functions?

Earlier, we learned that **Variables** are pointers to data (like remembering the player's score). Now, we will cover **Functions**.

If variables are the _Nouns_ of programming, functions are the _Verbs_. Functions allow us to store snippets of code (actions) so we can reuse them over and over again without having to type the same lines of code multiple times.

```js
// 1. Defining a function
function greeting() {
  console.log("Hello player!");
}

// 2. Calling a function
greeting();
greeting(); // The message prints to the console twice!
```

### Defining and Calling

It is incredibly important to understand the difference between _Defining_ a function and _Calling_ a function. A good way to think about it is like baking: defining is writing the recipe, and calling is actually baking the cake!

**How to Define a Function (Writing the Recipe)**
Creating a function follows a strict, step-by-step syntax:

1. **The Keyword:** Start by typing the word `function`. This tells the computer you are about to build a new action.
2. **The Name:** Give it a descriptive name. Because functions are actions, we usually name them with verbs (like `greeting`, `addScore`, or `buyItem`).
3. **The Parentheses:** Add `()` right after the name. Think of these like a funnel where we can drop information into the function later.
4. **The Curly Braces:** Add `{ }`. This creates the "body" of the function.
5. **The Instructions:** Write your actual code _inside_ the curly braces.

_Note: Just writing the instructions does not make them run! It just saves them for later._

**How to Call a Function (Baking the Cake)**
To actually run the code hidden inside the curly braces, you have to **Call** (or "invoke") the function.

To do this, you simply type the function's name followed by parentheses and a semicolon:
`greeting();`

The moment the computer reads that line, it jumps into the kitchen, reads your recipe, and executes the code. The best part? You can call it as many times as you want!

### Parameters and Arguments

Sometimes, a function needs a little bit of outside information to do its job. We can pass data into a function using **Parameters** and **Arguments**.

While people often use these words interchangeably, they actually mean two different things:

- **Parameter:** The placeholder variable we put inside the parentheses when _defining_ the recipe.
- **Argument:** The actual data we pass into the function when _calling_ it.

```js
// 'playerName' is the Parameter
function greeting(playerName) {
  console.log("Hello " + playerName + "!");
}

// "Wattson" and "Einstein" are the Arguments
greeting("Wattson"); // Prints: Hello Wattson!
greeting("Einstein"); // Prints: Hello Einstein!
```
