---
layout: note.njk
title: HTML Fundamentals
tags: wpc-d1-notes
order: 4
parentName: Day 1
---

## The Core Concept: HTML is the structure

**HTML (HyperText Markup Language)** is the language we use to tell a web browser (like Chrome, Firefox, or Safari) what everything is.

And HTML does so by using **tags**.

- **Is it a main title?** ➡️ Use an **`<h1>`** tag.
- **Is it a normal paragraph?** ➡️ Use a **`<p>`** tag.
- **Is it a link to another site?** ➡️ Use an **`<a>`** tag.

### Key Rule: The Tag Sandwich

Most HTML elements are a "sandwich" with two pieces of bread (the tags) and the content in the middle.

| Opening Tag |     Content     | Closing Tag |
| :---------: | :-------------: | :---------: |
| **`<h1>`**  | You're Invited! | **`</h1>`** |

> **Notice the Slash (`/`):** The closing tag always has a forward slash (`/`). This tells the browser: "The section I labeled `h1` is now **finished**."

## Setting Up Your Foundation

When you create a new website, it always starts with the same foundational code.

### The Homepage Name Tag: `index.html`

When you type a website name (like _google.com_), the server automatically looks for a file named **`index.html`**. This is your website's **official landing page** or **homepage**.

### The Magic Starter Code (The Skeleton)

When you type **`!`** or **`html:5`** (and press enter) in VS Code, you get this structure. Don't worry about every line, just focus on the two main parts:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- 🧑 The HEAD (Hidden Info) -->
    <title>My Cool Event!</title>
  </head>
  <body>
    <!-- 🧍 The BODY (Visible Content) -->
    <h1>Welcome to My Site</h1>
  </body>
</html>
```

```js
function myFunc() {
  return true;
}
```

| Tag Name      | What it is       | What it does                                                                                                                                                     |
| ------------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`<head>`**  | **The Brain**    | Holds all the important **secret** information: the title that shows up in the browser tab, links to CSS files, etc. Nothing in the head is visible on the page. |
| **`<title>`** | **The Tab Name** | This is the name that appears in the little tab at the top of your web browser.                                                                                  |
| **`<body>`**  | **The Body**     | **Everything you want to see** on your actual website (text, images, links) goes between the `<body>` and `</body>` tags.                                        |

## Your Essential HTML Toolbox

You'll need a few tags to build your first page. Think of these as the main tools in your coding toolbox!

| Tag Name             | Description                    | Example                                                                        |
| -------------------- | ------------------------------ | ------------------------------------------------------------------------------ |
| **`<h1>` to `<h6>`** | **Headlines & Subtitles**      | `<h2>Event Details</h2>`                                                       |
| **`<p>`**            | **Paragraph**                  | Used for all the main blocks of text.                                          |
| **`<ul>` / `<li>`**  | **Unordered List / List Item** | Creates bullet points. (`<ol>` creates numbered lists).                        |
| **`<a>`**            | **Anchor Tag (Link)**          | Makes text clickable! You use the attribute `href` to tell it _where_ to go.   |
| **`<img>`**          | **Image Tag**                  | Used to place pictures. _It's a special tag that does NOT need a closing tag!_ |

---

### The Challenge: Structuring Your Event Site

Now it's your turn. Let's build a simple website for an **event** (a party, a game release, a concert, or even just a hangout).

### Step 1: Set the Title

Inside your **`<head>`** tags, change the text in your **`<title>`** tag to reflect your event.

### Step 2: Create the Main Title and Description

In the **`<body>`** of your page, use the following tags to set the main topic:

1.  Use an **`<h1>`** tag for the biggest, most important title (the name of your event).
2.  Use a **`<p>`** tag for a short description.

> **💡 The Discovery:** Why do you need **`<p>`** tags? Try typing two lines of text without them and see what the browser does! (Hint: HTML cares about structure, not just blank lines.)

### Step 3: Add Details as a List

You need to tell people the **When** and **Where**. Use a sub-title (**`<h2>`**) and an **Unordered List** (**`<ul>`**) to organize your event details.

**Challenge Goal:** Make a unordered list that includes at least three of these:

- Location
- Date and Time
- Dress Code
- What to Bring

```html
<!-- Example of what to build -->
<h2>Event Details</h2>
<ul>
  <li>Location: My House</li>
  <li>Date: Saturday, Dec 12</li>
  <li>...your other details here...</li>
