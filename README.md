Some experimentation with combining nicegui (https://nicegui.io/), a Python web frontend with the javascript webserial API. UI elements defined in nicegui are hooked to javascript functions that access the webserial API. 

This example interfaces with a PyBadge board (https://learn.adafruit.com/adafruit-pybadge/overview). Light sensor readings are made at a rate of 5 Hz (adjustable) and read from the serial port, triggering a custom asyncrhonous event, and updating the live plot. The NeoPixel LEDs at the bottom of board can be toggled on or off, demonstrating writing data to the serial port.

![image](https://github.com/BlankAdventure/ngws/assets/24900496/fabcfe89-a19a-404e-a076-d5f03ce7b52f)

![image](https://github.com/BlankAdventure/ngws/assets/24900496/8724350d-bc61-484a-b253-29d044a40386)

main.py -> Python nicegui code. This is the file to run.
script.js -> JavaScript code lives here.
sketch.ino -> Wiring sketch (C++ code with Adafruit libraries) for target MCU.  
