---
layout: note.njk
title: Showcase & Final Polish
tags: wpc-d5-notes
order: 2
parentName: Day 5
---

## 🎉 CONGRATULATIONS! 🎉

Take a step back and look at your screen. Just a few days ago, you started with a completely blank text file.

Since then, you have built the **Skeleton** (HTML), painted the **Skin** (CSS), and wired up the **Brain** (JavaScript) to create a fully playable, auto-saving, interactive video game from absolute scratch.

You didn't just play a game this week, you engineered one. **You have started your web dev journey!**

Now, it is time to show off your hard work to your friends, fellow campers, and parents. But before we open the doors to our Arcade, we need to do what professional studios do before Launch Day: **The Final Polish**.

## Step 1: The "Code Freeze"

In the software industry, right before a game is released, the director declares a **Code Freeze**.

This means **no new features are allowed to be added.** If you try to add a massive new "Boss Fight" or a "Prestige System" 10 minutes before the showcase, you will probably break your game!

Instead of building new things, a Code Freeze means we spend our last hour doing two things: fixing bugs and polishing the UI. A simple game that works perfectly is _always_ better than a complicated game that crashes.

## Step 2: Squashing the Last Bugs (Stability)

You want to make sure your game doesn't crash when someone else sits down to play it. Be your own game tester!

- **Open the Console:** Press `F12` and look at your Console. Are there any red error messages? If so, put on your detective hat and fix them!
- **The "New Player" Test:** Right now, your game is balanced around _your_ save file. But a parent will be starting from 0.
  - Go to your browser's Application/Storage tab.
  - Clear your Local Storage.
  - Refresh the page.
  - Does the game load cleanly from 0

## Step 3: The Final Polish (Game Feel)

"Polish" is what separates a good game from a _great_ game. It’s all about the User Experience (UX). Go through this checklist:

- **🧹 Clean Up Your Code:** Delete any `console.log()` messages you used for testing. Erase commented-out code that you don't need anymore.
- **⚖️ Balance the Economy:** Play your game from zero for 5 minutes without cheating. Does it take way too long to buy your first upgrade? Is the second upgrade too cheap? Go into your `gameData` and tweak the `cost` and `rate` numbers until it feels _fun_.
- **👀 Check Readability:** Can a player actually read your score? If you have dark text on a dark background, change your CSS! Make sure your Shop buttons clearly display the Name and the Cost.
- **🖱️ Button Feedback:** Do your buttons feel "squishy"? Make sure you have a `:hover` and `:active` effect in your CSS so players know they are successfully clicking!

## Step 4: Welcome to the Arcade

When the polish is done, it's time to turn our classroom into an Arcade!

1.  **Set the Stage:** Close VS Code and all your other browser tabs. Make your game the only thing on the screen.
2.  **Go Fullscreen:** Press `F11` (on Windows) or `Cmd + Ctrl + F` (on Mac) to make your game take up the entire monitor. It looks like a real kiosk now!
3.  **The Arcade Walk:** You will get to walk around the room and play everyone else's games. Even though we all learned the exact same code, you will be amazed at how completely different every single game looks and feels.
4.  **Leave a Review:** When you play a peer's game, leave them a sticky note on their desk with a compliment. Tell them you loved their mascot, their color scheme, or how funny their upgrades were!

Be proud of what you built this week. Have fun at the showcase, and keep on coding!
