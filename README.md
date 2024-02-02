### Overview
Some experimentation with combining nicegui (https://nicegui.io/), a Python web frontend with the javascript webserial API. UI elements defined in nicegui are hooked to javascript functions that access the webserial API. 

This example interfaces with a PyBadge board (https://learn.adafruit.com/adafruit-pybadge/overview). Light sensor readings are made at a rate of 5 Hz (adjustable) and read from the serial port, triggering a custom asyncrhonous event, and updating the live plot. The NeoPixel LEDs at the bottom of board can be toggled on or off, demonstrating writing data to the serial port.

![image](https://github.com/BlankAdventure/ngws/assets/24900496/fabcfe89-a19a-404e-a076-d5f03ce7b52f)

![image](https://github.com/BlankAdventure/ngws/assets/24900496/8724350d-bc61-484a-b253-29d044a40386)

### Files
main.py -> Python nicegui code. This is the file to run.

script.js -> JavaScript code lives here.

sketch.ino -> Wiring sketch (C code with Adafruit libraries) for target MCU.  

### Why Is This Interesting?
Great, you wrote/read to a serial port and threw a web UI on top, big deal. Well...normally, the external hardware would be accessible only through locally-running code. For example, you might have a bunch of clients connecting to a remote server, controlling a remote webcam. In this arrangement the server has a local (physical) connection to the webcam, permitting Python to access it. With webserial, we can invert this relationship. Webserial allows for in-browser access of the local (client) machine's usb/serial ports! This enables the Python backend (running on the remove server) to break throgh the frontend and tunnel out of the browser to the client's serial port(s). This has a bunch of neat implications for production automation and deployment. For example, we could have local equipment (test equipment, etc) whose control interface is a web app. Here, there is no need to deploy any local code(!) beyond that of a modern updated browser. Duplicating test stations requires no local Python installation. Additionally any code updates can be singularly pushed the server! 
