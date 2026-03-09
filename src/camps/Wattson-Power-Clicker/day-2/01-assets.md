---
layout: note.njk
title: Assets Management
tags: wpc-d2-notes
order: 1
parentName: Day 2
---

## What are Assets?

In web development, **Assets** are the files that make your website look and sound unique. These include **images**, **videos**, **fonts**, and **audio files**. While code provides the structure and logic, assets provide the _personality_.

For our Idle Clicker game, the most important asset is your **Mascot**. This is the main button the player will click thousands of times!

In our example version, we use **Wattson** (the electric bolt) as our mascot because our theme is generating electricity. For your game, you need to decide on a **Theme**:

- **Cookie Clicker:** Your mascot is a Cookie.
- **Monster Slayer:** Your mascot is a Hero.
- **Space Miner:** Your mascot is an Asteroid.

You can search for pre-made assets in the `assets/` folder of the [Starter Code Github Repo](https://github.com/Science-Alive/Clicker-Game-Starter){target=blank}, or you can create your own.

## Image Formats: PNG vs. JPEG vs. SVG

Not all images are created equal. In web development, we primarily use three formats. Choosing the right one is important for how your game looks and how fast it loads.

### 1. JPEG (Joint Photographic Experts Group)

- **Best for:** Photographs, complex scenes, and background images.
- **Pros:** Small file size for big photos.
- **Cons:** **No transparency.** A JPEG always has a rectangular box behind it (usually white or black).
- **Use in Game:** Use this for your **Background Image**.

### 2. PNG (Portable Network Graphics)

- **Best for:** Logos, icons, and game sprites (like our Mascot).
- **Pros:** **Supports Transparency.** This allows us to have a cookie that is round, without a white square box around the corners. It is like a sticker on a clear sheet of plastic.
- **Cons:** File sizes can get big if the image is huge.
- **Use in Game:** Use this for your **Mascot** and **Shop Icons**.

### 3. SVG (Scalable Vector Graphics)

- **Best for:** Simple icons and logos.
- **Pros:** **Infinite Scaling.** You can make an SVG as big as a building and it will never look blurry or pixelated because it is made of math, not pixels.
- **Cons:** Cannot handle complex details like a photograph.

**Verdict:** For our clicker button, we will use **PNG** so our mascot can have a transparent background and look like a floating object.

## Making your Own Mascot

If you want to flex your creative muscles, you can use a free tool called [Piskel](https://www.piskelapp.com/p/create/sprite/){target=blank} to draw your own Pixel Art mascot.

![Screenshot of Piskel site](/images/piskel-overview.png)

### Steps to Create:

1.  **Draw:** Use the tools on the left (Pen, Paint Bucket) to draw your character.
2.  **Center It:** Keep your drawing in the middle of the canvas. This makes it easier to position in your game later.
3.  **Check Transparency:** Make sure you leave the background **checkered** (grey and dark grey squares). Do not paint the background white! The checkered pattern means "Invisible."

### Exporting (Crucial Step!)

Pixel art is usually tiny (32x32 pixels). If you download it at that size, it will be too small to see!

1.  Click the **Export** button (the picture of the mountain/sun on the right).
2.  Look for the **Scale** slider. Slide it up to roughly **10x** (or roughly 300px resolution).
3.  Click **Download PNG**.

![Screenshot of Piskel export options](/images/piskel-export.png)

## Adding the Asset to Your Game

Once you have your file (e.g., `my-dragon.png`), follow these steps to put it in the game:

1.  **Move the File:** Drag the image from your `Downloads` folder into your project's `assets/` folder.
2.  **Rename It:** Give it a simple, lowercase name with no spaces (e.g., `my-dragon.png` instead of `My Cool Dragon (1).png`).
3.  **Update CSS:** Open your `style.css` file. Look for the rule controlling your main button (usually `.click-btn` or `#clicker`) and update the `background-image` property.

```css
.click-btn {
  /* ... other styles ... */

  /* Link to your new image */
  background-image: url("assets/my-dragon.png");
}
```
