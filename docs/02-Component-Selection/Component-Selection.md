---
title: Component Selection
---

# Component Selection

Subsystem board powered from 9 V input through a 5 V regulator.  
Includes a **PIC18F16Q41 Curiosity Nano microcontroller** connected to:  
- Analog soil moisture sensor  
- Temperature / humidity sensor  
- Rain sensor  
- 8-pin connector to communicate with other boards  

---

## Soil Moisture Sensors

*Table 1: Soil Moisture Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](SEN0114.png)<br>**Option 1:** SEN0114 Soil Moisture Sensor Module<br>$ — each<br>[link to product](URL) | *Simple analog output*<br>*Low cost*<br>*Compact design* | *Corrodes over time if left in soil*<br>*Requires calibration for accuracy* |
| ![](ST0160.png)<br>**Option 2:** ST0160 Capacitive Soil Moisture Sensor V2.0<br>$ — each<br>[link to product](URL) | *No corrosion (capacitive)*<br>*Stable analog readings*<br>*Low power consumption* | *More expensive than SEN0114*<br>*Slightly larger PCB footprint* |
| ![](Industrial_Soil.png)<br>**Option 3:** Industrial Soil Moisture & Temperature Sensor (4-20 mA Output)<br>$ — each<br>[link to product](URL) | *Industrial-grade durability*<br>*Includes temperature output*<br>*Long-term outdoor reliability* | *Higher cost*<br>*Requires analog-to-current interface circuitry* |

**Choice:** Option 2 — ST0160 Capacitive Soil Moisture Sensor V2.0  

**Rationale:** Provides corrosion-free sensing with stable analog output, ideal for long-term moisture monitoring in outdoor environments while maintaining low cost and simple integration with the PIC ADC.

---

## Temperature & Humidity Sensors

*Table 2: Temperature & Humidity Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](DHT22.png)<br>**Option 1:** DHT22 / AM2302 Sensor<br>$ — each<br>[link to product](URL) | *Low cost*<br>*Simple one-wire interface*<br>*Good community support* | *Slow sampling rate*<br>*Limited accuracy (±2 °C, ±5 % RH)* |
| ![](SHT31.png)<br>**Option 2:** Adafruit Sensirion SHT31-D Sensor (I²C)<br>$ — each<br>[link to product](URL) | *High accuracy (±0.3 °C, ±2 % RH)*<br>*I²C communication*<br>*Fast response time* | *Moderate cost*<br>*Requires I²C pins on MCU* |
| ![](SHT45.png)<br>**Option 3:** SHT45 Precision Temperature Humidity Module<br>$ — each<br>[link to product](URL) | *Very high precision (±0.1 °C, ±1 % RH)*<br>*Low power consumption*<br>*Compact form factor* | *Higher price*<br>*May require fine-pitch connector or adapter* |

**Choice:** Option 2 — Adafruit Sensirion SHT31-D Sensor  

**Rationale:** Offers a balance between precision, power efficiency, and integration simplicity using I²C communication, aligning well with the PIC18F16Q41’s peripheral support.

---

## Rain Sensors

*Table 3: Rain Sensor Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](ST0247.png)<br>**Option 1:** ST0247 Raindrop Detection Sensor Module<br>$ — each<br>[link to product](URL) | *Low cost and easy to interface*<br>*Analog and digital outputs* | *Susceptible to corrosion and false positives*<br>*Not quantitative* |
| ![](SEN0545.png)<br>**Option 2:** SEN0545 Rain Sensor (UART Output)<br>$ — each<br>[link to product](URL) | *Digital UART interface*<br>*Corrosion-resistant coating*<br>*Stable signal processing built-in* | *Slightly higher cost*<br>*Requires UART parsing logic* |
| ![](OpticalRain.png)<br>**Option 3:** Optical Rain Gauge Sensor (RS485 Pulse Output)<br>$ — each<br>[link to product](URL) | *Industrial precision and long lifetime*<br>*Non-contact optical detection* | *High price*<br>*Requires RS485 interface and external housing* |

**Choice:** Option 2 — SEN0545 Rain Sensor (UART Output)  

**Rationale:** Provides reliable digital output with minimal maintenance and better environmental resistance than basic analog boards, while avoiding the complexity and cost of industrial RS485 systems.

---

## Voltage Regulator (9 V → 5 V)

*Table 4: Voltage Regulator Comparison*

| **Solution** | **Pros** | **Cons** |
|--------------|-----------|-----------|
| ![](LM7805.png)<br>**Option 1:** LM7805 Linear Regulator<br>$ — each<br>[link to product](URL) | *Simple design*<br>*Low noise*<br>*Stable 5 V output* | *Inefficient when dropping 9 V to 5 V*<br>*Generates heat at higher currents* |
| ![](LM2596.png)<br>**Option 2:** LM2596 Buck Converter<br>$ — each<br>[link to product](URL) | *High efficiency*<br>*Cooler operation*<br>*Can handle higher currents* | *Slight switching noise*<br>*More complex layout* |

**Choice:** Option 1 — LM7805 Linear Regulator  

**Rationale:** System current is low (< 150 mA) so the LM7805 offers sufficient efficiency with low noise, ideal for stable analog measurements on the sensor inputs.

---

## Microcontroller

**Component:** PIC18F16Q41 Curiosity Nano  
**Supply:** 5 V from LM7805 Regulator  

**Rationale:** Chosen for its low-power operation, built-in ADC channels for analog sensor inputs, I²C and UART support for digital sensors, and native compatibility with Microchip’s Curiosity Nano ecosystem for fast development and debugging.

