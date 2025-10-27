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

<img width="3300" height="2550" alt="Subsystem Schematic Design" src="https://github.com/user-attachments/assets/90c2a820-02b4-4488-9c30-1e0c806ae228" />

