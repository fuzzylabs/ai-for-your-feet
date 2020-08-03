# AI For Your Feet

This is a project to track gait, posture and exercise with wearable _things_. The project covers a full AI stack, from hardware to models to cloud-deployed web services.

AI For Your Feet, also known as *Wearable, [my foot](https://en.wiktionary.org/wiki/my_foot)* is built by [Fuzzy Labs](https://fuzzylabs.ai).

## Hardware

The hardware is based on an ESP32 microcontroller, which is Arduino-compatible.

n.b. the current generation of hardware is a prototype. Future iterations will have a better form-factor by using smaller components. Example product links are included for purchasing the components.

* 1 breadboard: https://www.amazon.co.uk/ELEGOO-Breadboard-Solderless-Distribution-Connecting/dp/B01M0QJTI5
* Wires: https://www.amazon.co.uk/Elegoo-120pcs-Multicolored-Breadboard-arduino-colorful/dp/B01EV70C78/
* ESP32 microcontroller: https://www.amazon.co.uk/ESP-32S-Development-2-4GHz-Bluetooth-Antenna/dp/B071JR9WS9/
* Resistors: 
* Pressure sensors: https://uk.farnell.com/ohmite/fsr04be/force-sensing-resistor-02ah9085/dp/3216598

## Microcontroller code

The code for the ESP32 is built using PlatformIO.

In the [esp32](esp32) directory:

### Optional Virtualenv setup

Feel free to skip if you're installing / have installed PlatformIO using a different method. To initialise the environment using `pip`:

```
virtualenv env
source env/bin/activate
pip install -r requirements.txt
```

To activate the environment, `source env/bin/activate`.

### Building and deploying to the device

To *Just build*

```
platformio run
```

*Build and upload*

```
platformio run -t upload
```

*Run the tests* - this builds a new image and uploads it so that tests are run on the device

```
platformio test
```

## Android app

The Android app allows the device to connect via Bluetooth and upload data. It's written in [Kotlin](https://kotlinlang.org).

### Building and deploying via Android Studio

TODO

### Screen sharing Android device on linx

TODO (scrcpy)

## Jupyter notebooks

## Data

The [data](data) directory contains some example data generated by the device.

## Data dashboard (Dash)

The [dash](dash) directory contains a dashboard generated by the [Dash](https://plotly.com/dash) framework. Dash is Python-based, and uses the [Flask](https://flask.palletsprojects.com) web framework; Dash is similar to [R-Shiny](https://shiny.rstudio.com).

### Running locally

```
pip install -r requirements.txt
```

```
python app.py
```

### Modification

* For a guide to Plot.ly graphs, see [here](https://plotly.com/python/basic-charts).
