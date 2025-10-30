---
title: Bill of Materials
tags:
- Smart Irrigation Subsystem
- Power and Sensor Board
---

## Overview

The following Bill of Materials (BOM) lists all major electronic and passive components used in the Smart Irrigation Subsystem Board.  
The design operates from a 9 V input using an LM7805 linear regulator to supply regulated 5 V power to the PIC18F16Q41 Curiosity Nano microcontroller, MCP6004 op-amp, and ST0160 capacitive soil moisture sensor.  
Additional components include protection diodes, capacitors for decoupling and filtering, LEDs for debugging, jumpers, and test points for signal access.

---

## Bill of Materials (BOM)

*Table 1: Complete Bill of Materials for Smart Irrigation Subsystem Board*

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer #** | **Vendor Link** | **Datasheet Link** | **Schematic Reference Designators** |
|:---------------------------|:-------:|:---------------:|:---------------:|:------------------|:------------------|:----------------|:------------------|:----------------|
| PIC18F16Q41 Curiosity Nano Microcontroller Board | 1 | $15.00 | $15.00 | Microchip Technology | DM164150 | [Microchip Product Page](https://www.microchip.com/en-us/development-tool/dm164150) | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F16Q41-Data-Sheet-40002214C.pdf) | U1 |
| LM7805 Linear Regulator (5V, TO-220) | 1 | $0.64 | $0.64 | STMicroelectronics | L7805ACV | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962) | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | LM7805_IL_5V_Reg1 |
| MCP6004 Quad Op-Amp (Through-Hole) | 1 | $1.25 | $1.25 | Microchip Technology | MCP6004-I/P | [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/21733j.pdf) | MCP6004_IL? |
| ST0160 Capacitive Soil Moisture Sensor V2.0 | 1 | $8.60 | $8.60 | SunFounder | ST0160 | [DigiKey](https://www.digikey.com/en/products/detail/sunfounder/ST0160/22116813) | [Datasheet](https://github.com/sunfounder/SunFounder_Soil_Moisture_Sensor/blob/master/README.md) | ST0160_IL? |
| 2x4 Connector Header | 1 | $0.20 | $0.20 | Generic | 2x4_CONN | — | — | 2x4_CONN_Connector_IL? |
| 0.33 µF Ceramic Capacitor | 1 | $0.10 | $0.10 | KEMET | C0805C334K5RACTU | [DigiKey](https://www.digikey.com/en/products/detail/kemet/C0805C334K5RACTU/2200105) | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) | C1 |
| 0.1 µF Ceramic Capacitor | 5 | $0.05 | $0.25 | KEMET | C0805C104K5RACTU | [DigiKey](https://www.digikey.com/en/products/detail/kemet/C0805C104K5RACTU/2200087) | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) | C2, C3, C4, C5, C8 |
| 1 µF Ceramic Capacitor | 1 | $0.10 | $0.10 | KEMET | C0805C105K4RACTU | [DigiKey](https://www.digikey.com/en/products/detail/kemet/C0805C105K4RACTU/2200099) | [Datasheet](https://content.kemet.com/datasheets/KEM_C1004_X7R_SMD.pdf) | C9 |
| Diode 1N4007 (Rectifier) | 1 | $0.06 | $0.06 | ON Semiconductor | 1N4007RLG | [DigiKey](https://www.digikey.com/en/products/detail/onsemi/1N4007RLG/458780) | [Datasheet](https://www.onsemi.com/pdf/datasheet/1n4001-d.pdf) | D1 |
| Red LED (Indicator) | 1 | $0.08 | $0.08 | Everlight | 204-10SURD/S530-A3 | [DigiKey](https://www.digikey.com/en/products/detail/everlight-electronics-co-ltd/204-10SURD-S530-A3/270563) | [Datasheet](https://www.everlight.com/file/ProductFile/204-10SURD-S530-A3.pdf) | D2 |
| Debug LED | 1 | $0.08 | $0.08 | Everlight | 204-10SURD/S530-A3 | [DigiKey](https://www.digikey.com/en/products/detail/everlight-electronics-co-ltd/204-10SURD-S530-A3/270563) | [Datasheet](https://www.everlight.com/file/ProductFile/204-10SURD-S530-A3.pdf) | D3 |
| Fuse 1000 mA | 1 | $0.25 | $0.25 | Bel Fuse | 0685H1000-01 | [DigiKey](https://www.digikey.com/en/products/detail/bel-fuse-inc/0685H1000-01/4397678) | [Datasheet](https://belfuse.com/resources/datasheets/circuitprotection/ds-cp-0685h.pdf) | F1 |
| Fuse 5 mA | 1 | $0.25 | $0.25 | Bel Fuse | 0685H005-01 | [DigiKey](https://www.digikey.com/en/products/detail/bel-fuse-inc/0685H005-01/4397672) | [Datasheet](https://belfuse.com/resources/datasheets/circuitprotection/ds-cp-0685h.pdf) | F2 |
| Barrel Jack with Switch | 1 | $0.60 | $0.60 | CUI Devices | PJ-102AH | [DigiKey](https://www.digikey.com/en/products/detail/cui-devices/PJ-102AH/96454) | [Datasheet](https://www.cuidevices.com/product/resource/pj-102ah.pdf) | J1 |
| Debug Header | 1 | $0.25 | $0.25 | Generic | DEBUG_HEADER | — | — | J2 |
| 2-Pin Jumper | 4 | $0.05 | $0.20 | Generic | JP | — | — | JP1, JP2, JP3, JP4 |
| Slide Switch (Wuerth 450301014042) | 1 | $1.80 | $1.80 | Würth Elektronik | 450301014042 | [DigiKey](https://www.digikey.com/en/products/detail/wurth-elektronik/450301014042/9926645) | [Datasheet](https://www.we-online.com/catalog/datasheet/450301014042.pdf) | SlideSwitch? |
| Debug Button (Momentary SW) | 1 | $0.15 | $0.15 | Omron | B3F-1000 | [DigiKey](https://www.digikey.com/en/products/detail/omron-electronics-inc-emc-div/B3F-1000/108395) | [Datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-b3f.pdf) | SW1 |
| 220 Ω Resistor | 2 | $0.02 | $0.04 | Yageo | RC0805FR-07220RL | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0805FR-07220RL/726747) | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R1, R3 |
| 100 Ω Resistor | 1 | $0.02 | $0.02 | Yageo | RC0805FR-07100RL | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0805FR-07100RL/726720) | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R2 |
| 10 kΩ Resistor | 1 | $0.02 | $0.02 | Yageo | RC0805FR-0710KL | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0805FR-0710KL/726787) | [Datasheet](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R4 |
| GND Test Point | 1 | $0.05 | $0.05 | Keystone | 5011 | [DigiKey](https://www.digikey.com/en/products/detail/keystone-electronics/5011/255260) | [Datasheet](https://www.keyelco.com/product-pdf.cfm?p=1200) | TP1 |
| 5V Test Points | 3 | $0.05 | $0.15 | Keystone | 5011 | [DigiKey](https://www.digikey.com/en/products/detail/keystone-electronics/5011/255260) | [Datasheet](https://www.keyelco.com/product-pdf.cfm?p=1200) | TP4, TP5, TP13 |
| Soil Op-Amp Output Test Point | 1 | $0.05 | $0.05 | Keystone | 5011 | [DigiKey](https://www.digikey.com/en/products/detail/keystone-electronics/5011/255260) | [Datasheet](https://www.keyelco.com/product-pdf.cfm?p=1200) | TP6 |
| ADC Input Test Point | 1 | $0.05 | $0.05 | Keystone | 5011 | [DigiKey](https://www.digikey.com/en/products/detail/keystone-electronics/5011/255260) | [Datasheet](https://www.keyelco.com/product-pdf.cfm?p=1200) | TP7 |

---

**Total Estimated Cost:** ≈ **$30.29**

---

## Bill of Materials Example (as Image)
![](BOM-Screenshot.png){style width: "2000"}
**Figure 1:** Screenshot of Bill of Materials spreadsheet (optional visual version).

