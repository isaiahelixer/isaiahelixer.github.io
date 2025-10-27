---
title: Individal Block Diagram
tags:
- tag1
- tag2
---

## Overview
This subsystem monitors environmental conditions using digital sensors for soil moisture, rainwater, and temperature/humidity. It uses a Microchip PIC18F57Q43 Curiosity Nano microcontroller to read sensor data via analog pins and digital I/O and PWM which processes the information and makes it available to the rest of the system for decision-making. 

The system is powered by a 9V, 3A unregulated power supply and is regulated down to 5V, 1.5A using a voltage regulator to ensure safe and stable operation of the microcontroller and all connected sensors.  

It interfaces with three digital sensors:  
-Soil Moisture Sensor  
-Rain Water Sensor  
-Temperature/Humidity Sensor  

Actuator Interface:  
This subsystem doesn't directly control an actuator but it provides sensor data to other subsystems such as motor control that can act upon the readings.  

## Block Diagram  

<img width="899" height="599" alt="Screenshot 2025-10-06 190912" src="https://github.com/isaiahelixer/isaiahelixer.github.io/blob/ac9d10433c230e0cc258b8df67a11bce1913b4ff/docs/01-Block-Diagram/Block%20Diagram%20-%20Individual.drawio.png" />
