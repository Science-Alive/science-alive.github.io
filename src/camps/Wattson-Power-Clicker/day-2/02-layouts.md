---
layout: note.njk
title: CSS Layouts & Flexbox
tags: wpc-d2-notes
order: 2
parentName: Day 2
---

## The "Block" Problem

If you have some experience with web development, you might have noticed something frustrating about standard HTML. By default, most elements (like `<div>`, `<h1>`, and `<section>`) behave like **Block Elements**.

Block elements act like boxes that want to be on their own line. They stack on top of each other, from the top of the page down to the bottom.

![image of the normal layout of webpage elements](/images/block-elements-layout.png)

This creates a problem for our Game. We want the **Clicker Area** on the left and the **Shop** on the right. If we used the default layout, the Shop would sit _underneath_ the Clicker, forcing the user to scroll down to buy upgrades.

To fix this, we need **Flexbox**.

## What is Flexbox?

Flexbox (Flexible Box Layout) is a "Layout Mode" in CSS designed to arrange items in rows or columns automatically. It is excellent for two things:

1.  Putting things side-by-side.
2.  Perfectly centering things (which is historically very hard in CSS!).

To start using Flexbox, you apply `display: flex;` to the **Parent Container**.

### 1. The Main Layout (Side-by-Side)

In our game, the `<body>` tag is the parent container. We want its two children (`.game-zone` and `.shop-zone`) to sit next to each other.

```css
/* Dark Mode Background */
body {
  /* ...colors and fonts... */

  margin: 0;
  display: flex; /* This turns the body into a Flex Container */
  height: 100vh; /* Forces the body to be as tall as the screen */
}
```

By default, `display: flex` arranges items in a **Row** (Left to Right).

### 2. Sharing the Space (`flex: 1`)

Now that they are side-by-side, how do we make them equal size? We use the `flex` property on the _children_.

```css
/* LEFT SIDE: The Game Zone */
.game-zone {
  flex: 1; /* Take 1 share of the available space */
  /* ... */
}

/* RIGHT SIDE: The Shop */
.shop-zone {
  flex: 1; /* Take 1 share of the available space */
  /* ... */
}
```

Think of `flex: 1` as a ratio. Since both zones have `1`, they split the screen 50/50. If we gave the game zone `flex: 2` and the shop `flex: 1`, the game zone would take up 66% of the screen.

### 3. Directions (`flex-direction`)

While the _Body_ uses a Row layout, the _insides_ of our zones need to be stacked. We want the Score to be above the Wattson Button.

We can change the direction of the flex stream:

- `row`: Left to Right (Default).
- `column`: Top to Bottom.

```css
.game-zone {
  display: flex; /* Turn on Flexbox inside the zone */
  flex-direction: column; /* Stack items vertically */
  /* ... */
}
```

### 4. Alignment (Centering the Button)

This is the Flexbox superpower. We can control how items sit inside the box using two properties:

- **justify-content:** Moves items along the main direction (e.g., Top to Bottom).
- **align-items:** Moves items along the cross direction (e.g., Left to Right).

In our `.game-zone`, we use both to put Wattson dead center:

```css
.game-zone {
  /* ... */
  align-items: center; /* Centers horizontally (Left/Right) */
  justify-content: center; /* Centers vertically (Top/Bottom) */
}
```

## Bonus: Flexbox in the Shop Buttons

We also use Flexbox inside the buy buttons! Look at `.buy-btn`.

We want the **Name** of the upgrade on the far left, and the **Cost** on the far right. We can use `justify-content: space-between` to force them apart.

```css
.buy-btn {
  display: flex;
  justify-content: space-between; /* Pushes child elements to the edges */
  align-items: center; /* Ensures text lines up vertically */
  width: 100%;
  /* ...colors and borders... */
}
```

![image of flex box inline direction](/images/flex-box-inline.png)
