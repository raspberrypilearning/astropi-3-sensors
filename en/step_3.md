## Display useful values

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will round off your float values and convert them to strings so they can be used with the senseHAT LED array and printed in the console neatly.
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>
 <p style='border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;'>
 A <strong>float</strong> value is short for **floating point**, and it really just means a number with a decimal point in it. We use **floats** when more precision is needed, but they look a little messy at first glance. A number without any decimal places is an **integer**, and it is a different sort of python data type.
 </p>

So far, the output from our sensor program is quite unreadable - if you didn't know exactly what this was, you would have no idea what any of the long numbers you were looking at meant! In order to get more useful data, you will need to shorten the output of these numbers using `round`.

When using `round`, you need to specify two arguments:
 + which number you want to round off
 + how many decimal places you want it rounded to

If you don't specify how many decimal places you want to round your float to, the default is `0` - `round` will return the nearest integer. 

The example here takes the floating point value of each of the datapoints from the sensors, then rounds that value to one decimal place, but you can put any number you like.

--- task ---

**Type:** On lines 13, 14 and 15 add the following to your script, to round each sensor value to one decimal place:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7
line_highlights: 13-15
---
#Take sensor reading
t = sense.get_temperature()
p = sense.get_pressure()
h = sense.get_humidity()

#Round sensor values
t = round(t,1)
p = round(p,1)
h = round(h,1)

--- /code --- 

--- /task --- 

--- task ---

**Test:** Run your code. The numbers output in the console should now have only one decimal place.

--- /task ---



+ Output float values to display - way too long/not useful
+ Round values using math library
+ Use f-strings to display values

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