# esphome-xiao-soil

ESPHome Zigbee firmware for the [Seeed Studio XIAO ESP32-C6 Soil Moisture Sensor](https://www.seeedstudio.com/XIAO-ESP32C6-p-5884.html).

## Status

At time of writing, this is operating in a garden outside. I don't know how much more power-efficent it is yet.

## Features

- Zigbee soil moisture, temperature, and battery reporting
- Adaptive deep sleep (15min / 1hr / 8hr based on moisture level)
- LED status indicators (red/yellow/green)
- 10-press button calibration with auto water detection
- Configurable NiMH/alkaline battery voltage range

## Differences from stock firmware

- Zigbee instead of WiFi (lower power, no router dependency)
- 10-press calibration instead of triple-press

## Calibration

Calibrate on first install, whenever the red LED is flashing (uncalibrated/error state), or every year or two as the sensor degrades.

1. Hold the probe in air and press the button 10 times rapidly (within 5 seconds)
2. Yellow flash confirms dry reading taken
3. Green blink — dip probe in a glass of water
4. Wait for solid green (wet reading taken)
5. Solid green = success, solid red = failure

## Hardware

- Board: Seeed XIAO ESP32-C6
- Soil sensor: capacitive ADC on GPIO1
- Battery sensor: ADC on GPIO0
- LEDs: GPIO18 (yellow), GPIO19 (green), GPIO20 (red)
- Excitation: LEDC PWM on GPIO21
- Button/wake: GPIO2

## Attribution

Based on the [Seeed Studio XIAO ESP32C6 Soil Moisture Sensor](https://wiki.seeedstudio.com/xiao_esp32c6_soil_moisture/).