</ul>
```

### Adding an Image

A website is boring without pictures! The **`<img>`** tag is unique because it's a **self-closing tag** (it doesn't need an **`</img>`**).

- **`src`**: The **source**, this is the link to the image you want to display.
- The link you want to add to your source can be a url link from a different site or it can be from an image that's in the project folder.
- **`alt`**: The **SUPER IMPORTANT** alternative text. If the picture can't load, or if a visually-impaired user is visiting your site, this text tells them what the picture was. **Always include `alt` text!**

```html
<!-- This link will display a random cat picture as a placeholder! -->
<img
  src="https://placekitten.com/200/300"
  alt="A cute cat placeholder image for the event"
/>
```

## The Finishing Touch: Favicons

Have you noticed the tiny logo next to the text in your browser tab? That is called a **Favicon** (short for Favorites Icon). It’s like the profile picture for your website.

Since this isn't content that appears _on_ the page, but rather information _about_ the page, it goes inside the **`<head>`** (The Brain).

**How to add it:**
You use the **`<link>`** tag. Unlike the anchor tag **`<a>`**, the link tag is used to connect your HTML file to external resources (like icons or CSS files).

You can find images for favicons at sites like [this](https://www.flaticon.com/)

```html
<head>
  <title>My Cool Event</title>
  <!-- The relationship (rel) is an icon, the href is the file location -->
  <link rel="icon" href="my-logo.png" />
</head>
```

> **Pro Tip:** You can use `.png` or `.ico` files for this. If you don't have a small logo ready, you can use an emoji!
>
> _Code for local Favicon:_
> `<link rel="icon" type="images/x-icon" href="assets/christmas-wreath.png">`

## Leaving Notes: HTML Comments

Sometimes you want to leave a note for yourself (or your instructor) inside the code, but you don't want that text to show up on the actual website. These are called **Comments**.

The browser sees the comment symbols and completely ignores everything inside them.

**The Syntax:**
It starts with a less-than bang dash dash `<!--` and ends with a dash dash greater-than `-->`.

```html
<body>
  <h1>My Event</h1>

  <!-- TODO: Change this color later -->
  <p>Welcome to the party!</p>

  <!-- This section below is for the RSVP link -->
  <a href="...">RSVP</a>
</body>
```

|   Symbol   | Meaning                                                      |
| :--------: | :----------------------------------------------------------- |
| **`<!--`** | **Start of Comment** (Browser: "I will stop reading now")    |
| **`-->`**  | **End of Comment** (Browser: "Okay, I'm reading code again") |

---

## Quick Concept: Attributes

You might have noticed a pattern with the **`<a>`**, **`<img>`**, and **`<link>`** tags. They all have extra bits of text inside the opening tag, like **`href="..."`** or **`src="..."`**.

These are called **Attributes**.

- Attributes provide **additional information** about an element.
- They always come in pairs: **`Name="Value"`**.
- They always live in the **Opening Tag**.

|     Tag     |  Attribute  |          Value           | Translation                                            |
| :---------: | :---------: | :----------------------: | :----------------------------------------------------- |
|  **`<a>`**  | **`href`**  | **`https://google.com`** | "I am a link, and **my destination is Google**."       |
| **`<img>`** |  **`src`**  |      **`cat.jpg`**       | "I am an image, and **my file source is cat.jpg**."    |
|  **`<p>`**  | **`class`** |      **`big-text`**      | "I am a paragraph, and **my style name is big-text**." |
