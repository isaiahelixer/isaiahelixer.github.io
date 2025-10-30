---
title: Bill of Materials
tags:
- Smart Irrigation Sensor Subsystem
- Power and Sensor Board
---

## Overview

The following Bill of Materials lists all major electronic and passive components used in my sensor subsystem board.  
The system operates from a 9 V input using an LM7805 linear regulator to provide a regulated 5 V rail powering the PIC18F57Q43 Curiosity Nano, MCP6004 op-amp, and ST0160 capacitive soil moisture sensor.  
The design also includes decoupling capacitors, diodes for reverse protection, resistors, fuses, jumpers, and test points for debugging and signal monitoring.

## Bill of Materials 

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Datasheet Link** |
|:---------------------------|:-------:|:--------------:|:---------------:|:----------------:|:------------------:|
| PIC18F57Q43 Curiosity Nano Microcontroller Board | 1 | $10.19 | $10.19 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/UserGuides/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf) |
| LM7805 Linear Regulator (5V, TO-220) | 1 | $1.80 | $1.80 | Texas Instruments | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7800.pdf) |
| MCP6004 Quad Op-Amp (Through-Hole) | 1 | $0.59 | $0.59 | Microchip Technology | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6001-1R-1U-2-4-1-MHz-Low-Power-Op-Amp-DS20001733L.pdf) |
| ST0160 Capacitive Soil Moisture Sensor V2.0 | 1 | $8.60 | $8.60 | SunFounder | [Datasheet](https://rajguruelectronics.com/Product/5538/Capacitive%20Soil%20Moisture%20Sensor%20V2(1).0.pdf) |
| 2x4 CONN Connector Header | 1 | $0.27 | $0.27 | Adam Tech | [Datasheet](https://app.adam-tech.com/products/download/data_sheet/203218/bhr-xx-vua-data-sheet.pdf) |
| 0.33 µF Ceramic Capacitor | 1 | $0.44 | $0.44 | KEMET | [Datasheet](https://www.yageogroup.com/content/datasheet/asset/file/KEM_C1051_GOLDMAX_Z5U) |
| 0.1 µF Ceramic Capacitor | 5 | $0.47 | $2.35 | KEMET | [Datasheet](https://content.kemet.com/datasheets/KEM_C1050_GOLDMAX_X7R.pdf) |
| 1 µF Ceramic Capacitor | 1 | $0.28 | $0.28 | KEMET | [Datasheet](https://www.yageogroup.com/content/datasheet/asset/file/KEM_C1051_GOLDMAX_Z5U) |
| Diode 1N4007 (Rectifier) | 1 | $0.19 | $0.19 | Onsemi | [Datasheet](https://www.onsemi.com/pdf/datasheet/1n4001-d.pdf) |
| Red LED (Indicator) | 1 | $0.47 | $0.47 | SunLED | [Datasheet](https://www.sunledusa.com/products/spec/XLM2CRK11W.pdf) |
| Blue LED (Debug) | 1 | $0.59 | $0.59 | QT Brightek | [Datasheet](https://www.qt-brightek.com/datasheet/QBL8XX60D.pdf) |
| Fuse 1000 mA | 1 | $0.98 | $0.98 | Bourns Inc | [Datasheet](https://www.bourns.com/pdfs/SF-0603SP.pdf) |
| Fuse 20 mA | 1 | $0.72 | $0.72 | Schurter | [Datasheet](https://www.mouser.com/datasheet/3/386/1/typ_SPT_3.6x10.pdf) |
| Barrel Jack (9V Power) | 1 | $0.76 | $0.76 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/pj-102ah.pdf) |
| 1x4 Debug Header | 1 | $0.10 | $0.10 | Adam Tech | [Datasheet](https://app.adam-tech.com/products/download/data_sheet/201605/ph1-xx-ua-data-sheet.pdf) |
| 2-Pin Jumper | 4 | $0.28 | $1.12 | Würth Elektronik | [Datasheet](https://www.we-online.com/components/products/datasheet/60900213421.pdf) |
| Slide Switch | 1 | $0.83 | $0.83 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/slw-1276864-4a-d.pdf) |
| Debug Button (Momentary SW) | 1 | $0.10 | $0.10 | Same Sky | [Datasheet](https://www.sameskydevices.com/product/resource/ts02.pdf) |
| 1/2 Watt 220 Ω Resistor | 2 | $0.10 | $0.20 | Yageo | [Datasheet](https://www.yageogroup.com/content/Resource%20Library/Datasheet/YAGEO-MFR_DATASHEET.pdf) |
| 1/2 Watt 100 Ω Resistor | 1 | $0.10 | $0.10 | Yageo | [Datasheet](https://www.yageogroup.com/content/Resource%20Library/Datasheet/YAGEO-MFR_DATASHEET.pdf) |
| 1/2 Watt 10 kΩ Resistor | 1 | $0.11 | $0.11 | Yageo | [Datasheet](https://www.yageogroup.com/content/Resource%20Library/Datasheet/YAGEO-MFR_DATASHEET.pdf) |
| Test Points | 9 | $0.39 | $3.51 | Keystone | [Datasheet](https://www.keyelco.com/userAssets/file/M65p56.pdf) |

**Total Estimated Cost:** ≈ **$33.55**

A complete Excel version of this Bill of Materials, including Manufacturer Part #, Vendor Links, Supplier Part #, and Schematic Reference Designators that can be accessed here:  
📂 [Smart Irrigation Sensor Subsystem BOM](sandbox:/mnt/data/Smart_Irrigation_BOM.xlsx)


