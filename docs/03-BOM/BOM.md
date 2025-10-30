---
title: Bill of Materials
tags:
- Smart Irrigation Subsystem
- Power and Sensor Board
---

## Overview

The following Bill of Materials (BOM) lists all major electronic and passive components used in the Smart Irrigation Subsystem Board.  
The system operates from a 9 V input using an LM7805 linear regulator to provide a regulated 5 V rail powering the PIC18F16Q41 Curiosity Nano, MCP6004 op-amp, and ST0160 capacitive soil moisture sensor.  
The design also includes decoupling capacitors, diodes for reverse protection, resistors, fuses, jumpers, and test points for debugging and signal monitoring.

---

## Bill of Materials (BOM)

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Datasheet Link** |
|:---------------------------|:-------:|:--------------:|:---------------:|:----------------:|:------------------:|
| PIC18F16Q41 Curiosity Nano Microcontroller Board | 1 | $15.00 | $15.00 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F16Q41-Data-Sheet-40002214C.pdf) |
| LM7805 Linear Regulator (5V, TO-220) | 1 | $0.64 | $0.64 | STMicroelectronics | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) |
| MCP6004 Quad Op-Amp (Through-Hole) | 1 | $1.25 | $1.25 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/21733j.pdf) |
| ST0160 Capacitive Soil Moisture Sensor V2.0 | 1 | $8.60 | $8.60 | SunFounder | [Datasheet](https://github.com/sunfounder/SunFounder_Soil_Moisture_Sensor/blob/master/README.md) |
| 2x4 Connector Header | 1 | $0.20 | $0.20 | Generic | — |
| 0.33 µF Ceramic Capacitor | 1 | $0.10 | $0.10 | KEMET | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) |
| 0.1 µF Ceramic Capacitor | 5 | $0.05 | $0.25 | KEMET | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) |
| 1 µF Ceramic Capacitor | 1 | $0.10 | $0.10 | KEMET | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) |
| Diode 1N4007 (Rectifier) | 1 | $0.06 | $0.06 | ON Semiconductor | [Datasheet](https://www.onsemi.com/pdf/datasheet/1n4001-d.pdf) |
| Red LED (Indicator) | 1 | $0.08 | $0.08 | Everlight | [Datasheet](https://www.everlight.com/file/ProductFile/204-10SURD-S530-A3.pdf) |
| Blue LED (Debug) | 1 | $0.08 | $0.08 | Everlight | [Datasheet](https://www.everlight.com/file/ProductFile/204-10SURD-S530-A3.pdf) |
| Fuse 1000 mA | 1 | $0.25 | $0.25 | Bel Fuse | [Datasheet](https://belfuse.com/resources/datasheets/circuitprotection/ds-cp-0685h.pdf) |
| Fuse 5 mA | 1 | $0.25 | $0.25 | Bel Fuse | [Datasheet](https://belfuse.com/resources/datasheets/circuitprotection/ds-cp-0685h.pdf) |
| Barrel Jack (9V Power) | 1 | $0.60 | $0.60 | CUI Devices | [Datasheet](https://www.cuidevices.com/product/resource/pj-102ah.pdf) |
| 1x4 Debug Header | 1 | $0.25 | $0.25 | Generic | — |
| 2-Pin Jumper | 4 | $0.05 | $0.20 | Generic | — |
| Slide Switch (Wuerth 450301014042) | 1 | $1.80 | $1.80 | Würth Elektronik | [Datasheet](https://www.we-online.com/catalog/datasheet/450301014042.pdf) |
| Debug Button (Momentary SW) | 1 | $0.15 | $0.15 | Omron | [Datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-b3f.pdf) |
| 220 Ω Resistor | 2 | $0.02 | $0.04 | Yageo | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) |
| 100 Ω Resistor | 1 | $0.02 | $0.02 | Yageo | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) |
| 10 kΩ Resistor | 1 | $0.02 | $0.02 | Yageo | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) |
| Test Points | 3 | $0.05 | $0.15 | Keystone | [Datasheet](https://www.keyelco.com/product-pdf.cfm?p=1200) |

---

**Total Estimated Cost:** ≈ **$30.29**

---


