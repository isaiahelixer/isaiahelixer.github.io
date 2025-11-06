---
title: Individual Block Diagram
tags:
- subsystem
- soil-sensor
---

## Overview
This subsystem monitors soil saturation levels using an analog soil moisture sensor. A Microchip PIC18F57Q43 Curiosity Nano microcontroller reads the sensor’s analog output, processes the data, and transmits the results to the main system for further analysis and control actions.

Power is supplied by a 9V, 3A wall adapter, which is regulated down to 5V, 1.5A through a voltage regulator to provide stable and safe operation for both the microcontroller and sensor.

## Sensors and Interfaces
Connected Sensor:
Analog Capacitive Soil Moisture Sensor  

System Interface:
Communicates soil data to other subsystems (e.g., motor control or irrigation logic) through an 8-pin connector, enabling coordinated system responses based on soil conditions.

## Block Diagram
<img width="1417" height="1052" alt="Screenshot 2025-11-05 194656" src="https://github.com/user-attachments/assets/f3822f91-4b1c-4023-a7da-51511fcb4c94" />







