---
title: Sensor Subsystem PCB Design
---
## Overview
This PCB design supports the Smart Irrigation Subsystem Board by integrating power regulation, signal processing, and communication functions onto a single compact layout. The board accepts a DC 9V wall adapter input and uses an LM7805 linear regulator with diode and fuse protection to supply a stable 5V rail. This regulated voltage powers the PIC18F57Q43 Curiosity Nano microcontroller and the MCP6004 op-amp, which amplifies and filters the signal from a custom-built capacitive soil moisture sensor. The PCB layout includes organized ground and power planes for noise reduction, onboard filtering components, expansion headers for system scalability, and a ribbon connector for reliable inter-board communication.

 <img width="1780" height="561" alt="PCB_Front" src="https://github.com/user-attachments/assets/d70744a4-3acb-42b6-949c-a39254618c03" />
*Figure 1: Showing the front of the board.*  
 <img width="1775" height="561" alt="PCB_Back" src="https://github.com/user-attachments/assets/cef372ab-c40e-4a5f-9693-b2ae584bf4bf" />
*Figure 2: Showing the back of the board.*  
 <img width="1531" height="510" alt="PCB_3D" src="https://github.com/user-attachments/assets/5214a9c9-ed6d-416f-bc5d-051b358c7a51" />
*Figure 3: Showing the 3D design of the board.*  

## Resources

The PCB design as a PDF download is available [*here*](https://github.com/user-attachments/files/23466374/Subsystem.Schematic.Design.pdf), the Zip folder of the Gerber Files [*here*](https://github.com/user-attachments/files/23466394/IsaiahLaCombe101.zip), and the Zip folder of the Project Files [*here*](https://github.com/user-attachments/files/23469348/Sensor.Subsystem.files.zip)

