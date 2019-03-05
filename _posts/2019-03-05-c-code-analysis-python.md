---
layout: post
title:  "C++ Code Analysis with Python"
date:   2019-03-05
categories: 
---

I was using [Mimir](https://www.mimirhq.com) in C++ labs last semester, and it was a great tool to check code correctness.  I still found myself spending a lot of time reviewing code, so in an attempt to automate some of the grading, I looked into cpplint and other style checkers.  They didn't do quite what I wanted, so I decided to write a few simple Python scripts to do static code analysis.

The scripts have limited applicability -- examining repetition, indentation, expression length, and a couple other things.  However, they were only needed for a few points regarding style and code layout, so as a means of automating that grading, they were really useful.  In case anyone else is looking for some basic code analysis that linters don't provide, I've shared my scripts in hopes others find them useful:

[Github - C++ Static Analysis Scripts](https://github.com/spolsley/C-Static-Analysis-Scripts)

There's a lot more specific information provided in the readme, so be sure to take a look on Github if this looks interesting to you.