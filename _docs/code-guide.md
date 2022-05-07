---
title: Coding Guide for MakeCode
permalink: /docs/code/
---

## Table of Contents
- [Understanding Blocks](#blocks)
  - [Events](#events)
  - [Loops](#loops)
  - [Logic](#logic)
  - [Variables](#variables)

## Understanding Blocks <a name="blocks"></a>
Blocks snap into each other to define the program that your Adafruit Circuit Playground Express will run. Blocks can be an event block (press buttons, shake the CPX, make a loud noise, etc.) or need to be snapped into an event to run. Blocks not snapped will appear translucent gray, and will not run.

There are multiple types of blocks in MakeCode, and the relevant blocks required for this curriculum will be covered in this guide.

| Type of Block | What It Does |
| ---: | --- |
| **events**  | Initiates groups of blocks to run. All runnable code is wrapped in event blocks.  |
| **loops**   | Runs the code inside repeatedly some number of times.  |
| **logic**   | Runs code based on whether a condition is true or false. |
| **variable**  | Stores information to be retrieved and used later in a program. |

### Events <a name="events"></a>
