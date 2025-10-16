---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** Isaiah LaCombe  
**Version:** 1.0  

**System input:** 9 V external → 5 V regulator (LM7805) → PIC18F16Q41 Curiosity Nano + sensors

---

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F16Q41 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 5 | 5 |
| Temperature / Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | SEN0545 (UART) | 5 | 1 | 40 | 40 |
| Indicator LED | Status LED (with resistor) | 5 | 1 | 10 | 10 |
| **Subtotal (estimated)** | | | | | **557 mA** |

**Arithmetic:**  
500 + 5 + 2 + 40 + 10 = **557 mA total subsystem current**

---

## Section B – Power Rails

### +5 V Rail
- Subtotal = **557 mA**  
- Safety margin (25%) = 557 × 1.25 = **696.25 mA** → round to **696 mA**

**Arithmetic:**  
557 × 1.25 = (557 × 5) / 4 = 2785 / 4 = **696.25 mA**

---

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25 V | 1500 | Simple, low noise, easy to use | Inefficient (9 V → 5 V drop causes heat; may need heat sink) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35 V | 100 | Compact, low quiescent current | Limited to 100 mA output (too low for this system) |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With the total estimated current of **696 mA** (including a 25% margin), the LM7805 provides enough capacity and thermal headroom.  
The UA78L05ACLP’s 100 mA limit is insufficient for this system.

**Regulator heat / dissipation check:**  
Voltage drop = 9 V − 5 V = 4 V  
Load current = 696 mA = 0.696 A  
Power dissipated = 4 V × 0.696 A = **2.784 W**  

> **Result:** LM7805 will require a small heat sink at this power level.

---

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9 V DC Adapter | 9 | 1000 |

- Required on +5 V rail (with 25% margin): **696 mA**  
- Remaining capacity: 1000 − 696 = **304 mA**

**Arithmetic:**  
1000 − 696 = **304 mA remaining capacity**

**Battery option (example):** 9 V alkaline ≈ 500 mAh (typical spec)  

Battery life = 500 mAh / 696 mA = **0.718 hours ≈ 43 minutes**

> **Result:** Battery operation is not practical due to high current draw.

---

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | **557 mA** |
| Total required on 5 V rail (with 25% margin) | **696 mA** |
| Regulator chosen | **LM7805 Linear Regulator** |
| Regulator dissipation (9→5 V at 696 mA) | **≈ 2.78 W (requires heat sink)** |
| External supply recommended | **9 V DC adapter, ≥ 1 A** |
| Estimated battery life (9 V, 500 mAh) | **~0.72 hours (≈43 min)** |
| Action required | **Verify PIC18F16Q41/Curiosity Nano current. If actual draw <100 mA, you may use UA78L05ACLP. Otherwise stay with LM7805.** |

---

### Notes & Tips
- Replace estimated MCU current (500 mA) with the **actual maximum** from the Microchip datasheet. The Curiosity Nano typically consumes **<50 mA**, so your actual total current and power dissipation will be **much lower** once corrected.  
- When using the LM7805, ensure you attach a **small heat sink** if your real current exceeds ~300 mA.  
- Keep the 25% safety margin in all power budget calculations.  
- Add datasheet links for all components when finalizing your GitHub page before export.


