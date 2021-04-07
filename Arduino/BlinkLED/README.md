# BlinkLED
Tutorial for writing better C++ code to control an LED with an Arduino

The BlinkLED example code shows how to blink one or more LEDs.  There are
multiple versions of the code, showing better and better ways to write the
code to make it more readable, maintainable, and reusable.

All of the versions of the code use the same circuit, which is described
here.  (The first version of the code uses only one of the LEDs.)

Components needed
-----------------
   2  LEDs (any colors, e.g., one red and one blue or even both the same) 
   2  resistors (almost any value, such as 220 ohms)
   1  Arduino board (any kind)
   1  breadboard (any kind)
      wires

Circuit description
--------------------
  1) LED1
       a) Negative lead connected to breadboard ground (-) rail
       b) Positive lead connected to any non-rail hole in the breadboard

  2) LED2
       a) Negative lead connected to breadboard ground (-) rail
       b) Positive lead connected to any non-rail hole in the breadboard other
            than one in the column you used for the LED1

  3) Resistor1
       a) One end connected to same column in breadboard as the positive
            lead of LED1
       b) Other end connected to a hole in a different column of the
            breadboard

  4) Resistor2
       a) One end connected to same column in breadboard as the positive
            lead of LED2
       b) Other end connected to a hole in an unused column of the
            breadboard

  5) Wires
       Note: It's good practive to leave the Arduino powered off until you've
             doublechecked your circuit.
       a) Wire from the end (3b above) of Resistor1 to Arduino pin 2
       b) Wire from the end (4b above) of Resistor2 to Arduino pin 3
       b) Wire Arduino pin "+5V" to "+" rail of breadboard
       c) Wire any Arduino pin labeled "GND" to "-" rail of breadboard


Here is a brief description of the sketch versions:
BlinkLED_v1
  Minimal demo showing how to blink a single LED, using only direct calls to
  low-level functions like digitalWrite().

BlinkLED_v2
  Defines functions like led_turnOn() and led_blink() as a clearer and more
  maintainable way to write code. Still blinks just a single LED.

BlinkLED_v3
  Generalizes the functions like led_turnOn() to take arguments, such as the
  pin number, in order to allow using one function with any number of LEDs.
  Blinks two LEDs and:
    1) shows why the basic led_blink() function just can't work as intended
    2) how to write timer-based code to allow blinking multiple LEDs
    3) shows the new maintainability problem that #2 just created

BlinkLED_v4
  Uses a C++ class as a much better way to encapsulate everything we've done
  so far, including fixing the new maintainability problem from the
  previous version.

BlinkLED_v5
  Uses the same code as the previous version, but shows how to split the C++
  class out into separate files from the sketch, so that the C++ class is
  ready to become its own library.
