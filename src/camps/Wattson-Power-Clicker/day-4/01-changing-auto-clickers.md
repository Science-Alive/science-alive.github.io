---
layout: note.njk
title: Auto Clickers
tags: wpc-d4-notes
order: 1
parentName: Day 4
---

## Customizing Your Auto Clickers

Right now, our shop is full of boring, generic names like `Auto Clicker 1`. If you look at our Wattson Power Clicker example, the upgrades have fun, thematic names like "Potato Battery" and "Solar Panel"!

In order to change these names to fit your game's custom theme, we need to dive into the `index.html` file.

Look for the **Shop Items** section in your HTML code. It will look something like this:

```html
<!-- SHOP ITEM 1 -->
<button class="buy-btn" id="btn-auto1">
  <span class="count" id="count-auto1"></span>
  <!-- 📝 TODO: Name your first auto clicker! (e.g., Grandma, Helper, Robot) -->
  <span>Auto Clicker 1 (+1/sec)</span>
  <span class="cost-text" id="cost-auto1"></span>
</button>

<!-- SHOP ITEM 2 -->
<button class="buy-btn" id="btn-auto2">
  <span class="count" id="count-auto2"></span>
  <!-- 📝 TODO: Name your second auto clicker! -->
  <span>Auto Clicker 2 (+5/sec)</span>
  <span class="cost-text" id="cost-auto2"></span>
</button>

<!-- SHOP ITEM 3 -->
<button class="buy-btn" id="btn-auto3">
  <span class="count" id="count-auto3"></span>
  <!-- 📝 TODO: Name your third auto clicker! -->
  <span>Auto Clicker 3 (+10/sec)</span>
  <span class="cost-text" id="cost-auto3"></span>
</button>
```

### Changing the Labels

To change what the button says, you just need to change the text inside the `<span>` tag that is directly below the `📝 TODO` comment.

For example, if we want our very first auto-clicker to be a **Potato Battery**, we would change the HTML to look like this:

```html
<!-- SHOP ITEM 1 -->
<button class="buy-btn" id="btn-auto1">
  <span class="count" id="count-auto1"></span>
  <!-- 📝 TODO: Name your first auto clicker! (e.g., Grandma, Helper, Robot) -->
  <span>Potato Battery (+2/sec)</span>
  <span class="cost-text" id="cost-auto1"></span>
</button>
```

### Label vs. Logic

You might have noticed something interesting in the example above: we changed the text from `(+1/sec)` to `(+2/sec)`.

If you save your file and test your game in the browser right now, the button will successfully say **"Potato Battery (+2/sec)"**. But if you buy it, **you will still only get 1 point per second!**

**Why did this happen?**
Remember our human body analogy! HTML is just the _skin and bones_ (the structure). Changing the text on a button is like sticking a new label on a box; it doesn't actually change what is _inside_ the box.

To actually change the math, the speed, and the cost of our auto clickers, we need to talk to the _brain_ of our website. To do that, we have to jump over to our JavaScript file!

## Updating Auto Clicker Behavior (The Game Logic)

As we learned, changing the HTML only changes the visual label. To change the actual math and behavior of our game, we need to open our `script.js` file and look at the **`gameData`** object.

If we look closely at the `autoClickers` property inside `gameData`, we can see an **Array** (a list) filled with **Objects** (the specific items).

```js
const gameData = {
  score: 0,
  clickPower: 1,
  lastTick: Date.now(),

  // 📝 TODO: Customize your shop items!
  // ⚠️ IMPORTANT: The 'id' here MUST match the id in your HTML file!
  // Example: id: "auto1" connects to id="btn-auto1" in HTML.
  autoClickers: [
    {
      id: "auto1",
      cost: 15, // How much does the first one cost?
      rate: 1, // How many points per second does it give?
      count: 0, // How many does the player own right now? (Leave at 0)
    },
    {
      id: "auto2",
      cost: 50,
      rate: 5,
      count: 0,
    },
    {
      id: "auto3",
      cost: 250,
      rate: 10,
      count: 0,
    },
  ],
};
```

### The Blueprint of an Upgrade

Each auto-clicker object has four specific properties that act as its blueprint:

- **`id`**: This is the most important part! It acts as the "secret handshake" that connects this JavaScript object to the specific HTML button.
- **`cost`**: The price tag. How many points the player has to spend to buy it.
- **`rate`**: The power level. How many points per second this item generates.
- **`count`**: The inventory. How many of these the player currently owns (this should always start at `0`).

### Fixing the Potato Battery

Let's look back at the change we made in the HTML section. We wanted our very first auto-clicker (the Potato Battery) to generate **2 points/sec**.

To make the brain of our game match the new label on our website, we need to update the `rate` property inside the first object from `1` to `2`:

```js
    {
      id: "auto1",
      cost: 15,
      rate: 2,  // CHANGED: This now matches our HTML label!
      count: 0,
    },
```

If you save your file and test your game now, buying the Potato Battery will actually give you 2 points every single second. The Label and the Logic finally match!

_Tip: You can change the `cost` here too! If you want your first upgrade to be super cheap, change `cost: 15` to `cost: 5`._

## Expanding the Shop: Adding New Auto-Clickers

Right now, your shop only has three auto clickers. But what if you want a massive game with 10 different upgrades?

To add more auto-clickers, we need to do two things: add another button to our HTML code, and add another object to our JS script.

### Step 1: Updating the HTML

The easiest way to add more buttons without breaking your layout is to simply copy and paste the code from an existing button.

Go to your `index.html` file, copy "Shop Item 3", and paste it right below.

**⚠️ CRITICAL STEP:** You must update the IDs! If two buttons share the exact same ID, the browser will get confused and your game will break. Update all the `3`s to `4`s:

```html
<!-- SHOP ITEM 3 (Original) -->
<button class="buy-btn" id="btn-auto3">
  <span class="count" id="count-auto3"></span>
  <span>Auto Clicker 3 (+10/sec)</span>
  <span class="cost-text" id="cost-auto3"></span>
</button>

<!-- SHOP ITEM 4 (New) -->
<button class="buy-btn" id="btn-auto4">
  <!-- Change ID here -->
  <span class="count" id="count-auto4"></span>
  <!-- And here! -->
  <span>Auto Clicker 4 (+20/sec)</span>
  <span class="cost-text" id="cost-auto4"></span>
  <!-- And here! -->
</button>
```

### Step 2: Updating the JavaScript

Now that we have a 4th button, we need to give it a brain. Go to your `script.js` file and find the `autoClickers` array.

Copy the last object (the curly braces `{}`) and paste a new one right below it.

**⚠️ CRITICAL STEP:** Don't forget the comma `,` between the objects! Arrays require commas to separate items.

```js
    {
      id: "auto3",
      cost: 250,
      rate: 10,
      count: 0,
    }, // <-- Make sure this comma is here!
    {
      id: "auto4", // This MUST match the 'auto4' from your HTML!
      cost: 500,
      rate: 20,
      count: 0,
    },
```

Now you can customize the name in your HTML, and adjust the `cost` and `rate` in your JavaScript to whatever you want. Keep copy-pasting to build the ultimate shop!
