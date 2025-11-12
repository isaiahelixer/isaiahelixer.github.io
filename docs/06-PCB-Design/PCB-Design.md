---
title: Sensor Subsystem PCB Design
---
## Overview
This PCB design supports the Smart Irrigation Subsystem Board by integrating power regulation, signal processing, and communication functions onto a single compact layout. The board accepts a DC 9V wall adapter input and uses an LM7805 linear regulator with diode and fuse protection to supply a stable 5V rail. This regulated voltage powers the PIC18F57Q43 Curiosity Nano microcontroller and the MCP6004 op-amp, which amplifies and filters the signal from a custom-built capacitive soil moisture sensor. The PCB layout includes organized ground and power planes for noise reduction, onboard filtering components, expansion headers for system scalability, and a ribbon connector for reliable inter-board communication.

<img width="2193" height="691" alt="Screenshot 2025-11-11 180942" src="https://github.com/user-attachments/assets/f42e4457-7d2d-4006-80d3-bb7fa32aa217" />
*Figure 1: Showing the front of the board.*  
<img width="2194" height="690" alt="Screenshot 2025-11-11 181010" src="https://github.com/user-attachments/assets/620a9d1e-b773-49de-8e23-42f5a2d35371" />
*Figure 2: Showing the back of the board.*  
<img width="2490" height="771" alt="Screenshot 2025-11-11 132253" src="https://github.com/user-attachments/assets/bbabcb18-9541-49d8-b8c7-fa01d32d3f07" />
*Figure 3: Showing the 3D design of the board.*  

## Resources

The PCB design as a PDF download is available [*here*](https://github.com/user-attachments/files/23489958/png2pdf.pdf), the Zip folder of the Gerber Files [*here*](https://github.com/user-attachments/files/23489894/IsaiahLaCombe101.zip), and the Zip folder of the Project Files [*here*](https://github.com/user-attachments/files/23490049/Subsystem.Schematic.Design.zip)

