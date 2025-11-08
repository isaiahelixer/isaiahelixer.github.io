---
title: Sensor Subsystem Schematic
---

## Overview
This schematic is designed to support the Smart Irrigation Subsystem Board. It regulates a DC 9V wall adapter input down to 5V using an LM7805 linear regulator with diode and fuse protection. The 5V rail powers a PIC18F57Q43 Curiosity Nano microcontroller that monitors capacitive soil moisture sensor using an MCP6004 op-amp to amplify/filter the signal. The system provides stable sensor inputs, onboard filtering, and a ribbon connector for inter-board communication.”

## Subsystem Schematic Design
<img width="1279" height="970" alt="Screenshot 2025-11-07 172855" src="https://github.com/user-attachments/assets/41f80fa1-ed91-4f3b-ac7f-37e76b07ac59" />

*Figure 1:* Showing the sensors, microcontroller, signal amplifier, and power delivery schematic.
## Resources

The schematic as a PDF download is available [*here*](https://github.com/user-attachments/files/23427434/Subsystem.Schematic.Design.pdf), and the Zip folder of the project [*here*](https://github.com/user-attachments/files/23427436/Sensor.Subsystem.zip)
