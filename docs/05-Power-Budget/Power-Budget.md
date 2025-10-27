---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Sensor Subsystem Board  
**Team Member Names:** Liam, Isaiah, Myles, and Raj  
**Version:** 1.3  

**System input:** 9V external → 5V regulator (LM7805) → PIC18F57Q43 Curiosity Nano + Soil Moisture Sensor + MCP6004 Op-Amp

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F57Q43 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 5 | 5 |
| Operational Amplifier | MCP6004 (Quad Op-Amp, TH) | 5 | 1 | 23 | 23 |
| **Subtotal** | | | | | **528 mA** |

**Arithmetic (component sum):**  
500 + 5 + 23 = 528 mA total subsystem current

## Section B – Power Rails

**+5V Rail**
- Subtotal = 528 mA  
- Safety margin (25%) = 528 × 1.25 = 660 mA

**Arithmetic (with margin):**  
528 × 1.25 = (528 × 5) / 4 = 2640 / 4 = 660.0 mA

**Rounded total (for spec/selection):** 660 mA

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25V | 1500 | Simple, low noise, reliable | Inefficient (9V→5V drop causes heat; needs heat sink) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35V | 100 | Compact, low quiescent current | Not enough output current for system needs |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With a total estimated current requirement of 660 mA (including margin), an LM7805 (1.5 A rated in common packages or variants) provides ample output capacity and thermal design margin. The UA78L05ACLP (100 mA) is insufficient.

**Regulator heat / dissipation check:**  
- Voltage drop = 9 V − 5 V = 4 V  
- Load current (with margin) = 660 mA = 0.660 A  
- Power dissipated = 4 V × 0.660 A = 2.64 W

**Result:** The LM7805 will require a small heat sink for continuous operation at this load.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on +5V rail (with 25% margin): 660 mA  
- Remaining capacity on 9V, 3A adapter: 3000 − 660 = 2340 mA

**Arithmetic:**  
3000 − 660 = 2340 mA remaining

**Battery Option (not implemented):**  
If powered by a 3000 mAh battery (for estimation only):

- Example sleep-mode average current = 50 mA → battery life = 3000 mAh / 50 mA = 60 hours (≈ 2.5 days)  
- With active current near the full draw (528 mA), battery life = 3000 / 528 ≈ 5.68 hours (not practical for continuous operation)

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | 528 mA |
| Total required on 5V rail (with 25% margin) | 660 mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation (9→5V at 660 mA) | ≈ 2.64 W (heat sink required) |
| External supply recommended | 9V DC adapter, ≥ 3 A |
| Estimated battery life (3000 mAh Li-ion) | ≈ 60 hours (sleep-mode avg) / ≈ 5.7 hours (continuous active draw) |

**Conclusion:**  
After including the MCP6004 (23 mA max), the subsystem’s estimated current draw is 528 mA. With a 25% safety margin the design calls for 660 mA on the 5V rail. The chosen LM7805 regulator will need a small heat sink to safely dissipate about 2.64 W when powered from the 9V adapter. The 9V, 3A wall adapter provides ample headroom (≈ 2.34 A spare capacity).

