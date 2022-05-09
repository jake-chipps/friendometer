---
title: Technical Guide
permalink: /docs/tech/
---
## Table of Contents
- [1 MakeCode](#makecode)
  - [Saving and Sharing Projects](#shareproject)
  - [Connecting the Circuit Playground Express to MakeCode](#cpx-makecode)
  - [Managing Projects](#projects)
- [2 Circuits](#circuits)
  - [Tips for Using Copper Tape](#copper)
  - [Tips for Using LEDs](#led)
- [3 Circuit Playground Express](#cpx)
  - [Input/Output Pins](#pins)
  - [NeoPixels](#neopixels)
  - [Sensors](#sensors)
  - [Troubleshooting the CPX](#troubleshoot)

## 1 MakeCode <a name="makecode"></a>
[MakeCode](https://makecode.adafruit.com/) is a free, web-based coding platform
that uses drag-and-drop blocks to scaffold learning. Students will create accounts
in MakeCode and can save their projects. Projects can be duplicated, edited,
and shared with others. After coding a project, students can download their code
from MakeCode into the Circuit Playground Express to run on their projects.

### Saving and Sharing Projects <a name="shareproject"></a>
There are no accounts in MakeCode, which means that saved projects are not attached to a student's individual account. But this does not mean that students cannot save and share their projects.

When inside of a project on MakeCode, there is a button in the top left corner of the browser window called "Share." Clicking "Share" will prompt a window that asks the user to name and publish their project. In order to save and share a project for later, a project must first be named and published. Any modifications made to the project after it is published will NOT be reflected in the shared link so if a student makes edits to a project after they have named and shared it, the project must be named and published again and they will get a different link to a new project. This allows us to create versions of projects (if you want students to learn about version control).

When students share and publish their code, they will get a link to that particular
version of their project. It is strongly recommended that students copy and paste
that link into a file that is compatible with the learning management system used
by the teacher. For example, students can create a database of projects links in
a Google Doc, text file, word processing file, etc. Students should add information
for each link such as the project name, date, changes made, etc.

### Connecting the Circuit PlayGround Express to MakeCode <a name="cpx-makecode"></a>
Connecting the Circuit Playground Express (CPX) to MakeCode has been simplified
compared to previous versions of the Circuit Playground such as the Classic.

To connect, follow these steps:
1. Open [MakeCode](https://makecode.adafruit.com/) in Chrome and open or create a new project.
2. Connect the CPX to the computer via USB.
3. Press the *reset* button on the CPX to enter Bootloader Mode. The NeoPixels should turn red briefly followed by contiuous green. If the NeoPixels stay red, your operating system is still installing drivers, and you may need to wait a minute. If the red continues, try using a different USB; the connection may be bad.
4. Click on the gear in the top right, and click "Pair Device."
5. You should see a device called CPLAYEXPRESS or similar. Click on the device name and click "connect."
6. To download the code onto the CPX, click "Download" below the simulator on the left.

### Managing Projects <a name="projects"></a>
To create a new project, go the MakeCode home screen, and click "New Project."

To share a project, click on "share" in the top left of the project. You will need
to name the project and then click "Publish Project." Copy the link to the project,
and store that link in a file with information about the project (see [Saving and Sharing Projects](#shareproject)).

To edit a project, you need the shared link to that project. Open the link, and
then click "edit" at the top. This is a duplicated project, and when shared, will
yield a different link from the original. This allows us to create versions of our
projects.

## 2 Circuits <a name="circuits"></a>
The materials we use to create circuits in this curriculum include:
- **copper tape** as an insulator
- **LEDs** for light patterns
- **Circuit Playground Express** as a power source with computational functionality.

### Tips for Using Copper Tape <a name="copper"></a>
<span class="todo">Write tips and tricks for using the copper tape</span>

### Tips for Using LEDs <a name="led"></a>
<span class="todo">Write some LED "insider knowledge"</span>

## 3 Circuit Playground Express <a name="cpx"></a>
The Circuit Playground Express (CPX) is a programmable microcontroller that is used as an introduction to computing systems. For this curriculum, we will be using the following features built into the CPX:
- 8 alligator-clip friendly input/output **pins**
- 5 mini **NeoPixels**
- 1 sound **sensor**

### Input/Output Pins <a name="pins"></a>
<span class="todo">Explanation of the differences between each of the pins and how we use them</span>

<span class="todo">Explanation of pins we should not use and why (include symbols for warnings)</span>

### NeoPixels <a name="neopixels"></a>
<span class="todo">Explanation of the NeoPixels: locations, colors, brightness</span>

### Sensors <a name="sensors"></a>
<span class="todo">Explanation of the sensors present on the CPX and their referenced pins</span>

### Troubleshooting the CPX <a name="troubleshoot"></a>
<span class="todo">Things that can go wrong and how to fix it</span>
