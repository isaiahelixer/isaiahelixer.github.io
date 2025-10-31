---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Sensor Subsystem Board  
**Team Member Names:** Liam, Isaiah, Myles, and Raj  
**Version:** 1.4  

**System input:** 9V external → 5V regulator (LM7805) → Soil Moisture Sensor + MCP6004 → Op-Amp PIC18F57Q43 Curiosity Nano

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller (Curiosity Nano) | PIC18F57Q43 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | ST0160 Capacitive | 5 | 1 | 20 | 20 |
| Operational Amplifier | MCP6004 (Quad Op-Amp, TH) | 5 | 1 | 23 | 23 |
| **Subtotal** | | | | | **543 mA** |

**Arithmetic (component sum):**  
500 + 20 + 23 = 543 mA total subsystem current

## Section B – Power Rails

**+5V Rail**
- Subtotal = 543 mA  
- Safety margin (25%) = 543 × 1.25 = 678.75 mA

**Arithmetic (with margin):**  
543 × 1.25 = (543 × 5) / 4 = 2715 / 4 = 678.75 mA

**Rounded total (for spec/selection):** 680 mA

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 (linear) | 7 – 25V | 1500 | Simple, low noise, reliable | Inefficient (9V→5V drop causes heat; needs heat sink) |
| UA78L05ACLP (TO-92, 100 mA max) | 7 – 35V | 100 | Compact, low quiescent current | Not enough output current for system needs |

**Choice:** LM7805 Linear Regulator  

**Rationale:**  
With a total estimated current requirement of ~680 mA (including margin), the LM7805 (1.5 A rated) provides ample output capacity and thermal headroom. The UA78L05ACLP (100 mA) is insufficient.

**Regulator heat / dissipation check:**  
- Voltage drop = 9 V − 5 V = 4 V  
- Load current (with margin) = 680 mA = 0.680 A  
- Power dissipated = 4 V × 0.680 A = 2.72 W

**Result:** The LM7805 will require a small heat sink for continuous operation at this load.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on +5V rail (with 25% margin): 680 mA  
- Remaining capacity on 9V, 3A adapter: 3000 − 680 = 2320 mA

**Arithmetic:**  
3000 − 680 = 2320 mA remaining

**Battery Option (not implemented):**  
If powered by a 3000 mAh battery (for estimation only):

- Example sleep-mode average current = 50 mA → battery life = 3000 mAh / 50 mA = 60 hours (≈ 2.5 days)  
- With active current near the full draw (543 mA), battery life = 3000 / 543 ≈ 5.52 hours (not practical for continuous operation)

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Subtotal (estimated) | 543 mA |
| Total required on 5V rail (with 25% margin) | 680 mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation (9→5V at 680 mA) | ≈ 2.72 W (heat sink required) |
| External supply recommended | 9V DC adapter, ≥ 3 A |
| Estimated battery life (3000 mAh Li-ion) | ≈ 60 hours (sleep-mode avg) / ≈ 5.5 hours (continuous active draw) |

**Conclusion:**  
After correcting the soil moisture sensor draw to 20 mA and including the MCP6004 (23 mA max), the subsystem’s estimated current draw is 543 mA. With a 25% safety margin, the design calls for ~680 mA on the 5V rail. The LM7805 regulator remains suitable but will dissipate about 2.72 W and requires a small heat sink for safe continuous operation. The 9V, 3A wall adapter provides ample spare capacity (≈ 2.32 A).
