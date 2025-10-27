---
title: Sensor Subsystem Schematic
---

## Overview

This schematic is designed to support the Smart Irrigation Subsystem Board. It regulates a DC 9V wall adapter input down to 5 V using an LM7805 linear regulator with diode and fuse protection. The 5 V rail powers a PIC18F57Q43 Curiosity Nano microcontroller that monitors capacitive soil moisture ST0160 using an MCP6004 op-amp to amplify/filter the signal. The system provides stable sensor inputs, onboard filtering, and a ribbon connector for inter-board communication.”


## Subsystem Schematic Design
*Figure 1:* Showing the sensors, microcontroller, signal amplifier, and power delivery schematic.
<img width="3300" height="2550" alt="Subsystem Schematic Design" src="https://github.com/user-attachments/assets/80f8975d-74ef-4791-8990-ff97184f6fb8" />



## Resources

The schematic as a PDF download is available [*here*](https://github.com/user-attachments/files/23157683/Subsystem.Schematic.Design.pdf), and the Zip folder of the project [*here*](https://github.com/user-attachments/files/23157733/Subsystem.Schematic.Design.zip).
