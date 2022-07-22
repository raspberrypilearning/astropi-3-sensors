## Display useful values

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will round off your float values and convert them to strings so they can be used with the senseHAT LED array and printed in the console neatly.
</div>
</div>
<div>
<iframe src="https://trinket.io/embed/python/c15fa5285a?outputOnly=true&runOption=run&start=result" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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
line_highlights: 14-16
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

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: SyntaxError
---
+ Have you got both brackets in your commands? `round()`

--- /collapse ---

--- collapse ---
---
title: NameError
---
+ Have you spelled `round` correctly?
+ Have you tried to round `t`, `p` and `h`, or something else?

--- /collapse ---

--- /task ---

Now that your numbers are looking more readable, you need to add some text to make the output more easily understandable. To do that, we need to format the value as a **string**.

--- task ---

**Edit:**  Change the argument in your `print` commands on lines 20,21 and 22 to match the following:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19 
line_highlights: 20-22
---
#Print sensor data
print(str(t))
print(str(p))
print(str(h))

--- /code ---

Using `str()` converts the data values of any argument put in the brackets from numbers into a **string**, so they can be linked together with other strings in your program. Linking strings together into one long one is called **concatenation**.

--- /task ---

--- task ---

**Edit:** Add another string to each of the `print` lines in your code to match the following:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 19 
line_highlights: 20-22
---
#Print sensor data
print("Temperature: " + str(t))
print("Pressure: " + str(p))
print("Humidity: " + str(h))

--- /code ---

--- /task ---

--- task ---

**Test:** Run your code. You should see an output that looks something like this:
`Temperature: 13.3`
`Pressure: 1013.0`
`Humidity: 46.2`

--- /task ---

--- task ---

**Debug:** 
+ What does your error message say? Which line has an error?
+ Does your code match the code above?

--- collapse ---
---
title: SyntaxError
---
+ Have you got four brackets in your print commands? `print( str())`
+ Have you got quotation marks at the start and end of all your strings? `"Temperature: "`
+ Have you got a `+` sign between your string and the sensor value on each line?

--- /collapse ---

--- collapse ---
---
title: NameError
---
+ Have you spelled `print` correctly?
+ Have you tried to round `t`, `p` and `h`, or something else?

--- /collapse ---

--- /task ---

--- task ---

--- collapse ---
---
title: **Challenge:** Can you show your sensor values on the LED array?
---

Change the `print` on the final three lines of your code to `show_message`!


--- /collapse ---

--- /task ---



--- save ---