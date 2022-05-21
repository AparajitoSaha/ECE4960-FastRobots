<head>
		<title>ECE 4960 - Fast Robots, Aparajito Saha</title>
		<link rel="shortcut icon" type="image/png" href="./images/fastrobot.png">
        	<link rel="icon" type="image/png" href="./images/fastrobot.png">
</head>

## Introduction
This webpage documents my progress through ECE 4960: Design and Implementation of Fast Robots in its Spring 2022 offering at Cornell University! Each of the labs below demonstrate incremental development of the robotic platform in this course, starting from microcontroller and robot characterization up to complex planning and control execution tasks.

[LAB 1: ARTEMIS](./lab1.html)

Lab 1 covers the usage of the Artemis Nano microcontroller through a series of basic examples illustrating the various abilities of the board.

[LAB 2: BLUETOOTH](./lab2.html)

Lab 2 walks through Bluetooth communication with the Artemis Nano by testing and developing communication characteristics with the microcontroller.

[LAB 3: SENSORS](./lab3.html)

Lab 3 involves setting up the time of flight sensors and inertial measurement unit with the Artemis Nano and investigating their functionality.

[LAB 4: CHARACTERIZE THE CAR](./lab4.html)

Lab 4 allows us to characterize the physical parameters of the car that will be used as our robot, and studies the performance of relevant aspects of the car with remote control.


[LAB 5: OPEN LOOP CONTROL](./lab5.html)

Lab 5 requires us to factor in the motor drivers to our hardware setup and mount all the hardware on the robot before trying some basic open loop control commands.

[LAB 6: CLOSED LOOP CONTROL](./lab6.html)

Lab 6 starts a 3 part lab on stunt execution, focusing on closed loop PID control using sensor values dependent on the desired task.

[LAB 7: KALMAN FILTER](./lab7.html)

Lab 7 develops the Kalman Filter, which is used to improve the state estimation of the robot obtained from the ToF sensor for quicker stunt execution.

[LAB 8: STUNTS!](./lab8.html)

Lab 8 ends the 3 part sequence culminating in stunt execution, with the robot performing a closed loop 180 degree drift as well as a repeatable open loop stunt.

[LAB 9: MAPPING](./lab9.html)

Lab 9 starts the second sequence of assignments by making the robot map a static environment that will ultimately be used for localization and planning tasks.

[LAB 10: SIMULATOR](./lab10.html)

Lab 10 walks through a simulator, which is used to test out key software for planning and execution before implementation on the real robot.

[LAB 11: LOCALIZATION (BAYES FILTER, SIMULATION)](./lab11.html)

Lab 11 implements the Bayes Filter for performing state estimation and localization tasks in simulation before attempting these on the real robot for planning and execution.


[LAB 12: LOCALIZATION (BAYES FILTER, REAL)](./lab12.html)

Lab 12 extends the localization module from Lab 11, with the real robot attempting to predict its position in the map using the Bayes Filter and time-of-flight sensor values.


[LAB 13: PLANNING AND EXECUTION](./lab13.html)

Lab 13 combines all our learnings from the latter sequence of labs to make the robot execute a desired trajectory within the map as accurately and quickly as possible.
