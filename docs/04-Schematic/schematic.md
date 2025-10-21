---
title: Sensor Subsystem Schematic
---

## Overview

This schematic is designed to support the Smart Irrigation Subsystem Board. It regulates a 9 V input down to 5 V using an LM7805 linear regulator with diode and fuse protection. The 5 V rail powers a PIC18F57Q43 Curiosity Nano microcontroller that monitors soil moisture (ST0160 via MCP6004 op-amp), temperature/humidity (SHT31-D via I²C), and rainfall (SEN0545 via UART). The system provides stable sensor inputs, onboard filtering, and a ribbon connector for inter-board communication.”


![schematic](file:///C:/Users/isaia/Documents/EGR%20304/Subsystem%20Schematic%20Design/Subsystem%20Schematic%20Design.pdf){style width:"350" height:"300;"}
**Figure 1:** Showing the sensors, microcontroller, and power delivery schematic.


## Resouces

The schematic as a PDF download is available [*here*](ExampleSchematic.pdf), and the Zip folder of the project [*here*](dummyZip.zip).
