# Automated Plant Watering System

An early-stage plant watering project built around an esp32 microcontroller, moisture sensing, pump control, and a small status display.

## Current Hardware Parts
- ESP32 board
- Soil moisture sensor
- Water pump and tubing
- Relay module
- Small display screen
- Breadboard and jumper wires

## Current Status
Gathering and testing the core components before wiring everything together, writing the control logic, and building an enclosure.

## Initial Sensor Testing
Tested the Capacitive Soil Moisture Sensor v2.0 powered from the ESP32 (`3V3` and `GND`) with `AOUT` wired to `GPIO 33` and read in Thonny using MicroPython (`12-bit` ADC with `ATTN_11DB`).

### Wiring Setup
![ESP32 and Capacitive Soil Moisture Sensor v2.0 Wiring Setup](initial_wiring.JPG)

The sensor is connected to the ESP32 board over USB with `3V3`, `GND`, and `AOUT` (`GPIO 33`) wired via jumper cables to verify power and analog signal response.

### Initial Test Results
![Thonny Shell Output Showing Dry vs. Wet Sensor Readings](initial_data.png)

In a dry environment, the sensor reads steady around **2.2–2.3 V** (`ADC` roughly `2747–2855`). When exposed to water, the voltage drops sharply (down to **0.96 V** / `ADC` `1188` in the capture), confirming the sensor responds to moisture.
