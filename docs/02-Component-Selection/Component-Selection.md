---
title: Component Selection
---

# Component Selection

Subsystem board powered from 9 V wall adapter input through a 5 V regulator.  
Includes a PIC18F16Q41 Curiosity Nano microcontroller connected to:  
- Analog capacitive soil moisture sensor  
- MCP6004 op-amp  
- 8-pin connector to communicate with other boards  

## Soil Moisture Sensors

*Table 1: Soil Moisture Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://github.com/user-attachments/assets/66eeb141-3a8a-4a65-ba30-f9e865b20f8b)
| *Simple analog output*<br>*Low cost*<br>*Compact design* | *Corrodes over time if left in soil*<br>*Requires calibration for accuracy* |
| ![](https://github.com/user-attachments/assets/d213c9d3-1647-4f78-83f7-da6f1a7d93ea)
<br>**Option 2:** ST0160 Capacitive Soil Moisture Sensor V2.0<br>$8.60 — each<br>[link to product](https://www.amazon.com/Capacitive-Corrosion-Resistant-Detection-Raspberry/dp/B0F6N259HM/?_encoding=UTF8&pd_rd_w=DQplV&content-id=amzn1.sym.048a6e3c-8d40-4302-8312-26c626af6738%3Aamzn1.symc.050ea944-f1cf-4610-b462-3b604f2f4082&pf_rd_p=048a6e3c-8d40-4302-8312-26c626af6738&pf_rd_r=6MM1VGGRWJ33QBQZWP95&pd_rd_wg=0njKJ&pd_rd_r=abac3d32-6dc9-42ad-bebb-c9ab94a5e445&ref_=pd_hp_d_btf_ci_mcx_mr_ca_id_hp_d) | *No corrosion (capacitive)*<br>*Stable analog readings*<br>*Low power consumption* | *More expensive than SEN0114*<br>*Slightly larger PCB footprint* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/930/342/MFG_314990620_sml.jpg)<br>**Option 3:** Industrial Soil Moisture & Temperature Sensor<br>$79 — each<br>[link to product](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/314990620/16570933) | *Industrial-grade durability*<br>*Includes temperature output*<br>*Long-term outdoor reliability* | *Higher cost*<br>*Requires analog-to-current interface circuitry* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  

**Rationale:** Provides corrosion-free sensing with stable analog output for long-term outdoor monitoring while maintaining low cost and simple integration with the PIC ADC.

## Voltage Regulator 

*Table 2: Voltage Regulator Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/415/110/497%7ETO220-3TO220AB%7E%7E3_sml.jpg)<br>**Option 1:** LM7805 Linear Regulator<br>$0.64 — each<br>[link to product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient when dropping 9 V to 5 V*<br>*Generates heat at higher currents* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/809/296%7E4040001-2%7ELP%7E3_sml%28200x200%29.jpg)<br>**Option 2:** UA78L05ACLP<br>$1.69 — each<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/UA78L05ACLP/13465029) | *Compact package*<br>*Low quiescent current*<br>*Perfect for ≤100 mA loads* | *Limited output current (100 mA max)*<br>*Not ideal for high-current systems* |
|<img width="301" height="300" alt="Screenshot 2025-10-27 085500 (1)" src="https://github.com/user-attachments/assets/89f2e40e-c528-4b86-9d24-e24a1fa8eebd" />
 <br>**Option 3:** N7805-1CW DC/DC Converter (Mean Well)<br>$4.84 — each<br>[link to product](https://www.digikey.com/en/products/detail/mean-well-usa-inc/N7805-1CW/22119070?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLlg-mikvqqI5kSyxvX2VfJ_hR&gclid=Cj0KCQjwsPzHBhDCARIsALlWNG103010_DEIqUxx9fiA1KByIbHfhtIRslfFwbx4pb0jn2gCCEdNubsaAjjsEALw_wcB) | *High efficiency (93%)*<br>*Wide 8–36 V input range*<br>*Compact enclosed design*<br>*Low heat output*<br>*500 mA max current, 7.5 W power*<br>*Operates -40°C to +85°C* | *Higher cost than LM7805*<br>*More complex sourcing if not stocked* |

**Choice:** Option 1 — LM7805 Linear Regulator  

**Rationale:** The LM7805 is already supplied and sufficient for the system’s moderate current demand. The N7805-1CW offers improved efficiency but is not required for this application.

## Microcontroller

*Table 3: Microcontroller Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
|<img width="423" height="250" alt="Screenshot 2025-10-27 083819 (1)" src="https://github.com/user-attachments/assets/74bf714e-3918-4d43-b116-b8da425d14f9" />
<br>**Option 1:** PIC18F16Q41 Curiosity Nano<br>$15 — each<br>[link to product](https://www.microchip.com/en-us/development-tool/dm164150) | *Low-power operation*<br>*Integrated ADC channels*<br>*I²C, SPI, and UART communication*<br>*Onboard debugger (USB)* | *Limited I/O for expansion*<br>*Requires MPLAB X IDE setup* |

**Choice:** Option 1 — PIC18F16Q41 Curiosity Nano  

**Rationale:** Readily available and already supplied to the team, simplifying integration with sensors and op-amp circuitry.

## Operational Amplifier

*Table 4: Operational Amplifier Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
|<img width="299" height="300" alt="Screenshot 2025-10-27 083608 (1)" src="https://github.com/user-attachments/assets/31820770-4b2e-4d94-a2e6-3f3f1526158e" />
<br>**Option 1:** MCP6004 Quad Op-Amp (Through-Hole)<br>$1.25 — each<br>[link to product](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | *Rail-to-rail I/O*<br>*Low quiescent current (23 mA max)*<br>*Operates from single 5 V supply*<br>*Four amplifiers per package* | *Through-hole package larger than SMD*<br>*Limited bandwidth for high-speed signals* |

**Choice:** Option 1 — MCP6004 Op-Amp  

**Rationale:** Already supplied; provides four precision amplifiers suitable for low-power sensor signal conditioning and stable analog performance.

## Power Adapter

*Table 5: Power Adapter Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
|<img width="299" height="300" alt="Screenshot 2025-10-27 084100 (1)" src="https://github.com/user-attachments/assets/04c6a715-77bc-453e-a9f3-900abc7a1e74" />
<br>**Option 1:** 9V 3A AC to DC Adapter — Model 0930<br>Supplied Item<br>[link to product](https://circuit.rocks/products/ac-dc-9v-3a-wall-power-adapter-5-5x2-1mm-barrel-jack-center-positive?srsltid=AfmBOorFslDo47N-3NvdrLDoGEcEk_4wOiCGbP_auU3NXxOUc5jR5Ha3) | *High current capacity (3 A)*<br>*Stable DC output*<br>*Compatible with LM7805 input requirements* | *Linear regulator heat generation at high loads*<br>*Requires correct barrel polarity and connector matching* |

**Choice:** Option 1 — 9 V 3 A AC to DC Adapter (Model 0930)  

**Rationale:** Already supplied and provides sufficient power for the full subsystem board, ensuring reliable operation of all components through the 5 V regulated supply.
