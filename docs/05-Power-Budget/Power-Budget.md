---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Sensor Subsystem Board  
**Team Member Names:** Liam, Isaiah, and Raj  
**Version:** 1.1  

**System input:** 9V external → 5V regulator (LM7805) → PIC18F57Q43 Curiosity Nano + soil moisture sensor

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F57Q43 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 5 | 5 |
| **Subtotal** | | | | | **505mA** |

**Arithmetic:**  
500 + 5 = **505mA total subsystem current**

## Section B – Power Rails

**+5V Rail**
- Subtotal = 505 mA  
- Safety margin (25%) = 505 × 1.25 = 631.25mA → round to **631mA**

**Arithmetic:**  
505 × 1.25 = (505 × 5) / 4 = 2525 / 4 = **631.25mA**

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25V | 1500 | Simple, low noise, reliable | Inefficient for high current (heat dissipation) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35V | 100 | Compact, low quiescent current | Not enough current for system needs |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With a total estimated current of 631mA (including the 25% margin), the LM7805 provides plenty of current capacity and thermal safety. The UA78L05ACLP’s 100mA limit is far below system requirements.

**Regulator heat / dissipation check:**  
Voltage drop = 9V − 5V = 4V  
Load current = 631mA = 0.631A  
Power dissipated = 4V × 0.631A = **2.52W**

**Result:** LM7805 will require a small heat sink for continuous operation.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on +5V rail (with 25% margin): 631mA  
- Remaining capacity: 3000 − 631 = **2369 mA**

**Battery Option (not implemented):**  
If powered by a 3000mAh Li-ion battery:  

Battery life = 3000 mAh / 50 mA (sleep-mode avg.) = **60 hours (≈2.5 days)**  

Due to higher active current draw, continuous battery use is not recommended for this design.

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | 505mA |
| Total required on 5V rail (with 25% margin) | 631mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation (9→5V at 631mA) | ≈ 2.52W (heat sink required) |
| External supply recommended | 9V DC adapter, ≥ 3A |
| Estimated battery life (3000 mAh Li-ion battery) | ≈ 60 hours (sleep mode average) |

**Conclusion:** 
The subsystem draws a safe and stable current within the LM7805’s limits. The 9V, 3A wall adapter provides more than enough headroom for all operations, ensuring reliable performance for the Smart Irrigation Sensor Subsystem.
