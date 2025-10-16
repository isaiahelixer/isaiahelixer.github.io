---
title: Power Budget
---

# Power Budget

**Team Number:** 101
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** Isaiah LaCombe
**Version:** 1.0  

---

## Section A – All Major Components

| **Component Name** | **Part Number / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|---------------------------|------------------------|-----------|---------------------------|------------------------|
| Microcontroller | PIC18F16Q41 Curiosity Nano) | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | Capacitive v1.2 | 5 | 1 | 10 | 10 |
| Temperature/Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | YL-83 | 5 | 1 | 10 | 10 |
| Indicator LED | Generic | 5 | 1 | 10 | 10 |
| **Subtotal** | | | | | **532 mA** |

---

## Section B – Power Rails

### +5 V Rail
Total current = 82 mA  
Safety margin (25%) = 82 × 1.25 = **103 mA**

---

## Section C – Regulator Selection

| **Regulator Option** | **Voltage Input Range** | **Max Output Current (mA)** | **Pros** | **Cons** |
|----------------------|-------------------------|-----------------------------|-----------|-----------|
| LM7805 Linear Regulator | 7 – 35 V | 1000 | Simple, low noise | Inefficient drop (9 → 5 V = 4 V × I loss) |
| LM2596 Buck Converter | 6 – 40 V | 2000 | High efficiency | Slight switching noise |

**Choice:** LM7805 Linear Regulator  
**Rationale:** For a total current near 100 mA, heat dissipation (≈ 0.4 W) is acceptable, and the clean output minimizes noise on analog sensor signals.

---

## Section D – External Power Source

| **Power Source** | **Part Number / Example** | **Input Range (V)** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|---------------------------|---------------------|------------------------|----------------------|
| Plug-in Wall Adapter | Generic 9 V DC Adapter | 100–240 VAC | 9 V DC | 500 |

**Connected Regulator:** LM7805  
**Required Current:** 103 mA (with margin)  
**Remaining Current Available:** ≈ 397 mA  

If powered by a 9 V 500 mAh battery:  
Battery Life = 500 mAh / 103 mA ≈ **4.8 hours (worst-case)**

---

## Section E – Summary

| **Item** | **Value** |
|-----------|-----------|
| Total Required on 5 V Rail (w/ 25% margin) | 103 mA |
| Regulator Choice | LM7805 Linear Regulator |
| External Power Source | 9 V Wall Adapter (≥ 500 mA) |
| Estimated Battery Life (9 V 500 mAh) | ~4.8 hours |
