# Automated Plant Watering System

An early-stage plant watering project built around an ESP32 microcontroller, capacitive moisture sensing, pump control, and a small status display.

## Current Hardware Parts
- ESP32 board
- Capacitive Soil Moisture Sensor v2.0
- Water pump and tubing
- Relay module
- Small display screen
- Breadboard and jumper wires

## Current Status
Flashed MicroPython (`v1.29.0`) onto the ESP32 and verified baseline analog sensor behavior before wiring in the relay, water pump, and display, writing control logic, and building an enclosure.

## Initial Sensor Testing
Using a 3-pin jumper connection (`3V3`, `GND`, and `AOUT` wired to `GPIO 33` with 12-bit ADC and `ATTN_11DB` attenuation), the sensor was tested in dry air and then exposed to water while streaming readings over Thonny's MicroPython Shell.

### Test Bench Wiring Setup
![ESP32 and Capacitive Soil Moisture Sensor v2.0 Wiring Setup](initial_wiring.png)

The sensor's `3V3` and `GND` pins are powered from the ESP32 rail, with the analog signal (`AOUT`) routed to `GPIO 33` (`ADC1`) to verify power and signal continuity without a multimeter.

### Dry vs. Wet Test Results
![Thonny MicroPython Serial Output Comparing Dry and Wet Sensor Readings](initial_data.JPG)

In dry air, the sensor outputs a steady baseline around **2.21 V – 2.30 V** (raw ADC ~2747–2855). When exposed to water, the analog voltage drops substantially (reaching as low as **0.96 V** / raw ADC 1188 in the test log), confirming the capacitive circuit responds cleanly and providing dry/wet endpoints for moisture percentage calibration.
