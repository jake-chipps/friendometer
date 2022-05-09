---
title: Encryption Project Guide
permalink: /docs/encryptionguide/
---

## Table of Contents
- [1 Overview](#overview)
- [2 Plan](#plan)
- [3 Program](#program)

## 1 Overview <a name="overview"></a>
By the end of section three, students have constructed the Ledger Art Project.
In lesson [4-1 (Binary)](../4-1/), students learn binary and develop a communication
protocol that maps the letters of the alphabet to decimal and then binary. In
lesson [4-2 (Encryption)](../4-2/), students use their binary communication
protocol to create an encryption technique and add an encrypted message on their
Ledger Art Project.

The Encryption Project is from [4-2 (Encryption)](../4-2/), and uses five of the
NeoPixels on the Circuit Playground Express to represent a 5-bit binary number.
This guide will build on the Ledger Art Project described in the
[Ledger Art Project Guide](../ledgerguide/), and will be written in the first
person to make visible the design and computational decisions made in this
individual project.

## 2 Plan <a name="plan"></a>
In order to create a 5-bit encryption for my message, I first needed to map the
letters of the alphabet to decimal numbers, as described in [4-1 (Binary)](../4-1/).
I decided to make *A = 1*, *B = 2*, *C = 3*, ... , *Z = 26*.

I then needed a message to send. Since my Ledger Art Project is build around the
idea of being in nature, I chose **nature** as the message I wanted to send using
the NeoPixels on the Circuit Playground Express.

Using the NeoPixel guide in [4-1 (Binary)](../4-1/),

![binary representation on the cpx](../resources/images/4-2_binary-representation-cpx.png)

I then [storyboarded the code](../guides/guide-resources/enc-4-2_program-name.pdf)
using the student handout from [4-2 (Encryption)](../4-2/) to make my message:

|     Letter    |     Decimal    |     Binary    |     NeoPixel Pin State                              |
|--------------:|---------------:|:-------------:|-----------------------------------------------------|
|     N         |     14         |     01110     |     0 OFF     1 ON     2 ON     3 ON     4 OFF      |
|     A         |     1          |     00001     |     0 OFF     1 OFF     2 OFF     3 OFF     4 ON    |
|     T         |     20         |     10100     |     0 ON     1 OFF     2 ON     3 OFF     4 OFF     |
|     U         |     21         |     10101     |     0 ON     1 OFF     2 ON     3 OFF     4 ON      |
|     R         |     18         |     10010     |     0 ON     1 OFF     2 OFF     3 ON     4 OFF     |
|     E         |     5          |     00101     |     0 OFF     1 OFF     2 ON     3 OFF     4 ON     |

I was now ready to begin coding my project.

## 3 Program <a name="program"></a>
