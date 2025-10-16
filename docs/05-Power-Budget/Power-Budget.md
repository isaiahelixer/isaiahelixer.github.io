---
title: Power Budget
---

# Power Budget

**Team Number:** —  
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** (Your Name)  
**Version:** 1.0  

**System input:** 9 V external → 5 V regulator (LM7805) → PIC18F16Q41 Curiosity Nano + sensors

> **IMPORTANT:** The PIC18F16Q41 current in this document is an **estimate (50 mA)**. BEFORE final submission replace the PIC18F16Q41 / Curiosity Nano current with the MCU **absolute maximum** (and add the Curiosity Nano board draw if you are using the dev board). Use datasheet numbers for all final calculations.

## Section A – All Major Components (estimates)

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F16Q41 Curiosity Nano (estimate) | 5 | 1 | **50 (estimate)** | 50 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 10 | 10 |
| Temperature / Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | SEN0545 (UART) | 5 | 1 | 10 | 10 |
| Indicator LED | Status LED (with resistor) | 5 | 1 | 10 | 10 |
| **Subtotal (estimated)** | | | | | **82 mA** |

**Arithmetic used (digit-by-digit):**  
50 + 10 = 60.  
60 + 2 = 62.  
62 + 10 = 72.  
72 + 10 = 82.  
→ **Subtotal = 82 mA**.

## Section B – Power Rails

### +5 V Rail
- Subtotal (estimated) = **82 mA**.  
- Safety margin (25%) = 82 × 1.25 = 102.5 mA → round to **103 mA**.

**Arithmetic used (digit-by-digit):**  
82 × 1.25 = 82 × (5/4) = (82 × 5) / 4 = 410 / 4 = 102.5 → round → **103 mA**.

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 35 V | 1000 | Simple, low noise | Inefficient: (9 V → 5 V) dissipates heat |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35 V | 100 | Compact, low quiescent current | Limited to ~100 mA output |

**Choice:** LM7805 Linear Regulator (per your latest selection)  
**Rationale:** With the current estimated at **103 mA** (including 25% margin), the LM7805 can supply the load with margin. If the final MCU + board current is below ~100 mA, the UA78L05ACLP is a compact alternative — otherwise stay with LM7805 to avoid current limits.

**Regulator heat / dissipation check (digit-by-digit calculation):**  
Voltage drop = 9 V − 5 V = 4 V.  
Current drawn from input ≈ load current = 103 mA = 0.103 A.  
Power dissipated = Voltage drop × Current = 4 V × 0.103 A.  
Compute: 4 × 0.103 = 0.412 (watts).  
→ **Regulator dissipation ≈ 0.412 W** (LM7805 can handle this without large heatsink; OK).

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9 V DC Adapter | 9 V | 500 mA |

- Required on +5 V rail (with 25% margin): **103 mA**.  
- Remaining capacity from 9 V / 500 mA adapter: 500 − 103 = **397 mA**.

**Arithmetic used (digit-by-digit):**  
500 − 103 = 397.

**Battery option (example):** 9 V alkaline ≈ 500 mAh (typical spec).  
Battery life estimate (worst-case, all subsystems running):

Battery life (hours) = Battery capacity (mAh) / Load (mA)  
= 500 mAh / 103 mA = 4.854369… hours → round to **4.85 hours**.

**Arithmetic used (digit-by-digit):**  
500 ÷ 103 ≈ 4.854369 (rounded to 4.85 h).

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | **82 mA** |
| Total required on 5 V rail (w/ 25% margin) | **103 mA** |
| Regulator chosen | **LM7805** (linear) |
| Regulator dissipation (9→5 V at 103 mA) | **≈ 0.412 W** |
| External supply recommended | 9 V DC adapter, **≥ 500 mA** |
| Estimated battery life (9 V, 500 mAh) | **~4.85 hours** |
| Action required (finalization) | **Replace MCU / Curiosity Nano estimate (50 mA) with absolute maximum values from PIC18F16Q41 datasheet and Curiosity Nano board docs. Recompute totals.** |

### Notes & tips
- If final MCU + board draw (with peripherals) is **≤ 100 mA**, you may choose the smaller **UA78L05ACLP** (TO-92) to save board space and quiescent current — but verify the UA78L05ACLP absolute max (100 mA) and that your final margin stays ≥ 25%.  
- If your final total (with margin) exceeds the UA78L05ACLP rating, **use LM7805** (or a small LDO rated >200 mA) to avoid regulator saturation.  
- For the final power-budget PDF, replace the “estimate” values with datasheet values (especially MCU) and include links to each datasheet/product page in your GitHub page.

If you want, I can now:
- Fetch and insert the **PIC18F16Q41 absolute-max active current** and the **Curiosity Nano board idle/USB current** from Microchip documents and update the `.md` automatically. (I already located the relevant Microchip documents and can extract numbers next if you want me to.)  
- Or I can produce a downloadable ZIP containing both `ComponentSelection.md` (the version with your chosen parts) and this `PowerBudget.md`.
