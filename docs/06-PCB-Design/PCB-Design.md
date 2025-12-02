---
title: Sensor Subsystem PCB Design
---
## Overview
This PCB design supports the Smart Irrigation Subsystem Board by integrating power regulation, signal processing, and communication functions onto a single compact layout. The board accepts a DC 9V wall adapter input and uses an LM7805 linear regulator with diode and fuse protection to supply a stable 5V rail. This regulated voltage powers the PIC18F57Q43 Curiosity Nano microcontroller and the MCP6004 op-amp, which amplifies and filters the signal from a custom-built capacitive soil moisture sensor. The PCB layout includes organized ground and power planes for noise reduction, onboard filtering components, expansion headers for system scalability, and a ribbon connector for reliable inter-board communication.  

<img width="2489" height="768" alt="PCB Front" src="https://github.com/user-attachments/assets/a797d63d-ed41-41a6-90f1-c61a3099f659" />  
*Figure 1: Showing the front of the board.*
<img width="2489" height="770" alt="PCB Back" src="https://github.com/user-attachments/assets/d3bf9030-d528-4e39-826e-8bbc1b9a2c91" />  
*Figure 2: Showing the back of the board.*
<img width="2232" height="755" alt="PCB 3D" src="https://github.com/user-attachments/assets/9463a6e6-2fb1-4aad-8a91-b56dc51c0dbe" />
*Figure 3: Showing the 3D veiw of the board.*  

## Resources
The PCB design as a PDF download is available [*here*](https://github.com/user-attachments/files/23871097/PCB.pdf), the Zip folder of the Gerber Files [*here*](https://github.com/user-attachments/files/23871074/IsaiahLaCombe101.zip), and the Zip folder of the Project Files [*here*](https://github.com/user-attachments/files/23870865/Subsystem.Schematic.Design.zip)

