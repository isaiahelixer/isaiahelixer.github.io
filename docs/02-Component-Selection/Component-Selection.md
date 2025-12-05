---
title: Component Selection
tags:
- Smart Irrigation Sensor Subsystem
- Power and Sensor Board
---

# Component Selection

Subsystem board powered from a 9 V wall adapter input through a 5 V regulator.  
Includes a PIC18F16Q41 Curiosity Nano microcontroller connected to:  
- Analog capacitive soil moisture sensor  
- MCP6004 op-amp  
- 8-pin connector for communication with other subsystem boards  

## Soil Moisture Sensor

**Table 1: Soil Moisture Sensor Comparison**

| **Solution** | **Pros** | **Cons** |
|---------------|-----------|-----------|
| ![](https://github.com/user-attachments/assets/66eeb141-3a8a-4a65-ba30-f9e865b20f8b)<br>**Option 1:** SEN0114 Soil Moisture Sensor Module<br>$2.70 — each<br>[Product Link](https://www.digikey.com/en/products/detail/dfrobot/SEN0114/6588525) | *Simple analog output*<br>*Low cost*<br>*Compact design* | *Corrodes over time if left in soil*<br>*Requires calibration for accuracy* |
| ![](https://github.com/user-attachments/assets/d213c9d3-1647-4f78-83f7-da6f1a7d93ea)<br>**Option 2:** ST0160 Capacitive Soil Moisture Sensor V2.0<br>$8.60 — each<br>[Product Link](https://www.amazon.com/dp/B0F6N259HM) | *No corrosion (capacitive)*<br>*Stable analog readings*<br>*Low power consumption* | *More expensive than SEN0114*<br>*Slightly larger PCB footprint* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/930/342/MFG_314990620_sml.jpg)<br>**Option 3:** Industrial Soil Moisture & Temperature Sensor<br>$79 — each<br>[Product Link](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/314990620/16570933) | *Industrial-grade durability*<br>*Includes temperature output*<br>*Long-term outdoor reliability* | *High cost*<br>*Requires analog-to-current interface circuitry* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  
**Rationale:** Provides corrosion-free sensing with stable analog output for long-term outdoor monitoring while maintaining low cost and easy integration with the PIC ADC.

## Voltage Regulator

**Table 2: Voltage Regulator Comparison**

| **Solution** | **Pros** | **Cons** |
|---------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/415/110/497%7ETO220-3TO220AB%7E%7E3_sml.jpg)<br>**Option 1:** LM7805 Linear Regulator<br>$0.64 — each<br>[Product Link](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient dropping 9 V → 5 V*<br>*Generates heat at higher currents* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/809/296%7E4040001-2%7ELP%7E3_sml%28200x200%29.jpg)<br>**Option 2:** UA78L05ACLP Regulator<br>$1.69 — each<br>[Product Link](https://www.digikey.com/en/products/detail/texas-instruments/UA78L05ACLP/13465029) | *Compact package*<br>*Low quiescent current*<br>*Ideal for ≤100 mA loads* | *Limited to 100 mA output*<br>*Not for high-current systems* |
| ![](https://github.com/user-attachments/assets/89f2e40e-c528-4b86-9d24-e24a1fa8eebd)<br>**Option 3:** N7805-1CW DC/DC Converter (Mean Well)<br>$4.84 — each<br>[Product Link](https://www.digikey.com/en/products/detail/mean-well-usa-inc/N7805-1CW/22119070) | *High efficiency (93%)*<br>*Wide 8–36 V input range*<br>*Compact enclosed design*<br>*Low heat output* | *Higher cost than LM7805*<br>*Less common in local stock* |

**Choice:** Option 1 — LM7805 Linear Regulator  
**Rationale:** Already supplied and sufficient for the system’s moderate current demand. The N7805-1CW offers higher efficiency but is unnecessary for this subsystem.

## Operational Amplifier

**Table 4: Operational Amplifier Comparison**

| **Solution** | **Pros** | **Cons** |
|---------------|-----------|-----------|
| ![](https://github.com/user-attachments/assets/31820770-4b2e-4d94-a2e6-3f3f1526158e)<br>**Option 1:** MCP6004 Quad Op-Amp (Through-Hole)<br>$1.25 — each<br>[Product Link](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | *Rail-to-rail I/O*<br>*Low quiescent current (23 mA max)*<br>*Operates from single 5 V supply*<br>*Four amplifiers per package* | *Through-hole package larger than SMD*<br>*Limited bandwidth for high-speed signals* |

**Choice:** Option 1 — MCP6004 Op-Amp  
**Rationale:** Already supplied; provides four precision amplifiers suitable for low-power sensor signal conditioning and stable analog performance.

## Summary Table of Final Major Components

| **Component Category** | **Final Component Selected** | **Reason for Selection** |
|------------------------|------------------------------|---------------------------|
| **Microcontroller** | PIC18F16Q41 Curiosity Nano | Provided to us, includes onboard debugger, and reliable ADC for moisture sensing. |
| **Soil Moisture Sensor** | DIY Capacitive Soil Moisture Sensor | Easy RC circuit, low-power, and provides a stable analog signal for PIC ADC processing. |
| **Operational Amplifier** | MCP6004 Quad Op-Amp | Rail-to-rail operation and low power, suitable for filtering and amplifying the sensor output. |
| **Voltage Regulator** | LM7805 Linear Regulator (TO-220) | Supplied to us, simple, and stable 5 V regulation for the subsystem. |
| **External Power Source** | 9 V DC Wall Adapter (≥3 A) | Provides more than enough current to power the 5 V subsystem load. |
| **Subsystem Connectivity** | 8-Pin Board-to-Board Connector | Provides communication and signal routing to teammate subsystem boards. |


