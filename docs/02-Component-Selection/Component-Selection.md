---
title: Component Selection
---

# Component Selection

Subsystem board powered from 9 V input through a 5 V regulator.  
Includes a PIC18F16Q41 Curiosity Nano microcontroller connected to:  
- Analog soil moisture sensor  
- Temperature/humidity sensor  
- Rain sensor  
- 8-pin connector to communicate with other boards  

---

## Soil Moisture Sensor (Analog)

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](soil1.png)<br>**Option 1:** Resistive probe (e.g., YL-69 Module)<br>$2 each<br>[YL-69 Resistive Sensor](https://www.digikey.com/) | *Very low cost*<br>*Easy analog output for ADC* | *Corrodes quickly*<br>*Non-linear readings*<br>*Requires frequent calibration* |
| ![](soil2.png)<br>**Option 2:** Capacitive soil moisture sensor v1.2<br>$5 each<br>[Capacitive Soil Module](https://www.adafruit.com/) | *No corrosion*<br>*Stable analog signal*<br>*Compact size* | *Slightly higher cost*<br>*Needs calibration per soil type* |
| ![](soil3.png)<br>**Option 3:** Industrial analog soil moisture transmitter (4–20 mA output)<br>$22 each<br>[Industrial Soil Transmitter](https://www.dfrobot.com/) | *Weatherproof housing*<br>*Highly accurate and robust* | *Expensive*<br>*Larger form factor* |

**Choice:** Option 2 — Capacitive Soil Moisture Sensor v1.2  
**Rationale:** Provides stable analog readings without corrosion, suitable for long-term outdoor deployment while remaining low-cost and easy to interface with the PIC ADC.

---

## Temperature & Humidity Sensor

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](temp1.png)<br>**Option 1:** DHT22 / AM2302<br>$6 each<br>[DHT22 Sensor](https://www.adafruit.com/) | *Low cost*<br>*Easy to use (library support)* | *Slow sampling rate*<br>*Moderate accuracy* |
| ![](temp2.png)<br>**Option 2:** SHT31-D (I²C)<br>$12 each<br>[SHT31-D Sensor](https://www.adafruit.com/) | *High accuracy and stability*<br>*Fast response*<br>*I²C communication* | *Higher price* |
| ![](temp3.png)<br>**Option 3:** BME280 (I²C/SPI)<br>$14 each<br>[BME280 Sensor](https://www.adafruit.com/) | *Adds pressure measurement*<br>*Accurate & low power* | *Adds unnecessary feature (pressure)*<br>*Slightly more expensive* |

**Choice:** Option 2 — SHT31-D Sensor  
**Rationale:** Best balance of precision, low power, and easy I²C integration for the PIC18F16Q41.

---

## Rain Sensor

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](rain1.png)<br>**Option 1:** Analog rain detection board (YL-83)<br>$3 each<br>[YL-83 Rain Module](https://www.adafruit.com/) | *Cheap and simple*<br>*Analog or digital output* | *Corrodes over time*<br>*Not weatherproof* |
| ![](rain2.png)<br>**Option 2:** Optical rain sensor (IR reflection type)<br>$25 each<br>[Optical Rain Sensor](https://www.dfrobot.com/) | *Non-contact detection*<br>*Long life* | *Requires optical calibration*<br>*Higher cost* |
| ![](rain3.png)<br>**Option 3:** Tipping-bucket rain gauge<br>$60 each<br>[Tipping Bucket Sensor](https://www.sparkfun.com/) | *Accurate rainfall measurement (mm)* | *Bulky, mechanical parts*<br>*Requires mounting and calibration* |

**Choice:** Option 1 — YL-83 Analog Rain Module  
**Rationale:** Simple analog detection is sufficient for moisture-triggered irrigation logic and is easy to interface with PIC ADC inputs.

---

## Voltage Regulator (9 V → 5 V)

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](reg1.png)<br>**Option 1:** LM7805 Linear Regulator<br>$1 each<br>[LM7805](https://www.ti.com/) | *Simple circuit, low noise*<br>*Stable 5 V output* | *Inefficient (heat loss) when dropping from 9 V* |
| ![](reg2.png)<br>**Option 2:** LM2596 Buck Converter<br>$4 each<br>[LM2596 Buck Module](https://www.digikey.com/) | *Efficient, handles higher current*<br>*Cool operation* | *More switching noise (may need filtering)* |

**Choice:** Option 1 — LM7805 Linear Regulator  
**Rationale:** Estimated system current is low; LM7805 gives a clean, low-noise 5 V rail which benefits ADC readings from analog sensors. If measured current grows above ~200–300 mA, switch to a buck converter.

---

## Microcontroller (PIC18F16Q41 Curiosity Nano)  **(subsystem: MCU)**

- **Board:** Microchip Curiosity Nano with PIC18F16Q41
- **Notes:** Use the Curiosity Nano breakout footprint or include the bare PIC18F16Q41 on your PCB as your design requires.
- **Power/IO:** 5 V logic (confirm board configuration) and ADC inputs for soil and rain sensors; I²C for SHT31.

**Rationale for selection:** PIC18F16Q41 provides sufficient analog inputs, low-power operation options, and easy integration with Microchip Curiosity Nano development board for rapid prototyping and debugging.

**Important:** Replace the estimated current values in your power budget with the PIC18F16Q41 *absolute maximum* current values from the Microchip datasheet and the Curiosity Nano board documentation (required for accuracy in the power budget).
