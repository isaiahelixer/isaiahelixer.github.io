---
title: Microcontroller Code Firmware
---
## Overview
This section describes the firmware code that runs the capacitive soil moister sensor subsystem. The code initializes the PIC18F57Q43 Curiosity Nano and initializes up all required peripherals, including the ADC for moisture sensing, UART for communication, PWM for output signaling, and GPIO for system inputs and LED feedback. After a short warm-up period to let the sensor stabilize and the microcontroller performs burst sampling on the RA7 analog input and applies a smoothing filter to produce a clean and stable moisture reading.

The firmware uses a simple system state with three modes being Waiting, Transmitting, and Error. In normal operation the system monitors a digital request line on RB4. When no request is active the device stays in a low-activity wait state and sends periodic status logs. When a request signal is received the controller calculates a corresponding PWM duty cycle based on the moisture level and sends that value out through the high-speed PWM channel for other connected boards to processes while also showing fast LED feedback for visibility.

If the ADC reading drops below a defined threshold the system enters an Error state and disables PWM output. Throughout operation the code maintains a steady communication over UART and handles LED heartbeat patterns for clear user feedback with smooth/low sensor noise and ensures consistent and reliable performance in the field.

The microcontroller firmware code as a project zip download is available [*here*](https://github.com/user-attachments/files/23916973/Soil_Sensor.zip)
