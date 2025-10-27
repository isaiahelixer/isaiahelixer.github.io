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
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/287/217/SEN0114_sml.jpg)<br>**Option 1:** SEN0114 Soil Moisture Sensor Module<br>$2.70 — each<br>[link to product](https://www.digikey.com/en/products/detail/dfrobot/SEN0114/6588525) | *Simple analog output*<br>*Low cost*<br>*Compact design* | *Corrodes over time if left in soil*<br>*Requires calibration for accuracy* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/169/089/MFG_ST0160_sml%28200x200%29.jpg)<br>**Option 2:** ST0160 Capacitive Soil Moisture Sensor V2.0<br>$8.60 — each<br>[link to product](https://www.digikey.com/en/products/detail/sunfounder/ST0160/22116813) | *No corrosion (capacitive)*<br>*Stable analog readings*<br>*Low power consumption* | *More expensive than SEN0114*<br>*Slightly larger PCB footprint* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/930/342/MFG_314990620_sml.jpg)<br>**Option 3:** Industrial Soil Moisture & Temperature Sensor<br>$79 — each<br>[link to product](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/314990620/16570933) | *Industrial-grade durability*<br>*Includes temperature output*<br>*Long-term outdoor reliability* | *Higher cost*<br>*Requires analog-to-current interface circuitry* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  

**Rationale:** Provides corrosion-free sensing with stable analog output and is suitable for long-term outdoor monitoring while maintaining low cost and simple integration with the PIC ADC.

## Voltage Regulator 

*Table 2: Voltage Regulator Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/415/110/497%7ETO220-3TO220AB%7E%7E3_sml.jpg)<br>**Option 1:** LM7805 Linear Regulator<br>$0.64 — each<br>[link to product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ACV/585962) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient when dropping 9 V to 5 V*<br>*Generates heat at higher currents* |
| ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/202/809/296%7E4040001-2%7ELP%7E3_sml%28200x200%29.jpg)<br>**Option 2:** UA78L05ACLP<br>$1.69 — each<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/UA78L05ACLP/13465029) | *Compact package*<br>*Low quiescent current*<br>*Perfect for ≤ 100 mA loads* | *Limited output current (100 mA max)*<br>*Not ideal for high-current systems* |

**Choice:** Option 1 — LM7805 Linear Regulator  

**Rationale:** System current is moderate so the LM7805 offers sufficient efficiency with low noise, needed for stable analog measurements on the sensor inputs.

## Microcontroller

**Component:** PIC18F16Q41 Curiosity Nano  
**Supply:** 5 V from LM7805 Regulator  

**Rationale:** Used for its low-power operation, built-in ADC channels for analog sensor inputs, I²C and UART support for digital sensors, and fast development and debugging.

## Operational Amplifier

**Component:** MCP6004 (Through-Hole Quad Op-Amp)  
**Supply:** 5 V from LM7805 Regulator  

**Rationale:** Already supplied component used for signal conditioning of analog sensor inputs. Offers rail-to-rail I/O, low power consumption, and stable operation within 5 V single-supply systems.  
**Note:** Maximum supply current is 23 mA. Ensure local decoupling with 0.1 µF capacitors near each Vcc pin.  

## Power Adapter

**Component:** Model 0930 — AC to DC Power Adapter  
**Specification:** 9 V DC Output, 3 A Max  

**Rationale:** Pre-supplied power source providing system input voltage for the LM7805 regulator. Rated current provides sufficient headroom for the subsystem load.  
**Note:** Verify barrel jack polarity and label on PCB (typically center-positive). Include a 2 A inline fuse and bulk capacitor (e.g., 470 µF, 25 V) on the input for protection and stability.


