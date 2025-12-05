---
title: Power Budget
---

# Power Budget

**Team Number:** 101  
**Project Name:** Smart Irrigation Capacitve Soil Sensor Subsystem Board  
**Team Member Names:** Liam, Isaiah, Myles, and Raj  
**Version:** 1.9  

**System input:** 9V external → 5V regulator (LM7805) → Soil Moisture Sensor + MCP6004 → PIC18F57Q43 Curiosity Nano

## Section A – All Major Components 

| **Component Name** | **Part / Example** | **Supply Voltage (V)** | **Qty.** | **Abs. Max Current (mA)** | **Total Current (mA)** |
|--------------------|--------------------|------------------------:|--------:|--------------------------:|-----------------------:|
| Microcontroller Curiosity Nano | PIC18F57Q43 Curiosity Nano | 5 | 1 | 500 | 500 |
| Soil Moisture Sensor | DIY Capacitive | 5 | 1 | 0.1 | 0.1 |
| Operational Amplifier | MCP6004 (Quad Op-Amp, TH) | 5 | 1 | 23 | 23 |
| **Subtotal** | | | | | **523.1 mA** |

**Arithmetic component sum:**  
500 + 0.1 + 23 = **523.1 mA total subsystem current**

## Section B – Power Rails

**+5 V Rail**
The following components are powered directly from the 5 V rail:

- PIC18F57Q43 Curiosity Nano  
- MCP6004 Quad Op-Amp  
- DIY Capacitive Soil Moisture Sensor  

Rail subtotal: 523.1 mA  
25% safety margin: 523.1 × 1.25 = 653.875 mA

Rounded for specification: ≈ 655 mA required from the 5 V rail

## Section C – Regulator Selection (Final Choice)

### Selected Regulator: LM7805 Linear Regulator

| **Parameter** | **Value** |
|--------------:|-----------|
| Input Voltage | 9 V from wall adapter |
| Output Voltage | 5 V |
| Max Output Current | 1.5 A |
| Required Current (with margin) | 655 mA |
| Meets Requirement? | Yes |

**Rationale:**  
The LM7805 provides more than enough headroom for the estimated 655 mA system demand. It is simple, reliable, and already available for use. Lower-current regulators (e.g., 100 mA TO-92 types) cannot support the system load.

### **Regulator Power Dissipation Check**

- Voltage drop: 9 V − 5 V = 4 V 
- Load current (with margin): 0.655 A 
- Power dissipated:  
  4 V × 0.655 A = 2.62 W

**Conclusion:** A small heat sink may be required for large continuous current draw.

## Section D – External Power Source

| **Power Source** | **Example** | **Output Voltage (V)** | **Max Current (mA)** |
|------------------|-------------:|------------------------:|---------------------:|
| Wall Adapter | Generic 9V DC Adapter | 9 | 3000 |

- Required on 5 V rail (with margin): **655 mA**  
- Remaining adapter capacity:  
  3000 − 655 = **2345 mA**

Battery Option (not implemented): 
- If powered by a 3000 mAh Li-ion:  
  - Sleep-mode (50 mA avg): 60 hours  
  - Full draw (523 mA): ≈ 5.7 hours

## Section E – Summary

| **Item** | **Value / Action** |
|---------:|--------------------|
| Estimated subtotal | 523.1 mA |
| Required 5 V rail with 25% margin | 655 mA |
| Regulator chosen | LM7805 Linear Regulator |
| Regulator dissipation | ≈ 2.62 W (heat sink needed) |
| External supply recommended | 9 V DC adapter, ≥ 3 A |
| Estimated battery life (3000 mAh) | 60 h (sleep) / 5.7 h (active) |

## Power Budget Conclusion

I used the power budget to estimate the maximum current each major part draws and summed them to find the total system load. After applying a 25% safety margin, this established the requirement for the 5 V rail. Since the rail needs around 655 mA, the LM7805 was the only regulator with enough output capacity. The calculations also showed the regulator would dissipate about 2.6 W, meaning a heat sink is required. A 9 V, 3 A wall adapter easily supports this load with plenty of current to spare.



