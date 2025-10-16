---
title: Component Selection
---

# Component Selection

Subsystem board powered from 9 V input through a 5 V regulator.  
Includes a microcontroller connected to:  
- Analog soil moisture sensor  
- Temperature/humidity sensor  
- Rain sensor  
- 8-pin connector to communicate with other boards  

---

## Soil Moisture Sensor (Analog)

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](soil1.png)<br>**Option 1:** Resistive probe (e.g., YL-69 Module)<br>$2 each<br>[YL-69 Resistive Sensor](https://www.digikey.com/en/products/detail/yl-69/)|*Very low cost*<br>*Easy analog output for ADC*|*Corrodes quickly*<br>*Non-linear readings*<br>*Requires frequent calibration*|
| ![](soil2.png)<br>**Option 2:** Capacitive soil moisture sensor v1.2<br>$5 each<br>[Capacitive Soil Module](https://www.adafruit.com/product/4026)|*No corrosion*<br>*Stable analog signal*<br>*Compact size*|*Slightly higher cost*<br>*Needs calibration per soil type*|
| ![](soil3.png)<br>**Option 3:** Industrial analog soil moisture transmitter (4–20 mA output)<br>$22 each<br>[Industrial Soil Transmitter](https://www.dfrobot.com/product-1385.html)|*Weatherproof housing*<br>*Highly accurate and robust*|*Expensive*<br>*Larger form factor*|

**Choice:** Option 2 — Capacitive Soil Moisture Sensor v1.2  
**Rationale:** Provides stable analog readings without corrosion, making it suitable for long-term outdoor testing while staying low-cost and easy to integrate with the microcontroller’s ADC.

---

## Temperature & Humidity Sensor

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](temp1.png)<br>**Option 1:** DHT22 / AM2302<br>$6 each<br>[DHT22 Sensor](https://www.adafruit.com/product/385)|*Low cost*<br>*Easy to use (Arduino library)*|*Slow sampling rate*<br>*±2 °C, ±5 % RH accuracy*|
| ![](temp2.png)<br>**Option 2:** SHT31-D (I²C)<br>$12 each<br>[SHT31-D Sensor](https://www.adafruit.com/product/2857)|*High accuracy (±2 % RH, ±0.3 °C)*<br>*Fast response*<br>*I²C communication*|*Higher price*|
| ![](temp3.png)<br>**Option 3:** BME280 (I²C/SPI)<br>$14 each<br>[BME280 Sensor](https://www.adafruit.com/product/2652)|*Adds pressure measurement*<br>*Accurate & low power*|*Adds unnecessary feature (pressure)*<br>*Slightly more expensive*|

**Choice:** Option 2 — SHT31-D Sensor  
**Rationale:** Best balance of precision, low power, and easy I²C integration for microcontroller communication.

---

## Rain Sensor

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](rain1.png)<br>**Option 1:** Analog rain detection board (YL-83)<br>$3 each<br>[YL-83 Rain Module](https://www.adafruit.com/product/2900)|*Cheap and simple*<br>*Analog or digital output*|*Corrosion over time*<br>*Not weatherproof*|
| ![](rain2.png)<br>**Option 2:** Optical rain sensor (IR reflection type)<br>$25 each<br>[Optical Rain Sensor](https://www.dfrobot.com/product-1529.html)|*Non-contact detection*<br>*Long life*|*Requires optical calibration*<br>*Higher cost*|
| ![](rain3.png)<br>**Option 3:** Tipping-bucket rain gauge<br>$60 each<br>[Tipping Bucket Sensor](https://www.sparkfun.com/products/8942)|*Accurate rainfall measurement (mm)*|*Bulky, mechanical parts*<br>*Requires mounting and calibration*|

**Choice:** Option 1 — YL-83 Analog Rain Module  
**Rationale:** Simple analog detection is sufficient for moisture-triggered irrigation feedback without needing quantitative rainfall measurement.

---

## Voltage Regulator (9 V → 5 V)

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](reg1.png)<br>**Option 1:** LM7805 Linear Regulator<br>$1 each<br>[LM7805](https://www.ti.com/product/LM7805)|*Simple circuit, low noise*<br>*Stable 5 V output*|*Inefficient (heat loss)*|
| ![](reg2.png)<br>**Option 2:** LM2596 Buck Converter<br>$4 each<br>[LM2596 Buck Module](https://www.digikey.com/en/products/detail/lm2596/)|*Efficient, handles higher current*<br>*Cool operation*|*More electrical noise (may affect ADC)*|

**Choice:** Option 1 — LM7805 Linear Regulator  
**Rationale:** System current is low (<150 mA), so heat dissipation is minimal. The LM7805’s clean output benefits analog sensors and simplifies the PCB design.
