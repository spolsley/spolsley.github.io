---
layout: post
title:  "FrameFixer - Reducing Dropped Frames when Downsampling Video"
date:   2019-10-11
categories: 
excerpt: "I was recording an emulated game the other day, and I noticed that Quicktime captures at 60fps, even though the game only ran at 30fps.  Half of the frames were duplicates!  I thought it would be easy to downsample to 30fps, keeping just the original content, but I couldn't find any tool that did exactly what I wanted.  Ultimately, I wrote a small OpenCV-based program for the task."
---

Recently I was playing an old Mac game<small>[^1]</small> in [Sheepshaver](https://www.emaculation.com/doku.php/sheepshaver), capturing the video with Apple's Quicktime.  Quicktime records the screen at 60fps, even though the game was only running at 30fps.  This meant half the frames were duplicates... a waste of space.  Logically, it should be possible to toss out these duplicates and obtain a 30fps video consisting only of the original content, yet every downsampling tool I tried ended up with dropped frames!

<hr>

I ended up writing a small OpenCV-based program to process videos and adjust frames for minimizing loss from downsampling: **FrameFixer**.  Some details are in this post, and you'll find all the code plus a very detailed ReadMe on GitHub:

<center>
<font size="+2"><a href="https://github.com/spolsley/framefixer" target="_blank">Download FrameFixer on GitHub</a></font>
</center>

## The Problem

In the ideal case, each frame of 30fps content occurs exactly twice in a 60fps recording, and when the naive downsampler picks every other frame, there will be no loss.  The flaw in my logic was assuming Quicktime's capture buffer aligned perfectly with the emulator's display buffer.  When these buffers are out of sync, frames won't always appear twice.

Consider the following example.  If you simply select every other frame from the recording, you'll get Frames 1, 3, 5, and 7.  Notice that Frame 3 of the game would be lost.

![60fps video of 30fps content doesn't mean every frame is repeated exactly twice]({{ site.baseurl }}/posts/images/framefixer/sample.jpg)

I looked around for more a sophisticated downsampler to address this problem.  The [`mpdecimate` plug-in for ffmpeg](https://ffmpeg.org/ffmpeg-filters.html#mpdecimate) came close but introduced audio sync issues.  Nothing seemed exactly right.

## My Solution

I wrote a small OpenCV & C++ tool called **FrameFixer** to read through a video file, locate duplicate or at-risk frames, and adjust them to minimize loss.  It was surprisingly difficult to make the frame comparison metric; I needed one that could recognize duplicates despite minor frame variations while also measuring broad visual changes.  Ultimately, I used the standard deviation of the absolute difference.  With **FrameFixer**, the sample clip maintains Frame 3 of content.

![FrameFixer adjusts frames to minimize loss]({{ site.baseurl }}/posts/images/framefixer/restored_frame.jpg)

This tool doesn't actually perform downsampling, merely adjusts frame positioning to prepare for it.  If frame loss is unavoidable, those with the least visible changes will be the first to go.  Also, make sure to review the steps for copying audio and take a look at additional options.  You can find all the info you'll need at the [GitHub page](https://github.com/spolsley/framefixer).

While I've only used **FrameFixer** for my specific problem, I believe it should work to reduce noticeable frame loss in any downsampling task.

<br>

[^1]: <small>If you're curious, the game shown in the images is [Ferazel's Wand](https://en.wikipedia.org/wiki/Ferazel%27s_Wand), a Mac-exclusive fantasy platformer developed by Ambrosia Software around 20 years ago.  As an enthusiast of classic Mac games, I enjoyed quite a few of Ambrosia's offerings, and I even maintain a website with a bunch of related materials: [Cythera Guides](http://www.cytheraguides.com).</small>