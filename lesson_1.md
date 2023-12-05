#  Introduction to Hardware Programming

## Task 1 - Using a Button to print words to the console.

### Overview

For the first task, we want to print some words every time the button is
pressed. We're going to use the breadboard, a button and the raspberry
pi for this, that's all.

### Components

- Raspberry Pi
- Breadboard
- Button
- Jumper Cables

### Step by Step

#### Build The Circuit

[image]

1. Using two jumper cables, connect the positive 'bar' to GPIO26 (#37), then the negative bar to GND (#39).
2. Place a button onto the breadboard, with the top left corner in cell E10.
3. Use two jumper cables, connect the positive bar to A10, then connect the negative bar to E12.

#### Write the Code

1. Setup

First, we'll import the Python module that allows us to interact with the GPIO pins. There's a
lot of code here that we need, that you don't really need to understand yet. We'll just copy and
paste this into the code editor.

In a new file called 'simple_button_press.py', add the following code:

```python3
import RPi.GPIO as GPIO # Import Raspberry Pi GPIO library

# Ignore warning for now
GPIO.setwarnings(False) 

# Use physical pin numbering
GPIO.setmode(GPIO.BOARD)
 
# Set pin 10 to be an input pin and set initial value to be pulled low (off)
GPIO.setup(10, GPIO.IN, pull_up_down=GPIO.PUD_DOWN) 

``` 

2. Add Your Code 

We need a while loop to run forever, and on each iteration check if pin 10 is now 'HIGH'.

There's a template below, replace the ... with code that will make this work.

```python3

# A While loop that will run forever (i.e. is always True)
... True: # Run forever

    # Now we need an If Statement to check if GPIO.input(1) is equal to GPIO.HIGH
    ... GPIO.input(10) ... GPIO.HIGH:
        print("Button was pushed!")
```

3. Make it Better!

You may notice that you see 'Button was pushed!' appear on your screen quite a few times...
This is because our code currently just checks if the button is pressed. Ideally, we want
to check if it *has just been pressed*.

We're going to modify the code to do that.

In a new file called 'better_button_press.py' add the following code:

```python3
import RPi.GPIO as GPIO # Import Raspberry Pi GPIO library

# Ignore warning for now
GPIO.setwarnings(False) 

# Use physical pin numbering
GPIO.setmode(GPIO.BOARD)
 
# Set pin 10 to be an input pin and set initial value to be pulled low (off)
GPIO.setup(10, GPIO.IN, pull_up_down=GPIO.PUD_DOWN) 

```

This time though, we're going to create a function, then tell the raspberry pi to call that
function each time the GPIO pin *changes state* (the fancy phrase for 'is pressed or not'.


4. Create the Function

Below is code that *should* take one argument called 'channel' and print 'Button was pushed!'
when it is called. Can you replace the ... with the code needed to make this work?

```python3
... button_callback...channel...:
    print("Button was pushed!")
```

5. Add the 'Callback'

This line tells the raspberry pi to call the function 'button_callback' each time the button
changes state.

```python3
GPIO.add_event_detect(10, GPIO.RISING, callback=button_callback)
```

Once you've added that into your code, run it and see what happens on the console. Do
you see one line each time the button is pressed?


## Task 2 - Getting an LED to blink.




## Task 3 - Looping Through Multiple LEDs.





