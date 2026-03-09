---
layout: note.njk
title: Files & Folders
tags: wpc-d1-notes
order: 2
parentName: Day 1
---

## Intro to Computer Organization

When we operate and look at computing devices, it's easy get lost in all their complexity, however the starting blocks of all software are **folders** (or **directories**) and **files**.

A **file** is a collection of information and they're organized by specific file types. Different file types will hold specific and different information such as a written message, an image, a video, and even programs. Perhaps you can think of this as notes, homework, papers, and other documents you probably do for school.

A **folder** is how files are given further organization. Folders can store files, but also other folders to group together similar files. In a computer system this might be placing all of your photos in one specific folder, but even that can cluttered so maybe you want to group together all the vacation photos into a separate folder. You can think of this like organizing your school work by different subjects, like math and English, and if you're really organized, separating by different topics within the subject.

All computing devices will have files and folders. The file navigation will be slightly different depending on the operating system of the computer.

![Diagram of files and folders inside of a parent file](/images/file-system.png)

In the above image you can see a folder that contains 2 different types of files as well as another folder.

The 3 main common operating systems for computer systems are:

- Microsoft Windows
- macOS
- Linux

When working with computers you will most likely run into these 3 computers, so it's good be familiar with their inner workings.
In the workshops we will be working on either Windows or macOS as they are the most common operating systems.

### Windows File Explorer

<img class="img-small" src="/assets/images/tech/intro-to-web-dev/Microsoft_PowerToys-Logo_File_Explorer_Preview_02.svg" alt="Windows File Explorer Logo"/>

Windows uses File Explorer as their default file navigator. Usually it's pinned in the task bar at the bottom of the screen and when you open it, you should see an application like the diagram below.

![Screenshot of Windows File Explorer](/images/windows-file-explorer.png)

[For more info about File Explorer](https://support.microsoft.com/en-us/windows/file-explorer-in-windows-ef370130-1cca-9dc5-e0df-2f7416fe1cb1){target=blank}

### macOS File Navigation

<img class="img-small" src="/assets/images/tech/intro-to-web-dev/Finder_Icon_macOS_Tahoe.png" alt="Mac OS Finder Logo"/>

Mac uses the Finder, which is not only a file navigator but also launches other applications. You should be able to find Finder in the dock at the bottom of the screen.

![Screenshot of Mac Finder on version Big Sur](/images/finder.png)

[For more info about Finder](https://support.apple.com/en-ca/guide/mac-help/mchlp2605/mac){target=blank}

### File Paths

A file path is a way to specify the location of folders and files.

A file path for **macOS** or **Linux** might look like this:
**/home/username/Wattson/hello.txt**

In the above example we can see that folders are separated using the **forward slash ( / )** and the file names end with their type, in this case a text file.

With **Windows** the file path looks a little different, the same example above might look like this:
**C:\Users\Wattson\hello.txt**

The biggest differences being that Windows use a letter based drive as well as using the **backward slash ( \\ )** to separate folder names.

### File System Game

Let's put what we learnt to by playing the [File System Game](https://file-system-game.vercel.app/){target=blank}
