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
|<img width="250" height="250" alt="Screenshot 2025-12-05 142235" src="https://github.com/user-attachments/assets/067f53bb-84fc-4f64-8438-9873440237e3" /><br>**Option 1:** DIY Resistive Copper/Steel Probe<br>$0.50 — each<br>*DIY-built from wires/nails* | *Very low cost*<br>*Simple voltage-divider interface*<br>*Easy to fabricate* | *Corrodes quickly in soil*<br>*Poor long-term stability*<br>*Requires recalibration* |
| <img width="250" height="250" alt="Screenshot 2025-12-05 141049" src="https://github.com/user-attachments/assets/b332ac6c-e4ca-45b7-8e63-54a251928135" /><br>**Option 2:** DIY Stainless-Steel Resistive Probe<br>$1.50 — each<br>*DIY using stainless rods/bolts* | *More corrosion-resistant than copper*<br>*Durable mechanical design*<br>*Still simple analog interface* | *Still corrodes slowly*<br>*Soil chemistry affects readings* |
| <img width="250" height="250" alt="Screenshot 2025-12-05 141651" src="https://github.com/user-attachments/assets/b51ff5d4-60ad-4ae1-a897-63575225aae5" /><br>**Option 3:** DIY PCB Capacitive Soil Sensor<br>$2–4 — each<br>*Fabricated or ordered PCB* | *No corrosion (non-contact sensing)*<br>*Stable long-term readings*<br>*Low power consumption* | *Requires PCB fabrication or ordering*<br>*Sensitivity depends on layout* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  
**Rationale:** Provides corrosion-free sensing with stable analog output for long-term outdoor monitoring while maintaining low cost and easy integration with the PIC ADC.

## Voltage Regulator

**Table 2: Voltage Regulator Comparison**

| **Solution** | **Pros** | **Cons** |
|---------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/415/110/497%7ETO220-3TO220AB%7E%7E3_sml.jpg)<br>**Option 1:** LM7805 Linear Regulator<br>$0.64 — each<br>[Product Link](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient dropping 9 V → 5 V*<br>*Generates heat at higher currents* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/809/296%7E4040001-2%7ELP%7E3_sml%28200x200%29.jpg)<br>**Option 2:** UA78L05ACLP Regulator<br>$1.69 — each<br>[Product Link](https://www.digikey.com/en/products/detail/texas-instruments/UA78L05ACLP/13465029) | *Compact package*<br>*Low quiescent current*<br>*Ideal for ≤100 mA loads* | *Limited to 100 mA output*<br>*Not for high-current systems* |
| <img width="200" height="200" alt="Screenshot 2025-12-05 142535" src="https://github.com/user-attachments/assets/f42cd1c6-66f5-481f-8207-0d845150bbab" /><br>**Option 3:** N7805-1CW DC/DC Converter (Mean Well)<br>$4.84 — each<br>[Product Link](https://www.digikey.com/en/products/detail/mean-well-usa-inc/N7805-1CW/22119070) | *High efficiency (93%)*<br>*Wide 8–36 V input range*<br>*Compact enclosed design*<br>*Low heat output* | *Higher cost than LM7805*<br>*Less common in local stock* |

**Choice:** Option 1 — LM7805 Linear Regulator  
**Rationale:** Already supplied and sufficient for the system’s moderate current demand. The N7805-1CW offers higher efficiency but is unnecessary for this subsystem.

## Operational Amplifier

**Table 4: Operational Amplifier Comparison**

| **Solution** | **Pros** | **Cons** |
|---------------|-----------|-----------|
| <img width="200" height="200" alt="Screenshot 2025-12-05 142417" src="https://github.com/user-attachments/assets/b1063e43-914e-45c0-835f-a7ebdf88fbd2" /><br>**Option 1:** MCP6004 Quad Op-Amp<br>$0.59 — each<br>[Product Link](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | *Rail-to-rail I/O*<br>*Low quiescent current*<br>*Operates from 5 V single supply*<br>*Four amps per package* | *Through-hole package takes more space*<br>*Limited bandwidth for fast signals* |
|<img width="200" height="200" alt="Screenshot 2025-12-05 142714" src="https://github.com/user-attachments/assets/0af626bd-bd1a-4e03-b055-ae3c11f23884" /><br>**Option 2:** MCP6024 Quad Op-Amp<br>$2.72 — each<br>[Product Link](https://www.digikey.com/en/products/detail/microchip-technology/MCP6024-I-P/417834?gclsrc=aw.ds&gad_source=1&gad_campaignid=20228387720&gbraid=0AAAAADrbLlgXsFbsfma99EMgt1hjWlxG0&gclid=Cj0KCQiAosrJBhD0ARIsAHebCNo42sJRNq7pd_p3qR2GxUZhzyr1IvkNuLgJJEWyxm9cKpmTgwIb6kMaAgq6EALw_wcB) | *Higher bandwidth than MCP6004*<br>*Rail-to-rail I/O*<br>*Good for faster signal conditioning* | *Slightly higher cost*<br>*More power consumption than MCP6004* |
|<img width="200" height="200" alt="Screenshot 2025-12-05 142843" src="https://github.com/user-attachments/assets/32c373c3-174a-403b-b894-f68828dbdce3" /><br>**Option 3:** TLV2374 Quad Op-Amp<br>$2.41 — each<br>[Product Link](https://www.digikey.com/en/products/detail/texas-instruments/TLV2374IN/413508?gclsrc=aw.ds&gad_source=1&gad_campaignid=20228387720&gbraid=0AAAAADrbLlgXsFbsfma99EMgt1hjWlxG0&gclid=Cj0KCQiAosrJBhD0ARIsAHebCNpv8ddaK9jiGKaLMNUOjc5NIupNYm57eTP3rzeC5kgycMvAU2WNKCoaAvxZEALw_wcB) | *Low noise performance*<br>*Rail-to-rail I/O*<br>*Great for precision sensing* | *Availability varies by distributor*<br>*Footprint changes based on package* |

**Choice:** Option 1 — MCP6004 Op-Amp  
**Rationale:** Already supplied; provides four precision amplifiers suitable for low-power sensor signal conditioning and stable analog performance.

## Summary Table of Final Major Components

| **Component Category** | **Final Component Selected** | **Reason for Selection** |
|------------------------|------------------------------|---------------------------|
| **Soil Moisture Sensor** | DIY Capacitive Soil Moisture Sensor | Easy RC circuit, low-power, and provides a stable analog signal for PIC ADC processing. |
| **Operational Amplifier** | MCP6004 Quad Op-Amp | Rail-to-rail operation and low power, suitable for filtering and amplifying the sensor output. |
| **Voltage Regulator** | LM7805 Linear Regulator (TO-220) | Supplied to us, simple, and stable 5 V regulation for the subsystem. |


