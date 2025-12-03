---
title: Microcontroller Code
---
## Overview
This section covers the core firmware that runs the Smart Irrigation Subsystem. The microcontroller code handles all real-time decisions by reading sensor inputs, processing data, and controlling system outputs. The program initializes the PIC18F57Q43 Curiosity Nano, sets up ADC channels for the capacitive soil moisture sensor, and manages timing routines for stable measurements. It also communicates with the main controller through a serial interface, sending moisture readings and receiving irrigation commands. The code ensures reliable operation by using debouncing, averaging filters, and clear state-based logic for pump activation, error handling, and system updates.
