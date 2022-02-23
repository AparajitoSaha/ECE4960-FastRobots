---
layout: default
---

## LAB 4: CHARACTERIZE THE CAR

[Back to Home](./index.html)

This lab involves characterizing the car that all future labs will employ. As a lightweight RC car with relatively high speed motors and a low mass, this car offers the potential to experiment with a number of different tricks. In this report, I describe some of the key physical parameters of the car, as well as some experimental details that will be relevant to future labs on navigation and control.

### Set A: Physical Parameters

These involved taking simple measurements of the car. I started by measuring the physical dimensions:
* Full width (incl. wheels) - 146mm
* Full length - 180mm
* Wheel diameter - 76mm (also body height since wheels are taller than the plastic chassis)
* Body height off ground (central axis) -  38mm
* Wheelbase - 100mm

The mass of the RC car along with the 850 mAh battery is 520 grams. The Artemis, along with the wired sensors and the unwired motor drivers, weighs about 35 grams. The total mass of the system would be around 560 grams (adjusting for wire mass and measuring errors).

To test battery life, I made the car spin about its axis until it slowed down to a stop (or more appropriately, until the car started shuddering and could not turn anymore, which I hope is not me damaging the motors). This took about 5 minutes and 48 seconds. I would have expected the battery to last longer, so it might be the case that the battery is degraded or was simply not fully charged. It took nearly 1 hour and 45 minutes to recharge the battery - I measured the voltage across the terminals until I reached close to 3.7 volts. This does mean that testing with the car will have to be planned out in advance and should be done incrementally so as to not deplete the battery fully while debugging errors.

### Set B: Experimental parameters

#### Velocity and Drift

For measuring the velocity of the car, I chose a control environment (namely, the hallway in Phillips Hall leading from Phillips 239 to Phillips 219) and measured out a distance of 5 meters using a measuring tape. I placed a cardboard box at the end of the 5 meter length in order to have a fixed stopping point that was easy to detect. With a friend’s help, I carried out 8 measurements of how long the RC car took to cover that distance using a stopwatch, getting a speed range of between 1.5 to 1.9 meters per second, with an average speed of 1.65 meters per second. The car is pretty fast for its size - it would be interesting to also measure how long it takes to accelerate to its maximum speed. I also noticed while conducting this test that the car doesn’t drive fully straight; it drifted from its initial position by about 60cm to the left, almost missing the box on two runs. This could result from a calibration issue between motors where the right one spins faster than the left causing a bias towards the left direction overall - future labs that implement closed loop PID control may resolve this problem.

#### Rotational (angular) velocity

For this test, I placed the RC car near the center of a 3 feet long by 3 feet wide box. I then drove the car in a circle around its axis, measuring how many times it rotates in a period of 4 seconds. I counted around 20 rotations, which means an average of 5 rotations per second. We can use this information to dictate the turns the car will need to make during navigation tasks - it may also prove useful while using the ToF sensors to create a grid of obstacles around the robot since we now roughly know the acquisition time for this data.

#### Tricks!

I performed a couple of interesting tricks with the robot. I first attempted a 180 degree flip, which consists of driving the robot ahead at full speed and then quickly reversing the direction of movement, which causes the robot to flip over due to its inertia. I also completed a “tree flip”, wherein I drove the robot straight into a vertical obstacle, causing it to climb until it was perpendicular to the floor before flipping over. I noticed that the wheels of the robot allow good enough grasp to complete such a task - this may lead to some issues with friction on carpeted surfaces instead of smooth ones.

#### Final thoughts on control

It is difficult to obtain precise control over the RC car using manual control. Flipping the car took some trial and error to get the timing down. Using the Artemis may work better for stunts since we can have more granular control sequences for the robot. While working out the velocity tests, I also experimented with trying to stop the robot before it collided with the box - the car took approximately 1 second to come to a complete stop from near maximum speed during these tests and with some practice, I could repeatedly stop the car before it hit the obstacle.

