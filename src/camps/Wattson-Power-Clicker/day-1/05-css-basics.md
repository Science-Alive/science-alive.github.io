---
layout: note.njk
title: CSS Basics
tags: wpc-d1-notes
order: 5
parentName: Day 1
---

## The Anatomy of a CSS Rule

Just as HTML uses tags for structure, CSS uses rules to apply style. Every line of CSS is a command that follows the same structure: **Selector, Property, and Value.**

```css
/* This is a CSS Rule */
p {
  font-weight: bold;
}
```

| Part of the Rule  |    What it is     |                                               Analogy                                                |
| :---------------: | :---------------: | :--------------------------------------------------------------------------------------------------: |
|      **`p`**      | **The Selector**  |  **The Target.** It says: "Find every single element that matches this tag (`<p>`, `<h1>`, etc.)."   |
| **`font-weight`** | **The Property**  | **The Feature.** This is what you want to change (the color, the size, the spacing, the font, etc.). |
|    **`bold`**     |   **The Value**   |   **The Setting.** This is what you want the change to _be_ (e.g., `blue`, `20px`, `bold`, etc.).    |
|      **`;`**      | **The Semicolon** |              **The Stop Sign.** Always put one at the end of every property-value pair!              |

## Types of Selectors: How to Target

There are two main ways to tell CSS _which_ elements you want to style.

### A. The Type Selector (The Broad Approach)

This targets **every single instance** of an HTML tag.

- **Syntax:** Just the tag name (e.g., `h1`, `p`, `img`).
- **Use case:** "I want _all_ my paragraphs to be size 16px."

```css
/* Every <p> tag on the website will be blue */
p {
  color: blue;
}
```

### B. The Class Selector (The Precise Approach)

This targets **only specific elements** that you have labelled. This allows you to create exceptions (e.g., "I want _most_ text black, but _this specific_ text red").

- **Syntax:** Starts with a **dot** (`.`) followed by a name you invent.
- **Use case:** "I want a special style for my error messages."

**Step 1: Create the Rule (CSS)**

```css
/* The dot tells CSS: "Look for a class named highlight" */
.highlight {
  background-color: yellow;
}
```

**Step 2: Apply the Label (HTML)**

```css
<p class="highlight">This text is highlighted.</p>
<p>This text is normal.</p>
```

## Understanding Colors

Computers are very specific about color. There are three main ways to tell the computer which color you want.

| Type             | Example                  | Description                                                                                                                                                                |
| :--------------- | :----------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Named Colors** | `color: red;`            | **The Basic Box.** There are about 140 named colors (e.g., `Blue`, `Tomato`, `PapayaWhip`). Great for testing, but limited for design.                                     |
| **Hex Codes**    | `color: #FF5733;`        | **The Computer's Language.** A hashtag followed by 6 characters (0-9 and A-F). This is the industry standard because it allows for 16 million specific color combinations. |
| **RGB**          | `color: rgb(255, 0, 0);` | **Mixing Light.** Stands for **R**ed, **G**reen, **B**lue. You define how much of each light to mix, from 0 (none) to 255 (full blast).                                    |

> **Pro Tip:** You don't need to memorize Hex codes! In VS Code, if you hover over a color, a color picker will appear. You can also search "Color Picker" on Google.

## Typography: Dressing Up Your Text

Most of the web is text, so how that text looks is crucial. We control this using **Fonts** and **Sizing**.

### A. Serif vs. Sans-Serif

When choosing a font family, you usually choose between two main categories.
![Serif vs Sans-Serif](/assets/images/tech/intro-to-web-dev/serif-vs-sans.png)

| Category       | Visual Feature                                                                           | Vibe                                 | Examples                            |
| :------------- | :--------------------------------------------------------------------------------------- | :----------------------------------- | :---------------------------------- |
| **Serif**      | Has little "feet" or decorative lines at the ends of letters.                            | Traditional, Formal, Newspaper-like. | Times New Roman, Georgia, Garamond. |
| **Sans-Serif** | "Sans" means _without_ in French. These letters have clean, straight edges with no feet. | Modern, Clean, Digital-friendly.     | Arial, Helvetica, Verdana.          |

```css
/* Example of setting a modern font */
h1 {
  font-family: Arial, sans-serif;
}
```

### B. Font Sizing: `px` vs. `rem`

How big should your text be? While you can use pixels (`px`), modern developers prefer using `rem`.

- **Pixels (`px`):** The rigid unit. `font-size: 16px` forces the text to be exactly that size. It’s easy to understand, but bad for accessibility (users with visual impairments cannot easily scale it up).
- **Rems (`rem`):** The flexible unit. `rem` stands for **"Root EM"**. It is a multiplier relative to the browser's default setting (which is usually 16px).

**Think of `rem` as a multiplier:**

- `1rem` = 1x Normal Size (Usually 16px)
- `2rem` = 2x Normal Size (Usually 32px)
- `0.5rem` = Half Size (Usually 8px)

> **Why use `rem`?** If a user sets their browser to "Large Text Mode" because they have poor eyesight, `rem` text will automatically grow larger to help them. `px` text will stay small and unreadable. **Be kind to your users: use `rem`!**

## Styling the Entire Website (The `body` Tag)

If you want to change something for the whole website (like the main font or background color), the best selector to use is **`body`**, because _all_ your visible HTML content is inside of it!

```css
body {
  /* Set the font for everything inside the body tag */
  font-family: Arial, Helvetica, sans-serif;

  /* Using a Hex Code for a nice dark blue */
  background-color: #1e475b;

  /* Using a Named Color for the text */
  color: white;
}
```

> **💡 Secret Backup List:** For `font-family`, the browser is smart! It tries the first font (`Arial`). If the user’s computer doesn't have it, it moves to the next (`Helvetica`), and so on.

## The Flow of Style: Cascading

CSS stands for **Cascading** Style Sheets. "Cascading" means the rules fall down the sheet like a waterfall.

**The Golden Rule:** If you write the same rule twice, **the last rule read by the browser is the one that wins!**

```css
h1 {
  color: white; /* This color will be IGNORED */
}

h1 {
  color: blue; /* This color WINS because it is written last */
}
```

## The Box Model (Spacing is Everything)

Every single HTML element, from your `<h1>` to your `<img>`, is treated by the browser as its own **rectangular box**. Understanding this box is key to controlling layout.

![CSS Box Model Diagram](/images/css-box-model.png)

Think of your element as a **Gift Box**:

| Box Component |          What it is          |                                           How it works                                           |
| :-----------: | :--------------------------: | :----------------------------------------------------------------------------------------------: |
|  **Content**  |  The text or image itself.   |                                   The **Toy** inside the box.                                    |
|  **Padding**  |  Space _inside_ the border.  | The **Bubble Wrap** around the toy. (Adds room between the text and the edge of its background.) |
|  **Border**   | The line around the element. |                                  The **Cardboard Box** itself.                                   |
|  **Margin**   | Space _outside_ the border.  |                   The space between _your_ box and the next box on the shelf.                    |

#### Example: Adding Padding

By adding `padding` to your `<h1>`, you are adding "bubble wrap" that pushes the text away from the edge of its own background color.

```css
h1 {
  background-color: lightblue;
  padding: 20px; /* Adds 20 pixels of space on ALL 4 sides */
}
```
