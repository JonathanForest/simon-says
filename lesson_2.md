# Creating A Light Show

## Introduction

For today, we are going to connect 4 LEDs to separate GPIO pins on the Raspberry Pi.

We are going to use loops and functions to create a light show, where we turn on one or many LEDs at
a time.


## Setup

### Building the Board

![Alt Text](./images/multipleLEDs.png?raw=true)

Copy this diagram as best you can. Ask one of the Instructors if you need anything.

Remember to ensure all the LEDs are plugged in the same way.

### Setting up the Code

As we're just making sure the circuit is working, copy the below code into your code editor and
run it.

If the LEDs don't turn on, check the circuit. If don't see anything wrong, ask an instructor
(or someone next to you who has managed to get it to work...


```python3
# Import Raspberry Pi GPIO library
import RPi.GPIO as GPIO 

# Ignore warnings for now, don't worry - all errors in your code will still show up...
GPIO.setwarnings(False) 

# Use physical pin numbering instead of the technical numbering
GPIO.setmode(GPIO.BOARD)
 
# To ensure that the circuit is built correctly, run this code. *In Theory*, all the LEDs
# should light up.

LED1 = 36
LED2 = 37
LED3 = 38
LED4 = 40

GPIO.setup(LED1, GPIO.OUT)
GPIO.setup(LED2, GPIO.OUT)
GPIO.setup(LED3, GPIO.OUT)
GPIO.setup(LED4, GPIO.OUT)

print("GPIO Pins have been setup")

def turn_on_an_led(pin):
    GPIO.output(pin, True)

for led in [LED1, LED2, LED3, LED4]:
    print(f"Turning on GPIO pin {led}")
    turn_on_an_led(led)

print("Lights should be turned on now.")

```

## Now the fun begins!

**Create a new file called 'lightshow.py'.**

Copy the following code:

```python3
# Import Raspberry Pi GPIO library
import RPi.GPIO as GPIO 

# Ignore warnings for now, don't worry - all errors in your code will still show up...
GPIO.setwarnings(False) 

# Use physical pin numbering instead of the technical numbering
GPIO.setmode(GPIO.BOARD)
 
```

### Setup the GPIO Pins

Now we need to setup the GPIO pins. Complete the code below, create four variables and add them to
the GPIO setup code.

(If stuck, Your code should look like the stuff from before...)

```python3
... = 36
... = 37
... = 38
... = 40

GPIO.setup(..., GPIO.OUT)
GPIO.setup(..., GPIO.OUT)
GPIO.setup(..., GPIO.OUT)
GPIO.setup(..., GPIO.OUT)

```

### Creating a list that contains the Pin variables

Later on in the program, we're going to use a list to make it easier to turn the LEDs on and off.

Let's create a list, that contains the four variables we made earlier.

Complete the following line of code and add it to the end of your program.

```python3

led_list = ...

```

### Importing Other Peoples Code

We've just realised that we need to import some code other people have written.

We need to import the 'time' module, as well as the 'random' module.

Scroll back up to the top of your file (because module imports *should* go at the top) and add the
following line:

```python3
# Here, we want to import the time module
import ...

# Here, we want to import the random module. When we do it this was though, we are only
# importing the function randint.
from ... import randint 

# Import Raspberry Pi GPIO library
import RPi.GPIO as GPIO 

# Ignore warnings for now, don't worry - all errors in your code will still show up...
GPIO.setwarnings(False) 

```

### Creating the Loop that light's up the LEDs!

Scroll back down to the bottom of the file. Now that we have setup the GPIO pins and imported the
modules we need, we can now start writing the code that does things!

We've got to do the following things:

1. Create a function that turns on the LED, waits half a second, then turns it off.
2. Create a function that generates a random number between 36 and 40, but regenerates it if it
   is equal to 39.
3. Create a while loop that never ends.
4. Call the function we created earlier, sending the randomly generated number as a
   parameter/argument.

### 1. Create the function that turns the LED on and Off

This function needs to turn a GPIO pin on, then wait half a second, then turn the GPIO pin off.

(For extra credit, figure out how to send the number of seconds as an optional keyword
argument...)

```python3

# When creating a function, use this as a hint
def new_function(put, arguments, here):
    # Code goes here.

# Below create a new function called 'blink_light' that takes one argument.
... blink_light...:
    # Then, add three lines of code, one to turn the light on, the other to wait, then one more
    # to turn the light off.

    GPIO.ouput(..., ...)
    time.sleep(...)
    GPIO...(..., ...)

```

### 2. Create a function that generates a random number.

Now we're going to generate a random number, using a while loop and an if statement. **We'll put this
code into a function so that we can call it from elsewhere in the program.**

```python3

# Define a function below called 'get_random_pin_number'
... get_random_pin_number...
    
    # Here, let's set the variable pin to equal 'None'
    ... = None

    # Here' we're creating a while loop that runs until the random number generator generates a
    # valid pin number
    while True:
    
        pin = randint(36, 40)

        # Below, add an if statement that checks if the value of pin is not equal to 39.
        # If it is not equal to 39 'return' the variable 'pin'.
        if ...:
            return ...

```


### 3. Connecting it all together

We now need to create a while loop, and call the functions above to make the LEDs flash in a random
order.

Let's create a while loop, and then call the two functions we defined above.

```python3

# Create a while loop that never ends
... True:
    
    # Call the 'get_random_pin_number' function
    ...

    # Call the 'blink_light' function
    ...

```

Now if you run your code, you should see the lights turn on and off in a random order!




## The End!

If you have enough time (around 30 minutes left), 








