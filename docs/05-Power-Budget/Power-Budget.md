---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** Isaiah LaCombe  
**Version:** 1.0  

**System input:** 9V external → 5V regulator (LM7805) → PIC18F16Q41 Curiosity Nano + sensors

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F16Q41 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 5 | 5 |
| Temperature / Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | SEN0545 (UART) | 5 | 1 | 40 | 40 |
| **Subtotal** | | | | | **547mA** |

**Arithmetic:**  
500 + 5 + 2 + 40 = **547mA total subsystem current**

## Section B – Power Rails

## +5V Rail
- Subtotal = **547 mA**  
- Safety margin (25%) = 547 × 1.25 = 683.75mA → round to 684mA

**Arithmetic:**  
547 × 1.25 = (547 × 5) / 4 = 2735 / 4 = 683.75mA

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25V | 1500 | Simple, low noise, easy to use | Inefficient (9V → 5V drop causes heat under load; may need heat sink) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35V | 100 | Compact, low quiescent current | Limited to 100mA output (too low for this system) |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With the total estimated current of 684mA (including the 25% margin), the LM7805 provides sufficient current capacity and thermal headroom.  
The UA78L05ACLP’s 100mA limit is below system requirements.

**Regulator heat / dissipation check:**  
Voltage drop = 9V − 5V = 4V  
Load current = 684mA = 0.684A  
Power dissipated = 4V × 0.684A = 2.736W  

**Result:** LM7805 will require a small heat sink at this power level.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on +5V rail (with 25% margin): 684mA 
- Remaining capacity: 1000 − 684 = 316 mA

**Arithmetic:**  
1500 − 684 = 816mA remaining capacity before voltage Regulator Failure

**Battery option:** 3000 mAh Li-ion battery
This is not used in the design but if it was:  

Battery life = 3000 mAh / 50 mA = 60 hours (≈2.5 days) Reducing average current to 50 mA using sleep + duty cycling
for maximum battery life.

> **Result:** Battery operation is not practical due to high current draw.

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | 547mA |
| Total required on 5V rail (with 25% margin) | 684mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation (9→5V at 684 mA) | ≈ 2.74W (may need a heat sink) |
| External supply recommended | 9V DC adapter, ≥ 3 A |
| Estimated battery life (3000 mAh Li-ion battery) | Max Current 60 hours (≈2.5 days) |
