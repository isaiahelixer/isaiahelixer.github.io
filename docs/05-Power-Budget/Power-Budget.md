---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** Isaiah LaCombe  
**Version:** 1.0  

**System input:** 9 V external → 5 V regulator (LM7805) → PIC18F16Q41 Curiosity Nano + sensors

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F16Q41 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 5 | 5 |
| Temperature / Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | SEN0545 (UART) | 5 | 1 | 40 | 40 |
| **Subtotal (estimated)** | | | | | **547 mA** |

**Arithmetic:**  
500 + 5 + 2 + 40 = **547 mA total subsystem current**

## Section B – Power Rails

### +5 V Rail
- Subtotal = **547 mA**  
- Safety margin (25%) = 547 × 1.25 = **683.75 mA** → round to **684 mA**

**Arithmetic:**  
547 × 1.25 = (547 × 5) / 4 = 2735 / 4 = **683.75 mA**

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25 V | 1500 | Simple, low noise, easy to use | Inefficient (9 V → 5 V drop causes heat; may need heat sink) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35 V | 100 | Compact, low quiescent current | Limited to 100 mA output (too low for this system) |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With the total estimated current of **684 mA** (including a 25% margin), the LM7805 provides sufficient current capacity and thermal headroom.  
The UA78L05ACLP’s 100 mA limit is below system requirements.

**Regulator heat / dissipation check:**  
Voltage drop = 9 V − 5 V = 4 V  
Load current = 684 mA = 0.684 A  
Power dissipated = 4 V × 0.684 A = **2.736 W**  

> **Result:** LM7805 will require a small heat sink at this power level.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9 V DC Adapter | 9 | 1000 |

- Required on +5 V rail (with 25% margin): **684 mA**  
- Remaining capacity: 1000 − 684 = **316 mA**

**Arithmetic:**  
1000 − 684 = **316 mA remaining capacity**

**Battery option (example):** 9 V alkaline ≈ 500 mAh (typical spec)  

Battery life = 500 mAh / 684 mA = **0.731 hours ≈ 44 minutes**

> **Result:** Battery operation is not practical due to high current draw.

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | **547 mA** |
| Total required on 5 V rail (with 25% margin) | **684 mA** |
| Regulator chosen | **LM7805 Linear Regulator** |
| Regulator dissipation (9→5 V at 684 mA) | **≈ 2.74 W (requires heat sink)** |
| External supply recommended | **9 V DC adapter, ≥ 1 A** |
| Estimated battery life (9 V, 500 mAh) | **~0.73 hours (≈44 min)** |
| Action required | **Verify PIC18F16Q41/Curiosity Nano current. If actual draw <100 mA, you may use UA78L05ACLP. Otherwise stay with LM7805.** |

### Notes & Tips
- Replace estimated MCU current (500 mA) with the **actual max current** from the Microchip datasheet. The Curiosity Nano typically draws **<50 mA**, meaning the real current and power dissipation will be **much lower** than the conservative estimate shown.  
- Attach a **small heat sink** if current exceeds ~300 mA.  
- Maintain the **25% safety margin** in all power calculations.  
- Add **datasheet links** for all components when finalizing your GitHub Markdown page before export.
