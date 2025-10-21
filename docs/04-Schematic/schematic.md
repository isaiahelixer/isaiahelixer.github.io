---
title: Sensor Subsystem Schematic
---

## Overview

This schematic is designed to support the Smart Irrigation Subsystem Board. It regulates a 9 V input down to 5 V using an LM7805 linear regulator with diode and fuse protection. The 5 V rail powers a PIC18F57Q43 Curiosity Nano microcontroller that monitors soil moisture (ST0160 via MCP6004 op-amp), temperature/humidity (SHT31-D via I²C), and rainfall (SEN0545 via UART). The system provides stable sensor inputs, onboard filtering, and a ribbon connector for inter-board communication.”


![Subsystem Design schematic](https://github.com/user-attachments/assets/70585855-dbef-4f42-9997-7f19edc4834f){style width:"350" height:"300;"}
**Figure 1:** Showing the sensors, microcontroller, and power delivery schematic.


## Resources

The schematic as a PDF download is available [*here*](https://drive.google.com/file/d/1_huN4Ivck--dMZcGOye8KnJlNY8wMjda/view?usp=sharing), and the Zip folder of the project [*here*]().
