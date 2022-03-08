---
layout: default
---

## LAB 5: OPEN LOOP CONTROL

[Back to Home](./index.html)

This lab integrates the final hardware element for our robot - the motor drivers. It is necessary to understand how the motor drivers enable control of the motors, particularly given their high current consumption for driving the car at fast speeds. Later, I demonstrate open loop control of the car, by making it execute some given tasks such as driving in a straight line and turning for fixed amounts of time. 

### Prelab

By parallel coupling the input of output channels of each motor driver, we can increase the average current delivered to the motor without overheating the chip on the driver. For this reason, we use one motor driver for each motor on the robot, shorting the AIN1 and BIN1 pins together, AIN2 and BIN2 pins together, AOUT1 and BOUT1 pins together, and AOUT2 and BOUT2 pins together. In addition, we use the 850mAh battery to power the motors (so that we can test the car for longer), for which we connect the VIN of both motor drivers to the red lead of the battery connector. The GND of both motor drivers is connected to the black lead, which is additionally connected to one of the GND pins on the Artemis to provide a common ground signal for the motor PWM. 

We need 4 pins for writing analog signals to the motor drivers - I chose pins 11, 12, 13, and 14 since all these pins are PWM enabled and on the same side of the Artemis Nano, minimizing wire routing concerns. We want to power the Artemis and the motor drivers from different batteries in order to ensure that we can test the robot for longer and not be concerned by electromagnetic interference from the motors.

The hardware setup for my robot is shown in the image below:

### Task 1

Considering we are using an 850 mAh LiPo battery at 3.7V, we can assume that the motor drivers will need to operate at a level of between 3.2 and 4.2 volts (with 3.3V being the voltage level of the high PWM signal from the Artemis). By hooking up an external power supply and supplying a PWM output from the Artemis, I noticed that dropping below 3V starts to distort the PWM signal. A current level below 0.5A has the same effect.

### Task 2

I use an AnalogWrite value of 50 initially, seeing the following output from the coupled output of the motor driver. Channel 1 contains the actual PWM signal from the Artemis, while Channel 2 contains the resultant output from the motor drivers.

I then increase the value to 150 to see the following result (with similar channel configuration).

### Task 3

The below image shows the robot taken apart (*evil scientist noises*).

### Task 4

I used the datasheet (linked here) to run the motor forward for 3 seconds with a PWM value of 60, stop the motor for 3 seconds, run the motor backward for 3 seconds with a PWM value of 60 and then stop the motor again. I put in a while(1) after the second stop to ensure that I don’t continue running this code over and over again (relevant for the battery installed in the next task). The video below demonstrates this result.

### Task 5

I use the same code as the previous task, and hook up the motor drivers to the battery leads on the robot. The video below demonstrates the result.

### Task 6

Once again, I used the same code (except the pin numbers, which were changed appropriately) and saw the following result.

### Task 7

I managed to install everything inside the car chassis. My wire lengths were a little long (since I wanted to try different installations), so I had to loop the wires to ensure they fit. I tried to keep wires away from the motors to ensure that I could minimize EMI noise in my signals.

Placed on a hardwood floor, it turns out that a PWM value lower than 30 means that the motor does not turn at all. So PWM values from 0 to 30 form the deadband of the motors. 

Without a calibration filter, the motors do not drive the robot completely straight even over a 2 meter distance. I had to calibrate the left motor to a factor of xx as compared to the right. The video shows the calibrated motor operation for the robot traveling over a straight line.

Finally, I established open loop control by driving the robot forward for 5 seconds, turning left for 0.25 seconds, turning right for 0.25 seconds and then driving backward. I used the following code to set up the individual driving directions, and called the functions in a loop to see the results in the given video
