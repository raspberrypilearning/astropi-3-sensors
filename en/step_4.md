## Use images for display

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will use the data collected from the SenseHAT sensors to display different colours or images  on the SenseHAT LED array.  
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

Now that you can output useful information from our sensors, you can use the SenseHAT's LED array to display that information in an easy to read format that is visible at a glance. 

You can use the array to display a single colour, as a simple readout for something like temperature. For example, if the temperature goes above a certain point or **threshold**, the SenseHAT will show red, but if below that point it will show blue.

The first thing to do is create the rules for this in your program using an **if statement**.

<p style='border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;'>
**If statements** are logical blocks used in programming. They allow a computer to make decisions based on certain information, like how warm the room is. They are called **if** statements because they ask the computer to do something **if a certain condition is met**.
</p>

In this example, we are going to use the `sense.clear()` function to make the LED array change to a single colour using RGB values. The example uses red and blue, but you can use any colour you like!

[[[rpi-sensehat-display-colour]]]

[[[generic-theory-colours]]]

--- task ---

**Type:** You will need to access the sleep library for this step, so must import it at the beginning of your program. At the top of your code, on the second line add:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 2
---
from sense_hat import SenseHat
from time import sleep
--- /code ---

--- /task ---


--- task ---

**Type:** On line 25, beneath the line which reads `#If statement to check threshold` add the following lines to your code:
--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 24 
line_highlights: 
---
#If statement to check threshold
if t >= 13:
  sense.clear(255,0,0)
  sleep(0.5)
else:
  sense.clear(0,0,255)
  sleep(0.5)

--- /code ---

**Tip:** Make sure you get the indents in the right places! `if` and `else` should be in line, while the other lines are indented. 

--- /task ---

--- task ---

**Test:** Run your code. You should see the LED array light up red or blue, depending on the value of the ambient temperature around your SenseHAT.  

--- /task ---

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: SyntaxError
---
+ Have you got a colon at the end of  your `if` statement? `if t >=13:`
+ Have you got an indent of four spaces before `sense.clear()` and `sleep()`?
+ Have you got closed the brackets at the end of `sense.clear()` and `sleep()`?

--- /collapse ---

--- /task ---

--- task ---

**Try:** Move the temperature slider and run your code again. You should see the colour change on the LED array.

--- /task ---

The last step is to create a **loop** that will allow our sensors to check repeatedly and keep track of the temperature. Because you have added a `sleep` of 0.5 seconds to our program after each check of the sensors, create a loop that runs 60 times - this means your program will run for **30 seconds**. 

--- task ---

**Type:** On line 7 in your code, **above** where it reads `#Take sensor reading` add the following line:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 5 
line_highlights: 7
---
sense = SenseHat()

for i in range(120):
#Take sensor reading

--- /code ---

--- /task ---

--- task ---

**Edit:** Select all the code below the line you just typed - everything from line 8 to the end. Press `Tab` on your keyboard to indent all this code and have it run inside your new `for` loop. 

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 9-33
---
from sense_hat import SenseHat
from time import sleep


sense = SenseHat()


for i in range(120):
  #Take sensor reading
  t = sense.get_temperature()
  p = sense.get_pressure()
  h = sense.get_humidity()
  
  
  #Round sensor values
  t = round(t,1)
  p = round(p,1)
  h = round(h,1)
  
  
  #Print sensor data
  print("Temperature: " + str(t))
  print("Pressure: " + str(p))
  print("Humidity: " + str(h))
  

  #If statement to check threshold
  if t >= 13:
  sense.clear(255,0,0)
    sleep(0.5)
  else:
    sense.clear(0,0,255)
    sleep(0.5)
--- /code ---

--- /task ---

--- task ---

**Test:** Run your code and move the temperature slider. You should see the LED array change colour between red and blue.

--- /task ---

--- task ---

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: SyntaxError
---
+ Have you missed a line with your indenting?
+ Do you have both brackets in your `for` loop?
+ Does your `for` loop have a colon at the end? `for i in range(120):` 

--- /collapse ---

--- /task ---

--- /task ---



--- save ---