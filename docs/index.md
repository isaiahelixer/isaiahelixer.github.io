---
title: Welcome Here
tags:
- tag1
- tag2
---
<center>
<font size= "6"> Welcome</font><br>
as part of<br>
<font size= "8"> Projectz</font><br>
for<br>
<font size= "5"> Team 101 </font><br>

**Submission: 11/10/2025**
</center>

## Introduction

This datasheet provides a complete overview of the Sensor Subsystem Board used in the Smart Irrigation System project. The subsystem is designed to measure soil moisture levels and send that data to the main control unit in turn helping the system make decisions about when to water.  

The document outlines how the subsystem works, what components were selected, and how power is managed to ensure reliable performance. It includes the block diagram, component selections, bill of materials (BOM), schematic, power budget, PCB design and appendix for full reference listed above.  

## Project Summary

The Smart Irrigation System is a water-efficient lawn watering project designed by Team 101. Its goal is to help homeowners and renters maintain healthy lawns while reducing water waste and cost. The system automatically monitors soil conditions and water usage to decide when watering is needed.  

The project is built around four main subsystems — Control, Sound Feedback, Sensor, and Motor — each using a PIC18F57Q43 Curiosity Nano microcontroller. These subsystems work together to create a modular watering system that can function both online and offline.  

My subsystem Sensor Board plays a key role by measuring soil moisture levels and sending accurate data to the Control Board. This data allows the system to decide when to turn the pump on or off working to create efficient and automatic lawn irrigation.  

For a full overview of the team project, including our mission statement, user needs, and system design, you can visit the [Team Report Appendix](https://egr304-2025-f-101.github.io/team101.github.io/Appendix/).

## My Contribution

My part in this project focuses on the Sensor Subsystem which handles data collection and signal processing for the soil moisture readings. I designed the board to convert a 9V supply down to 5V using an LM7805 regulator and included diode and fuse protection for safe operation. The board uses an MCP6004 op-amp to condition the sensor signal before it’s read by the PIC18F57Q43 microcontroller.  

The data is then processed and converted, then sent to the Control Subsystem through an 8-pin connector to support other subsystems. My design ensures the sensor data is clean, stable, and accurate which is very important for the irrigation logic to function properly.  

To review the materials and components used to build this subsystem, visit the [BOM](https://isaiahelixer.github.io/03-BOM/BOM/) section of this datasheet.  
For information on circuit layout and wiring, see the [Schematic](https://isaiahelixer.github.io/04-Schematic/schematic/) section. For information on the PCB design, see the [PCB Design](https://isaiahelixer.github.io/06-PCB-Design/PCB-Design/) section.  
For power usage and regulation details, check the [Power Budget](https://isaiahelixer.github.io/05-Power-Budget/Power-Budget/) section.
