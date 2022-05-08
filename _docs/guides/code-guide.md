---
title: Coding Guide
permalink: /docs/code/
---

## Table of Contents
- [1 Understanding Blocks](#blocks)
  - [Events](#events)
  - [Loops](#loops)
  - [Logic](#logic)
  - [Variables](#variables)
- [2 Programming Output Pins (LEDs)](#programpins)
- [3 Writing and Using Functions](#functions)
- [4 Programming the NeoPixels](#programneo)
- [5 Programming Input Pins (Sensors)](#programsensors)
  - [Getting the Sensor Value](#getsensor)
  - [Writing to the Console](#console)
  - [Running Code Based on the Sensor Value](#usesensor)

## 1 Understanding Blocks <a name="blocks"></a>
In [MakeCode](https://makecode.adafruit.com/), Blocks snap into each other to define the program that your Adafruit Circuit Playground Express will run. Blocks can be an event block (press buttons, shake the CPX, make a loud noise, etc.) or need to be snapped into an event to run. Blocks not snapped will appear translucent gray, and will not run.

MakeCode can handle multiple groupings of blocks. You do not need to put all of your code in a single group of blocks.

There are multiple types of blocks in MakeCode, and the relevant blocks required for this curriculum will be covered in this guide. For more information about specific blocks beyond the scope of this curriculum, [MakeCode offers a guide](https://makecode.adafruit.com/blocks) for all of the blocks within the programming interface.

| Type of Block | What It Does |
| ---: | --- |
| **events**  | Initiates groups of blocks to run. All runnable code is wrapped in either event blocks, functions, or the forever loop.  |
| **loops**   | Runs the code inside repeatedly some number of times.  |
| **logic**   | Runs code based on whether a condition is true or false. |
| **variable**  | Stores information to be retrieved and used later in a program. |

### Events <a name="events"></a>
Events allow code to run when a particular pattern is detected. For example, the *on shake* event runs code when a shaking gesture is detected by the accelerometer. You can mix and match events from different sensors in the same program but each event type can only be registered once.

The only event block this curriculum uses is the *on start* block. *on start* is an event that runs when the program starts.

|   Block   | What It Does    |
| ---: | --- |
| *on start* | A special event that runs when the program starts, before any other event. Use this event to initialize your program. This event does not need to be used in every program - we tend to use it if we have variables that need to be initialized. |

### Loops <a name="loops"></a>
There are two loop blocks this curriculum uses: the *forever* block and the *pause* block.

|   Block   | What It Does    |
| ---: | --- |
| *forever* | The code you have in a forever loop will run and keep repeating itself the whole time your program is active. Code in other parts of your program won’t stop while your forever loop is running. This includes other forever loops.  |
| *pause [NUMBER] ms*  | Pause a part of the program for some number of milliseconds. When code in a block comes to a pause, it will wait the amount of time you tell it to.  |

### Logic <a name="logic"></a>
Logic blocks control the flow of your program. While groups of blocks normally run sequentially from top to bottom, you can redirect the code that runs next by checking if a condition is true.

There are two logic blocks this curriculum uses: the *if(BOOLEAN)...else...* block and the *boolean* block.

|   Block   | What It Does    |
| ---: | --- |
| *if(BOOLEAN)...else...* | Run code depending on whether a boolean condition is true or false. The code inside the if block only runs when the condition block is true. To create the Boolean condition, you can compare variables to values or variables to variables. If you want some other code to run when the opposite condition is true, you put it in an additional block area called else and tell the code what to do else the condition is not true.  |
| *boolean*  | A Boolean has one of two possible values: true or false. Boolean (logical) operators (and, or, not) take Boolean inputs and make another Boolean value. This block represents Boolean values (true/false), which can be dragged any place a Boolean value is expected (such as an *if(BOOLEAN)...else...* block). |

### Variables <a name="variables"></a>
When we need to store information (like the current value of a sensor), we need to store that value within a variable, which is physically allocated on the memory of the Circuit Playground Express when the code runs. Data stored in a computer or microcontroller (like the CPX) has an address in the memory. When a computer accesses a variable, it checks the memory address where the variable is stored. Memory addresses are not easy for humans to remember. So we can point to a particular memory address by naming a variable. Then, instead of knowing the address of where the data is stored, we can just call the name of the variable. The computer will link the variable name and the address for us.

In MakeCode, to store a value inside of a variable, we need to create the variable in the interface and then use the *set* block in the variables menu.

|   Block   | What It Does    |
| ---: | --- |
| *set [NAME] to [VALUE]* | Assign (set) a variable’s value. |
| *[NAME]* | Access (get) a variable's value. When we want to check the current state of a variable, we need to get it first using the variable's name. |

For example, if I want to set a variable called *age* to 11, I would write
```
set age to 11
```
and if I want to check if the person can drive yet, I would write
```
if(age > 15)
  You can drive
else
  You cannot drive
```
In [4-2 (Encryption)](../4-2/), students will create variables called ON and OFF to store the color they will use for their NeoPixels (see [Programming the NeoPixels](#programneo)). One example of student code might look as follows
```
set ON to GREEN
set OFF to RED
```

## 2 Programming Output Pins (LEDs)<a name="programpins"></a>
The LEDs on the Ledger Art Project are connected (by copper tape and alligator clips) to output pins on the Circuit Playground Express. As described in the [Technical Guide](../tech/), the pins that can be used to connect to LEDs are: A0, A1, A2, A3, A4, A5, A6, and A7.

For example, if we have connected an LED to pin A7, then we need to be able to send messages to the pin to allow the flow of current to turn on the LED or block the current and turn the LED off. We do this using a block called *digital write*. The word **digital** means that the value we send to the pin is a binary value; that is, it has one of two values (ON/OFF, TRUE/FALSE, LOW/HIGH). Either the current will flow or it will be blocked, there is no middle ground.

|   Block   | What It Does    |
| ---: | --- |
| *digital write pin [PIN] to {LOW/HIGH}* | Write a value of false or true to a pin. In the case of an LED connected to the pin, false means that the LED connected to the pin is turned off. In a similar way, true means something the connected LED is on. In PIN, we specify which pin we want do write to (e.g. A7). LOW means off (false) and HIGH means on (true). The value from the last digital write stays at the pin until another digital write happens. |

For example, if I want the LED connected to pin A7 to be OFF, then I would write
```
digital write pin A7 to LOW
```
and if I want the LED to be ON, I would write
```
digital write pin A7 to HIGH
```

## 3 Writing and Using Functions <a name="functions"></a>
In [3-2 (Design the Ledger Art Project)](../3-2/) and [3-3 (Program the Ledger Art Project)](../3-3/) students will design and program light patterns for their Ledger Art Projects, respectively. A simple light pattern for a single LED might entail the sequence
```
Turn LED on
Pause 1 second
Turn LED off
Pause 1 second
```
This sequence requires four lines of code that we can define inside of a function. A function is a block of code where we can snap multiple blocks inside. For example, I might call the function above "Blink." Then, when I call the Blink function, those four lines of code will run. Blink becomes a substitute phrase for the entire sequence of code.

To create a function, go to the functions menu, and click "make a function." Name the function using a descriptive name for whatever the code is going to do. The *function* block with your personalized name will appear in the workspace. Drag the blocks you need to complete that function inside.

Once your function is defined and has code, we need to call the function. To call your function, go back into the functions menu and drag the *call* block wherever you want the function to run.

|   Block   | What It Does    |
| ---: | --- |
| *function [NAME]* | Defines a sequence of blocks that will run when the function is called. |
| *call [NAME]*   | Runs the sequence as defined by the function.  |

For example, the code for the Blink sequence would look as follows
```
function Blink:
  digital write pin A7 to HIGH
  pause 1000
  digital write pin A7 to LOW
  pause 1000

forever:
  call Blink
```

## 4 Programming the NeoPixels <a name="programneo"></a>
The NeoPixels are the ten LEDs circling the Circuit Playground Express. NeoPixels differ from the individual LEDs in that they can change color and brightness. For this reason, before setting the state of each LED, we need to set their color and brightness. We can use a predefined color or create our own using the *red green blue* block.

|   Block   | What It Does    |
| ---: | --- |
| *set all pixels to [COLOR]* | Sets the color of all NeoPixels to the specified color. |
| *set brightness to [NUMBER]*   | Sets the brightness of all NeoPixels to the specified brightness. NUMBER is an integer from 0 to 255.  |
| *red [NUMBER] green [NUMBER] blue [NUMBER]* | Creates a color with the amount of red, green, and blue specified. NUMBER is an integer from 0 to 255.  |

When we set the color and brightness of the NeoPixels, we want to do this right when the code starts. For this reason, we need the *on start* block. Here is what it might look like to initialize the NeoPixels to the color cyan and brightness 255 (full brightness)
```
on start:
  set cyan to red 0 green 255 blue 255
  set all pixels to cyan
  set brightness to 255
```
Now that we have initialized the NeoPixels, we can change their states. There are ten NeoPixels. How do we tell the CPX which one we want to set? Each NeoPixel has a position from 0 to 9. We need to specify the position of the NeoPixel and the state we want that NeoPixel to have.

|   Block   | What It Does    |
| ---: | --- |
| *set pixel color at [POSITION] to [COLOR]* | Sets the color of the NeoPixel at the specified position to the specified color. |

If I want the NeoPixels to alternate between RED and BLUE, I might write the following code:
```
on start:
  set brightness to 255
forever:
  set pixel color at 0 to RED
  set pixel color at 1 to BLUE
  set pixel color at 2 to RED
  set pixel color at 3 to BLUE
  set pixel color at 4 to RED
  set pixel color at 5 to BLUE
  set pixel color at 6 to RED
  set pixel color at 7 to BLUE
  set pixel color at 8 to RED
  set pixel color at 9 to BLUE
```

## 5 Programming Input Pins (Sensors) <a name="programsensors"></a>
In [5-2 (Human-Computer Interaction)](../5-2/), students use the sound sensor (microphone) in order to activate the light patterns on their Ledger Art Projects by telling their stories. To do this, we need to:
- access the current sound level read by the microphone on the Circuit Playground Express,
- output the current value of the sound level so that we, the programmer, know what is happening, and then
- run some code based on the value of the sound sensor.

Each of these three sequences will be explored here.

### Getting the Sensor Value <a name="getsensor"></a>
MakeCode has made it very easy to access the sound level of the CPX's microphone. In input, there is a block called *sound level* which stores the current sound level of the microphone. The value of this variable is constantly changing and represents the current value of sound as computed by the microphone.

|   Block   | What It Does    |
| ---: | --- |
| *sound level* | Stores the level of sound "heard" by the microphone. Represents a number between 0 (quiet) and 255 (loud). The value stored is always changing. |

### Writing to the Console <a name="console"></a>
Now that we have the amount of sound heard by the microphone, we can print it out so that we as humans can see what it is. In the console menu, there is a block called *console log*. The *sound level* block can be dragged inside the white space of the *console log* block to print out the current value of the variable in the console. To access the console in MakeCode, simply click "Show Console Simulator" directly below the CPX simulator on the left side of the screen. The code should look as follows:
```
forever:
  console log(sound level)
```
In the console, you should now see various numbers between 0 and 255 descending.

### Running Code Based on the Sensor Value <a name="usesensor"></a>
Now that we can access the sound level of the microphone and see what the current value of the sound level is, we are ready to use it in our program to make decisions. If I use the console log to determine that when I tell my story, the value 180 is enough to catch what I am saying without also including background noises, then I would write the following code:
```
forever:
  console log(sound level)
  if(sound level > 180)
    call Blink
  else
    call Off
```
It is important that if the sound level is 180 or less, we turn off the LEDs. If we use the *digital write* block to turn an LED on, that LED will stay on until we turn it off using *digital write* again. In the code above, without the else statement, once the light pattern starts, it would never stop. And we want the light pattern to stop when the speaker is not speaking.
