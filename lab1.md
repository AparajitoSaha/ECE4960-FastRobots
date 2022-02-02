---
layout: default
---

## LAB 1: ARTEMIS

[Back to Home](./index.html)

This lab involved getting familiar with the Sparkfun Redboard Artemis Nano, the microcontroller used throughout this course. Through a series of basic examples, we understand the capabilities of the Artemis Nano and their applications to different robot tasks.

#### Software Installations
The Artemis Nano is compatible with the Arduino IDE software suite, which means that we can use Arduino-like syntax to perform functions related to the ports on the microcontroller. I used the instructions in the lab handout to configure the Arduino environment on my computer for interacting with the Artemis Nano, mainly through these following steps:
* Update the Arduino IDE to its latest version (I had an older version installed, now updated to v1.8.19)
* Add the Arduino Core for the Sparkfun Apollo3 (the processor onboard the Artemis Nano) by entering the custom link `https://raw.githubusercontent.com/sparkfun/Arduino_Apollo3/main/package_sparkfun_apollo3_index.json` in the Boards Manager URL
* Install the Sparkfun Apollo3 library through the Boards Manager, and select the Sparkfun Redboard Artemis Nano from the Boards dropdown menu - after this, we’re all set to plug in the cable to the Artemis Nano!

#### Example 1: Blink
The Blink sketch is the default example tested on every Arduino board, which turns on and off the onboard LED connected to pin 13 at 1 second intervals. On the Artemis Nano, the onboard LED is connected to pin 19, which can be accessed through the `LED_BUILTIN` environment variable. The video snippet below shows the LED blinking on and off as desired.

<iframe width="560" height="315" src="https://www.youtube.com/embed/DE4cjBMbxAs" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Example 2: Serial
We next test the serial connectivity sketch provided as part of the Apollo3 core example scripts. The sketch initializes the serial connection to a baud rate of 115200, and then echoes any input through the serial console back to the serial monitor after printing out some initial statements. The video snippet below shows the printed statements from the Artemis Nano on the serial monitor.

<iframe width="560" height="315" src="https://www.youtube.com/embed/wGPHTpmnUb8" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Example 3: Analog Read Temperature Sensor
The third test involved using the onboard Analog-to-Digital Converter to measure analog voltage to read in values associated with the board and the processor. In this case, we wanted to read the processor’s temperature while touching and blowing on the chip to increase the temperature. I modified the sample script to print out only the temperature change and slow down the rate at which the values were being printed in order to better observe the changing values. One issue I faced was trying to retrieve Fahrenheit values by using the “getTempInDegF()” builtin function - however, using this resulted in only “%f” being printed out on the serial monitor (which is the string argument passed for printing float values). While I was unable to resolve this issue, we can see the deviation in the raw ADC values from blowing on and touching the chip in the following video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IZnIipwHDN0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Example 4: PDM Microphone
The final example for this class is using the pulse density modulation (PDM) microphone example script to decipher sound frequencies. The sketch involved more technical understanding than the earlier examples - the key takeaway is that the PDM sampling frequency (46875 Hz) and the clock frequency (6MHz) are set by the code depending on the microcontroller, after which it samples the frequency of the sound and performs a fast fourier transform (FFT) to determine the loudest frequency (highest peak). The following video shows the results from whistling with the microphone near the source of sound.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Kqg8v-r3Xbg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

As a measure of accuracy, I used an online tone generator to create sounds of specific frequency (880 Hz) and observed the result produced by the Artemis Nano as shown in the following video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/nXmsR6uUBKY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
