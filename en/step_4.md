## Sense movement

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will explore the Inertial Measurement Unit (IMU) on the SenseHAT and use it to make the LED array do something. 
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

<p style='border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;'>
The Sense HAT has a movement sensor called an <strong>IMU</strong>, which measures the kinds of movement it experiences. It’s actually three sensors in one:

+ A gyroscope: measures momentum and rotation
+ An accelerometer: measures acceleration forces and can be used to find the direction of gravity
+ A magnetometer: measures the Earth’s own magnetic field (a bit like a compass)
</p>

[[[generic-theory-pitch-roll-yaw]]]

The `sense.get_accelerometer_raw()` method tells you the amount of G-force acting on each axis (x, y, z). If any axis has ±1G, then you know that axis is pointing downwards.

 + Image change based on physical input - shake/hit/rotate

--- task ---

Another step of tasks to complete.

--- /task ---

--- task ---

Step content... 
Can use:
**Test:**
**Choose:**
**Tip:**

--- /task ---

--- save ---