---
title: Microcontroller Code Firmware
---
## Overview
This section describes the firmware that runs the Smart Irrigation Subsystem’s soil-moisture controller. The code initializes the PIC18F57Q43 Curiosity Nano and brings up all required peripherals, including the ADC for moisture sensing, UART for communication, PWM for output signaling, and GPIO for system inputs and LED feedback. After a short warm-up period to let the sensor stabilize, the microcontroller performs burst sampling on the RA7 analog input and applies a smoothing filter to produce a clean and stable moisture reading.

The firmware uses a simple state machine with three modes—Waiting, Transmitting, and Error. In normal operation, the system monitors a digital request line on RB4. When no request is active, the device stays in a low-activity wait state and sends periodic status logs. When a request signal is received, the controller calculates a corresponding PWM duty cycle based on the moisture level and sends that value out through the high-speed PWM channel for downstream processing, while also providing fast LED feedback for visibility.

If the ADC reading drops below a defined fault threshold, the system enters an Error state, disables PWM output, and logs a fault message to help identify sensor issues. Throughout operation, the code maintains steady communication over UART, handles LED heartbeat patterns for clear user feedback, smooths sensor noise, and ensures consistent and reliable performance in the field.

The microcontroller code as a project zip download is available [*here*](https://github.com/user-attachments/files/23916973/Soil_Sensor.zip)
