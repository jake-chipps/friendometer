---
title: Storytelling Project Guide
permalink: /docs/storytellingguide/
---

## Table of Contents

- [1 Overview](#overview)
- [2 Data Collection](#data)
- [3 Program](#program)

## 1 Overview <a name="overview"></a>
After section four, students will have created their Ledger Art Projects
and added an encrypted message on top of their visual narratives during the Encryption
Project. In [5-2 (Human-Computer Interaction)](../5-2/),
students will add the final addition to their computational artifact: initiating
their light patterns with their voices. Students will add code so that when they
tell their story, the project will light up, and when they are not talking, the
LEDs will not turn on.

This guide will add to the narrative started in the [Ledger Art Project Guide](../ledgerguide/)
and the [Encryption Project Guide](../encryptionguide/).

## 2 Data Collection <a name="data"></a>
In order to activate my Ledger Art Project with my voice, I needed to use the
microphone on the Circuit Playground Express. The microphone is a sensor that
"hears" the loudness of sound entering the sensor. MakeCode stores the readings
from the microphone in a variable called *sound level*. *sound level* is an integer
from 0 (quiet) to 255 (loud).

I considered some of the questions I had before beginning:
- What is the *sound level* of me telling a story?
  - Does *sound level* change while I tell a story or is *sound level* one value throughout?
- Does the distance of the Circuit Playground Express from my mouth affect *sound level*?
- Does environment affect *sound level*?
- What if someone else wants to use my projec? Will someone else have the same *sound level* as me?

In order to answer these questions, I had to collect data. For the purposes of this
project, I decided to simplify my inquiry and focus on two variables:
1. Distance between the CPX and the speaker's mouth
2. The person speaking

I hypothesized that while telling a story, *sound level* was probably not going to
remain constant; *sound level* would most likely be a range of values, and that range
might change based on either the distance away from the speaker's mouth as well as
who is speaking. Since a range can be defined by its minimum and maximum values,
I decided to collect the lowest and highest values of *sound sensor* at various
distances and from various speakers. Because everyone speaks at different volumes
in different situations, I decided to tell the paricipants to tell a story as if
they were in a classroom before class begins; that is, speak at a volume as if you
are speaking to someone in the near area (1-5 seats away) in a classroom sized room.

I wrote some code that would print out the current *sound level* to the console.

![printing the sound level to the console](../guides/guide-resources/sto-print-sound.png)

I collected data from my family and friends.

| Participant     |    Close: Lowest    |     Close: Highest    |     Average: Lowest    |     Average: Highest    |     Far: Lowest    |     Far: Highest    |
|-----------------|---------------------|-----------------------|------------------------|-------------------------|--------------------|---------------------|
|     Me          |     45              |     187               |     41                 |     153                 |     45             |     116             |
|     Alex        |     97              |     178               |     95                 |     163                 |     96             |     125             |
|     Jamie       |     51              |     155               |     51                 |     143                 |     51             |     120             |
|     Fernanda    |     53              |     192               |     53                 |     179                 |     52             |     154             |
|     Sue         |     45              |     185               |     42                 |     169                 |     45             |     122             |

## 3 Program <a name="program"></a>
