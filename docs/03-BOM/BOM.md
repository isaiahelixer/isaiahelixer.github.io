---
title: Bill of Materials
tags:
- Smart Irrigation Sensor Subsystem
- Power and Sensor Board
---

## Overview

The following Bill of Materials lists all major electronic and passive components used in my sensor subsystem board.  

The system operates from a 9 V input using an LM7805 linear regulator to provide a regulated  
5V rail powering the PIC18F57Q43 Curiosity Nano, MCP6004 op-amp, and DIY RC capacitive soil moisture sensor.  

The design also includes decoupling capacitors, diodes for reverse protection, resistors, fuses, jumpers, and test points for debugging and signal monitoring.

## Bill of Materials

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Datasheet Link** |
|:---------------------------|:-------:|:--------------:|:---------------:|:----------------:|:------------------:|
| PIC18F57Q43 Curiosity Nano | 1 | $10.19 | $10.19 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/UserGuides/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf) |
| LM7805 Linear Regulator (5 V, TO-220) | 1 | $1.80 | $1.80 | Texas Instruments | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7800.pdf) |
| MCP6004 Quad Op-Amp (Through-Hole) | 1 | $0.59 | $0.59 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) |
| 2 x 420mm Titanium Rods | 1 | $9.99 | $9.99 | Uxcell | [Datasheet](https://3dedge.com.br/wp-content/uploads/2022/12/Titanium-TC4-Data-sheet.pdf) |
| 2×4 CONN Connector Header | 1 | $1.51 | $1.51 | Molex | [Datasheet](https://www.molex.com/en-us/products/part-detail/702460802?display=pdf) |
| 0.33 µF Ceramic Capacitor | 1 | $0.44 | $0.44 | KEMET | [Datasheet](https://www.yageogroup.com/content/datasheet/asset/file/KEM_C1051_GOLDMAX_Z5U) |
| 0.1 µF Ceramic Capacitor | 5 | $0.47 | $2.35 | KEMET | [Datasheet](https://www.yageogroup.com/content/datasheet/asset/file/KEM_C1051_GOLDMAX_Z5U) |
| 47 nF Ceramic Capacitor | 1 | $0.86 | $0.86 | KEMET | [Datasheet](https://content.kemet.com/datasheets/KEM_C1050_GOLDMAX_X7R.pdf) |
| Diode 1N4007 (Rectifier) | 1 | $0.19 | $0.19 | Onsemi | [Datasheet](https://www.onsemi.com/pdf/datasheet/1n4001-d.pdf) |
| Red LED (Indicator) | 1 | $0.47 | $0.47 | Rohm Semiconductor | [Datasheet](https://www.rohm.com/datasheet?p=SLR-56VC&dist=Digi-key) |
| Blue LED (Debug) | 1 | $0.59 | $0.59 | Marktech Optoelectronics | [Datasheet](https://specs.marktechopto.com/pdf/products/datasheet/MT5470-BL.pdf) |
| Fuse 700 mA | 1 | $0.71 | $0.71 | Littelfuse Inc. | [Datasheet](https://www.littelfuse.com/assetdocs/littelfuse_fuse_235_datasheet.pdf?assetguid=79b16c87-8337-4c9c-96d1-6ac09ce4e440) |
| Barrel Jack (9 V Power) | 1 | $0.76 | $0.76 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/pj-031ch.pdf) |
| 1×4 Debug Header | 1 | $0.10 | $0.10 | Adam Tech | [Datasheet](https://app.adam-tech.com/products/download/data_sheet/201605/ph1-xx-ua-data-sheet.pdf) |
| 2-Pin Jumper | 3 | $0.28 | $0.84 | Würth Elektronik | [Datasheet](https://www.we-online.com/components/products/datasheet/60900213421.pdf) |
| Slide Switch | 1 | $0.83 | $0.83 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/slw-1276864-4a-d.pdf) |
| Debug Button (Momentary SW) | 1 | $0.10 | $0.10 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/ts02.pdf) |
| 1/2 Watt 220 Ω Resistor | 2 | $0.10 | $0.20 | YAGEO | [Datasheet](https://www.yageogroup.com/content/Resource%20Library/Datasheet/YAGEO-MFR_DATASHEET.pdf) |
| 1/2 Watt 10 kΩ Resistor | 2 | $0.11 | $0.22 | Stackpole Electronics Inc. | [Datasheet](https://www.seielect.com/catalog/SEI-RNF_RNMF.pdf) |
| 1/2 Watt 1 kΩ Resistor | 1 | $0.31 | $0.31 | Stackpole Electronics Inc. | [Datasheet](https://www.seielect.com/catalog/SEI-ASR_ASRM.pdf) |
| 1/2 Watt 1MΩ Resistor | 1 | $0.10 | $0.10 | YAGEO | [Datasheet](https://www.yageogroup.com/content/Resource%20Library/Datasheet/YAGEO-MFR_DATASHEET.pdf) |
| Test Points | 8 | $0.39 | $3.12 | Keystone Electronics | [Datasheet](https://www.keyelco.com/userAssets/file/M65p56.pdf) |

**Total Estimated Cost:** ≈ **$37.39**

<img width="2462" height="662" alt="Screenshot 2025-11-06 231102" src="https://github.com/user-attachments/assets/89fa4673-2e89-4dc2-b768-98a9ebf4d20f" />


A downloadable Excel version of this Bill of Materials, including Manufacturer Part #, Vendor Links, Supplier Part #, and Schematic Reference Designators can be accessed here:  
📂 [Smart Irrigation Sensor Subsystem BOM.xlsx](https://arizonastateu-my.sharepoint.com/:x:/g/personal/ilacombe_sundevils_asu_edu/EYToEqM0qnFFsyiPlOJMnzIBPYc3zt9iHRCOJaCWnhvnrA?e=ITvCyg)


