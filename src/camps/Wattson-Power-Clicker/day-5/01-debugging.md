---
layout: note.njk
title: Debugging & Troubleshooting
tags: wpc-d5-notes
order: 1
parentName: Day 5
---

## What is a Bug?

In the world of programming, a **Bug** is just a mistake in the code that causes the game to crash or behave weirdly.

If your game is broken, take a deep breath. **You are not failing.** Getting stuck and fixing bugs is not just a _part_ of a programmer's job, **it is 90% of the job!** Even the best engineers spend hours staring at their screens trying to figure out why their program isn't working as intended.

When your code doesn't work, you become a **Detective**. And every good detective needs a magnifying glass.

## The Detective's Flashlight: `console.log()`

When a game breaks, it usually happens invisibly. The screen just sits there, and you have no idea _what_ the computer is thinking.

To see inside the computer's brain, we use our favorite command: `console.log()`. This acts like a flashlight in a dark room. It forces the computer to talk to us in the Developer Tools Console.

There are two main ways we use `console.log()` to solve mysteries: **Tracking the Flow** and **Checking Values**.

### 1. Tracking the Flow (Leaving Footprints)

Sometimes you click a button, and nothing happens. The first question a detective asks is: _"Did the computer even hear my click?"_

We can leave "footprints" in our code to track exactly which paths the computer is taking. By putting a simple text message inside a function, we can prove whether or not the computer actually visited that function.

```js
function buyAutoClicker(autoClicker) {
  // 1. Leave a footprint!
  console.log("I am inside the buyAutoClicker function!");

  if (gameData.score >= autoClicker.cost) {
    // 2. Leave another footprint!
    console.log("The computer says I have enough money!");

    gameData.score -= autoClicker.cost;
    autoClicker.count++;
  } else {
    // 3. And another one!
    console.log("The computer says I am too poor.");
  }
}
```
