---
title: Power Budget
---

# Power Budget

**Team Number:** —  
**Project Name:** Smart Irrigation Subsystem Board  
**Team Member Names:** (Your Name)  
**Version:** 1.0  

**System input:** 9 V external → 5 V regulator → PIC18F16Q41 Curiosity Nano + sensors

> NOTE: The current values below are **estimates**. For the final submission you **must** replace the MCU and module currents with the *absolute maximum current* values from the PIC18F16Q41 datasheet and Curiosity Nano documentation.

---

## Section A – All Major Components (estimates)

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F16Q41 Curiosity Nano (estimate) | 5 | 1 | **50 (estimate)** | 50 |
| Soil Moisture Sensor | Capacitive v1.2 | 5 | 1 | 10 | 10 |
| Temperature/Humidity Sensor | SHT31-D | 5 | 1 | 2 | 2 |
| Rain Sensor | YL-83 analog module | 5 | 1 | 10 | 10 |
| Indicator LED | Generic status LED | 5 | 1 | 10 | 10 |
| **Subtotal (estimated)** | | | | | **82 mA** |

> **Replace** the "Microcontroller" row value (50 mA) with the PIC18F16Q41 **absolute maximum** current from Microchip (and include Curiosity Nano board consumption if you plan to use the development board rather than the bare MCU).

---

## Section B – Power Rails

### +5 V Rail
- Subtotal (estimated) = **82 mA**  
- Safety margin (25%) → 82 × 1.25 = **102.5 mA** → round to **103 mA**

---

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 35 V | 1000 | Low noise, simple | Inefficient (dissipates (9–5)V × I) |
| LM2596 (buck) | 6 – 40 V | 2000 | High efficiency, low heat | Switching noise; filter may be required |

**Choice:** LM7805 Linear Regulator  
**Rationale:** With estimated 103 mA load the dissipation is ≈ 4 V × 0.103 A = 0.412 W — acceptable without a large heatsink. LM7805 gives a clean rail which benefits analog readings. If measured final current > 200–300 mA, switch to a buck regulator.

---

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9 V DC Adapter | 9 V | 500 mA |

- Required on +5 V rail (with margin): **103 mA**  
- Remaining capacity on 9 V adapter (500 mA): ≈ **397 mA**

**Battery option example:** 9 V alkaline ~500 mAh  
- Battery life ≈ Capacity / Load = 500 mAh / 103 mA ≈ **4.85 hours** (worst-case)

---

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Total required on 5 V rail (w/ 25% margin) | **103 mA** (estimate) |
| Regulator chosen (example) | LM7805 Linear Regulator |
| External supply | 9 V wall adapter ≥ 500 mA recommended |
| Estimated battery life (9 V, 500 mAh) | ~4.8 hours (worst-case) |
| Action required | **Replace MCU/Curiosity Nano current estimate with absolute max values from datasheet** |

---

### How to finalize
1. Open the PIC18F16Q41 datasheet / Curiosity Nano documentation.  
2. Find absolute maximum current values for the MCU (active modes, peripherals enabled) and add any extra consumption from the Curiosity Nano board (USB interface, LEDs, onboard regulator) if you plan to use the development board.  
3. Replace the estimate in Section A and recompute totals in Sections B–E.  
4. If final current > ~200–300 mA, switch the regulator choice to a buck converter and recalculate heat and battery life.
