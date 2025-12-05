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
Communicates soil data to other subsystems through an 8-pin connector which enables a coordinated system responses based on soil conditions.

## Meeting Team Product Requirments
In my subsystem the PIC Microcontroller Generates the 100 kHz PWM drive signal, performs ADC processing, and outputs a clean PWM moisture value to show accurate soil-based watering decisions that help reduce household water and support smart scheduling for both homeowners and landscapers. It Inlcudes a Hand-built Capacitive Soil Moisture Sensor to Measure real soil saturation and allowing the system to avoid unnecessary watering and meet the core requirement of water efficiency while supporting user stories centered on preventing overwatering. Op-Amp Filter/Amplifier to Improve signal quality and stability which enhances system reliability in outdoor conditions and supports durable and accurate operation needed for long-term watering control. Voltage Regulator 9V to 5V to Provide stable power to the PIC and sensor supporting durability and safety with consistent performance in varying temperatures and weather. The 8-Pin Connector Sends processed soil data to the teammate’s controller and waits for a sensor ready signal supporting the multi-zone expandability and coordinated scheduling. My PWM output to the main controller provides a simple and affordable communication method that integrates easily with the larger system which supports cost targets of under $200 and helping compatibility with smart cloud-based features. My handshake input pin helps the subsystem only transmits data when the main controller requests it, this improving reliability and reducing processing errors in use cases requiring accurate multi-zone reporting. My debug header pins allows quick diagnostics to help in customer support needs for easy troubleshooting to identify faults without disassembly. My debug button can help test and verify subsystem function quickly which supports a 30-minute installation goal and aiding in manufacturing/assembly testing. The debug LEDs Provide instant visual feedback on system status and helping beginners understand what the sensor is doing giving accessible diagnostics required by stakeholders.

## Block Diagram
<img width="1558" height="1159" alt="Block Diagram - Isaiah" src="https://github.com/user-attachments/assets/a040560a-7d5a-4997-b7ab-ab9e056c5ab4" />
*Figure 1: Showing the capacitive soil sensor subsystem block diagram.*  







