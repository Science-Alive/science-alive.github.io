---
layout: note.njk
title: Saving the Game
tags: wpc-d4-notes
order: 2
parentName: Day 4
---

## Memory vs. Storage

If you play your game and then refresh your browser... you end up losing all of your hard-earned points. This is definitely not what we want to happen!

To fix this, we need to understand the difference between **Memory** and **Storage** on a computer.

- **Memory (RAM):** Think of memory like your **Brain**. It is a temporary workspace for your computer to access things incredibly fast. However, when you go to sleep (or when you refresh the browser), your brain wipes that short-term memory clean. Right now, our `gameData` lives in Memory.
- **Storage (Hard Drive):** Think of storage like a **Notebook**. It is where long-term information (like pictures, apps, and code files) is saved. It takes a little longer to open a notebook and read it, but the information stays there permanently, even if the computer turns off.

To save our game, we need to take our data out of the "Brain" and write it into the browser's "Notebook" (called `localStorage`).

## Creating the Save Function

There is a slight catch: the browser's notebook can only write in plain text. It doesn't know what a JavaScript Object is!

To solve this, we use **JSON** (JavaScript Object Notation). JSON acts like a freeze-ray that transforms our complex `gameData` object into a simple text string so it can be saved.

Let's create our `saveGame` function at the bottom of our `script.js` file:

```js
function saveGame() {
  // 1. "Freeze" the object into a text string
  const gameString = JSON.stringify(gameData);

  // 2. Write it into the browser's notebook under the name "myClickerGame"
  localStorage.setItem("myClickerGame", gameString);

  // 3. Let us know it worked!
  console.log("Game Saved!");
}
```

## The Auto-Save

If we remember how functions work, what we did above was just _defining_ the save recipe. Now we need to actually _call_ it.

We could create a "Save Button" for the player to click, but it's much better to just auto-save the game in the background. We will use `setInterval` to run our save function every 15 seconds.

Inside your `main()` function, add the following code:

```js
// Time delay is measured in milliseconds (10 seconds * 1000)
setInterval(saveGame, 10000);
```

The `setInterval` method repeatedly calls a function over and over again, waiting the specified amount of milliseconds between each call.

## Loading the Game

Okay, our game is saving! But if you refresh the page, the score still resets to 0. Why? Because we wrote the data in the notebook, but **we never told the computer to read the notebook when the game starts!**

We need to retrieve the text from `localStorage`, un-freeze it back into a JavaScript object, and overwrite our starting data.

Add this function to the bottom of your script:

```js
function loadGame() {
  // 1. Read the notebook
  const savedGame = localStorage.getItem("myClickerGame");

  // 2. SAFETY CHECK: If this is the player's very first time playing,
  // there is no save file! Stop the function so the game doesn't crash.
  if (savedGame === null) {
    return;
  }

  // 3. "Un-freeze" the text back into a JavaScript Object
  const parsedGame = JSON.parse(savedGame);

  // 4. Copy the saved stats over our current gameData
  Object.assign(gameData, parsedGame);
}
```

## Starting the Engine

Finally, we need to call this load function the exact second the game boots up. Go back to your `main()` function and put `loadGame()` at the very top:

```js
function main() {
  console.log("Game Starting...");

  // Load the game before doing anything else!
  loadGame();

  // ... the rest of your main function ...
}
```

Test it out! Click your button a few times, wait 10 seconds to see the "Game Saved!" message in your console, and then refresh the page. Your points will still be there!

## How to Hard Reset

During playtesting, you might want to wipe your save file to test the beginning of the game again. Because we did our job so well, refreshing won't work anymore!

To delete your save:

1. Open your browser's Developer Tools (Inspect).
2. Go to the **Application** tab (in Chrome) or the **Storage** tab (in Firefox).
3. On the left sidebar, click **Local Storage**.
4. Right-click on your web address and click **Clear** (or find the `myClickerGame` key and delete it).
5. Refresh the browser to start with a clean slate!
