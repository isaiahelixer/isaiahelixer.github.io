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

## Meeting Team Product Requirments
PIC Microcontroller – Generates the 100 kHz drive signal, performs ADC processing, and outputs a clean PWM moisture value, enabling accurate soil-based watering decisions that help reduce household water use by ≥30% and support smart scheduling for both homeowners and landscapers.

Hand-built Capacitive Soil Moisture Sensor – Measures real soil saturation, allowing the system to avoid unnecessary watering and meet the core requirement of water efficiency while supporting user stories centered on preventing overwatering.

Op-Amp Filter/Amplifier – Improves signal quality and stability, which enhances system reliability in outdoor conditions and supports durable, accurate operation needed for long-term watering control.

Voltage Regulator (9V → 5V) – Provides stable power to the PIC and sensor, supporting durability, safety, and consistent performance in varying temperatures and weather.

8-Pin Connector (Data Out + Handshake Input) – Sends processed soil data to the teammate’s controller and waits for a ready signal, supporting multi-zone expandability, coordinated scheduling, and efficient installation with modular plug-and-play wiring.

PWM Output to Main Controller – Provides a simple and affordable communication method that integrates easily with the larger system, supporting cost targets under $200 and ensuring compatibility with smart, cloud-based features.

Handshake Input Pin – Ensures the subsystem only transmits data when the main controller requests it, improving reliability, reducing processing errors, and supporting landscaper use cases requiring accurate multi-zone reporting.

Debug Header Pins – Allow quick diagnostics, helping customer support needs for easy troubleshooting and enabling users or technicians to identify faults without disassembly.

Debug Button – Lets developers and technicians test and verify subsystem function quickly, supporting a 30-minute installation goal and assisting with manufacturing/assembly testing.

Debug LEDs – Provide instant visual feedback on system status, helping beginners understand what the sensor is doing and supporting clear, accessible diagnostics required by stakeholders.


## Block Diagram
<img width="1558" height="1159" alt="Block Diagram - Isaiah" src="https://github.com/user-attachments/assets/a040560a-7d5a-4997-b7ab-ab9e056c5ab4" />
*Figure 1: Showing the capacitive soil sensor subsystem block diagram.*







