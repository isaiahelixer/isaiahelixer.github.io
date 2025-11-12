---
title: Sensor Subsystem PCB Design
---
## Overview
This PCB design supports the Smart Irrigation Subsystem Board by integrating power regulation, signal processing, and communication functions onto a single compact layout. The board accepts a DC 9V wall adapter input and uses an LM7805 linear regulator with diode and fuse protection to supply a stable 5V rail. This regulated voltage powers the PIC18F57Q43 Curiosity Nano microcontroller and the MCP6004 op-amp, which amplifies and filters the signal from a custom-built capacitive soil moisture sensor. The PCB layout includes organized ground and power planes for noise reduction, onboard filtering components, expansion headers for system scalability, and a ribbon connector for reliable inter-board communication.

*Figure 1: Showing the front of the board.*  
![Screenshot 2025-11-11 182913](https://github.com/user-attachments/assets/96165025-5c4f-4b40-97ed-9e608c26fea3)
*Figure 2: Showing the back of the board.*  
![Screenshot 2025-11-11 182937](https://github.com/user-attachments/assets/2d8cbc56-ea50-4164-b607-a6c9fa61988b)
*Figure 3: Showing the 3D design of the board.*  
![Screenshot 2025-11-11 183107](https://github.com/user-attachments/assets/dd3df83f-5c5e-414f-9fc3-777b4ab06e9a)

## Resources
The PCB design as a PDF download is available [*here*](https://github.com/user-attachments/files/23489958/png2pdf.pdf), the Zip folder of the Gerber Files [*here*](https://github.com/user-attachments/files/23489894/IsaiahLaCombe101.zip), and the Zip folder of the Project Files [*here*](https://github.com/user-attachments/files/23490049/Subsystem.Schematic.Design.zip)

