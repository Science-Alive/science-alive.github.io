---
layout: note.njk
title: Data Types & Variables
tags: wpc-d3-notes
order: 2
parentName: Day 3
---

## Data Types

In computer science, a **Data Type** tells the computer what kind of data it is looking at. This determines what operations can be performed on it.

For example, you can do Math with **Numbers**, but you cannot do Math with **Text**. If you try to multiply "Apple" \* "Orange", the computer will get confused because those are the wrong data types!

### Primitive Data Types

There are many different data types, but the three main ones we will focus on are:

- **Strings**: Represent text data. They must be surrounded by single quotes (`'hello'`), double quotes (`"hello"`), or backticks (`` `hello` ``).
- **Number**: Represents both whole integers (e.g., `42`, `-5`) and decimals (e.g., `3.14`, `0.001`).
- **Boolean**: Represents a logical entity (a switch) with only two possible values: `true` or `false`.

```js
"Hello World"; // String
42; // Number
true; // Boolean
```

## Code Comments (Notes for Humans)

In the code block above, you might have noticed the // symbols. These are called Comments.

Sometimes you want to leave a note in your code to explain what a complicated section does, or to remind yourself to fix something later. But if you just type regular words, the computer will try to read them as code and crash!

Comments are special text that the computer completely ignores. They are only there for humans to read.

### Single-Line Comments

Use two forward slashes // to create a comment on a single line. Everything after the slashes on that line is ignored.

```js
// This controls how many points you get per click
let clickPower = 1;
```

### Multi-Line Comments

If you have a lot to say, or you want to temporarily "turn off" a big chunk of code without deleting it, you can use /\* to start a comment and \*/ to end it.

```js
/*
TO DO LIST:

1. Add a background image
2. Make the button play a sound
3. Fix the shop math
*/
```

## Variables

Now that we know about data types, you might wonder: _"What happens if I have a number I need to use in ten different places, like the Player Score?"_

If we just typed `0` everywhere, and the player scored a point, we would have to find every `0` in our code and change it to `1`. That would be impossible!

That is where **Variables** come in.

Think of a variable like a **Contact in your phone**.

When you save your friend's number under the name "Alex", the word "Alex" is just a helpful label that **points** to their phone number.

In programming, data (like a score of `100` or a string like `"Game Over"`) lives out in the computer's memory. A variable is just a nametag that **points to that specific piece of data**.

Whenever you need to use that data, you don't have to remember exactly where the computer hid it; you just call the variable's name, and the computer follows the pointer right to the value!

### Variable Declaration

In modern JavaScript, we declare variables using two keywords:

- **let**: Use this when the value inside the box needs to **change** later (like a Score or Level).
- **const**: Use this when the value will **never change** (like the Game Name or the value of Pi).

```js
let score = 0; // We start at 0, but this will change.
score = 10; // We changed it!

const pi = 3.1415; // This is a universal constant.
// pi = 5;          // ERROR! You cannot change a const.
```

### Variable Naming Rules

There is a joke that naming variables is the hardest part of programming. To keep things organized, developers follow strict rules:

1.  **Camel Case:** We start with a lowercase letter, and every new word gets a Capital letter. It looks like the humps of a camel.
    - _Bad:_ `highscore`, `High_Score`
    - _Good:_ `highScore`, `playerClickPower`
2.  **Descriptive:** The name should describe what is inside the box.
    - _Bad:_ `let x = 10;` (What is x?)
    - _Good:_ `let cost = 10;`
3.  **Case Sensitive:** `score` and `Score` are two completely different variables. This is the #1 cause of bugs for beginners!

## Non-Primitive Data Types

Strings and numbers are simple. But what if we have a complex list of items?

### Arrays

Sometimes it is better to work on a list of data. Let's say we have a shop with items; it is better to store them in a list rather than creating `item1`, `item2`, and `item3`.

An **Array** is a list that can store multiple values. It is denoted by **Square Brackets** `[]`.

```js
const inventory = ["Apple", "Sword", "Potion"];
```

### Indexing

To access elements in an array, we use the square brackets with a number. This number is called the **Index**.

#### Zero Indexing

In almost all programming languages, **counting starts at 0**, not 1.

- The first item is at index `0`.
- The second item is at index `1`.

```js
console.log(inventory[0]); // Prints "Apple"
console.log(inventory[1]); // Prints "Sword"
```

### Objects

Arrays are great for lists, but what if we want to describe a specific thing with details?

An **Object** allows us to package related data together using **Key-Value pairs**. It is denoted by **Curly Braces** `{}`. Think of it like a character sheet in an RPG.

```js
const car = {
  wheels: 4,
  color: "blue",
  isElectric: true,
};
```

#### Dot Notation

To access the values inside an object, we use the **Dot Notation**. It reads just like English: "The car's color."

```js
console.log(car.color); // Prints "blue"
console.log(car.wheels); // Prints 4
```
