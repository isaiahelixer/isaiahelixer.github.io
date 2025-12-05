---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Sensor Subsystem Board  
**Team Member Names:** Liam, Isaiah, Myles, and Raj  
**Version:** 1.6  

**System input:** 9V external → 5V regulator (LM7805) → Soil Moisture Sensor + MCP6004 → Op-Amp PIC18F57Q43 Curiosity Nano

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller Curiosity Nano | PIC18F57Q43 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | DIY Capacitive (5 V PWM, 10 kΩ–1 MΩ–0.1 µF RC) | 5 | 1 | 0.1 | 0.1 |
| Operational Amplifier | MCP6004 (Quad Op-Amp, TH) | 5 | 1 | 23 | 23 |
| **Subtotal** | | | | | **523.1 mA** |

**Arithmetic component sum:**  
500 + 0.1 + 23 = 523.1 mA total subsystem current

## Section B – Power Rails

**+5 V Rail**
- Subtotal = 523.1 mA  
- Safety margin (25%) = 523.1 × 1.25 = 653.875 mA  

**Arithmetic (with margin):**  
523.1 × 1.25 = (523.1 × 5) / 4 = 2615.5 / 4 = 653.875 mA  

Rounded total for spec/selection: ≈ 655 mA

## Section C – Regulator Selection

| **Regulator Option** | **Input Range (V)** | **Max Output (mA)** | **Pros** | **Cons** |
|----------------------|---------------------:|--------------------:|----------|---------|
| LM7805 linear | 7 – 25 V | 1500 | Simple, low noise, reliable | Inefficient (9V→5V drop causes heat; needs heat sink) |
| UA78L05ACLP TO-92, 100 mA max | 7 – 35 V | 100 | Compact, low quiescent current | Not enough output current for system needs |

Choice: LM7805 Linear Regulator  

**Rationale:**  
With a total estimated current requirement of ~655 mA including margin, the LM7805 1.5 A rated provides ample output capacity and thermal headroom.  
The UA78L05ACLP 100 mA is insufficient.

**Regulator heat / dissipation check:**  
- Voltage drop = 9 V − 5 V = 4 V  
- Load current with margin = 655 mA = 0.655 A  
- Power dissipated = 4 V × 0.655 A = 2.62 W

Result: LM7805 will require a small heat sink for continuous operation.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on +5 V rail with 25% margin: 655 mA  
- Remaining capacity on 9V, 3A adapter: 3000 − 655 = 2345 mA

**Arithmetic:**  
3000 − 655 = 2345 mA remaining

**Battery Option (not implemented):**  
If powered by a 3000 mAh battery for estimation only:

- Example sleep-mode average current = 50 mA → battery life = 3000 / 50 = 60 hours ≈ 2.5 days  
- With active current near full draw 523 mA: 3000 / 523 ≈ 5.73 hours (not practical for continuous operation)

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Estimated subtotal | 523.1 mA |
| Total required on 5 V rail (with 25% margin) | 655 mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation 9→5 V at 655 mA | ≈ 2.62 W (heat sink required) |
| External supply recommended | 9 V DC adapter, ≥ 3 A |
| Estimated battery life (3000 mAh Li-ion) | ≈ 60 h (sleep-mode avg) / ≈ 5.7 h being continuous active draw |

**Power budget Conclusion:**  
I used the power budget to estimate the max current each major part of the subsystem would draw and then added those numbers to find the total system load. Once I had the subtotal, I applied a 25% safety margin to make sure the design would handle higher-than-expected current spikes or future additions. This final value told me what the 5 V rail needed to supply and helped determine which voltage regulator was appropriate.

From the budget our system needs about 655 mA so the LM7805 was the only regulator with enough headroom. The power budget also showed that the regulator would dissipate around 2.6 W meaning a heat sink may be required. Comparing this to our 9 V, 3 A adapter confirmed the external supply can easily support the load with plenty of current to spare. The budget also made it clear that battery power is not practical for continuous operation due to the high draw.


