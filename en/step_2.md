## Sense the Environment

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will use the environmental sensors (thermometer, hygrometer, barometer) to collect information about the environment and print it to the console.
</div>
</div>
<div>
<iframe src="https://trinket.io/embed/python/c15fa5285a?outputOnly=true&runOption=run&start=result" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

+ Temp
+ Humidity
+ Pressure
+ Colour sensor
+ Display Readout 



--- task ---

Open the [SenseHAT Sensors Starter project](https://trinket.io/python/4b417a690b){:target="_blank"}. Trinket will open in another browser tab.

--- /task ---

We can **poll** the sensors on the SenseHAT to find out what the temperature is by using the command `sense.get_temperature()`. To be able to use this data, we need to store it in a variable.

--- task ---

**Type:** In you new script window on line 8, below `#Take sensor reading` add the following line:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7 
line_highlights: 8
---
#Take sensor reading
t = sense.get_temperature()

--- /code ---

This stores the current temperature reading as `t`.

--- /task ---

The next step is to print the temperature data to the console, so it can be read.

--- task ---

**Type:** On line 12, beneath the line which reads `#Print sensor data` add the following command:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 11 
line_highlights: 12
---
#Print sensor data
print(t)

--- /code ---

--- /task ---

--- task ---

**Test:** Run your code. You should see the console print out a long number: 13.3096771666. This is the default simulated temperature of the SenseHAT. 

--- /task ---

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: AttributeError
---
+ Have you spelled `get_temperature` correctly?

--- /collapse ---

--- collapse ---
---
title: SyntaxError
---
+ Have you got both brackets in your command? `get_temperature()`

--- /collapse ---

--- collapse ---
---
title: NameError
---
+ Have you tried to print `t`, or something else?


--- /collapse ---

--- /task ---


--- task ---

**Try:** Move the temperature slider and run your code again. It should print out something different that matches your new slider value.

--- /task ---

You can also use the commands `get_pressure` and `get_humidity` to poll the barometer and hygrometer.

--- task ---

**Type:** On lines 9 and 10, add the following to your script:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7
line_highlights: 9-10
---
#Take sensor reading
t = sense.get_temperature()
p = sense.get_pressure()
h = sense.get_humidity()

--- /code ---

--- /task ---

--- task ---

**Type:** Now `print` the new data in the same way as the temperature data:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 13 
line_highlights: 15-16
---
#Print sensor data
print(t)
print(p)
print(h)
--- /code ---

--- /task ---

--- task ---

**Test:** Run your code. You should now see three numbers printed out for the temperature, pressure and humidity values.

--- /task ---

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: AttributeError
---
+ Have you spelled `get_pressure` and `get_humidity` correctly?

--- /collapse ---

--- collapse ---
---
title: SyntaxError
---
+ Have you got both brackets in your commands? `get_pressure()`

--- /collapse ---

--- collapse ---
---
title: NameError
---
+ Have you tried to print `p` and `h`, or something else?

--- /collapse ---

--- /task ---

In the next step, you will take those long numbers and make them look neater and easier to read!

--- save ---