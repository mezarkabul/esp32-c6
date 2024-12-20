# Antenna Matching Circuit for ESP32-C6

This document provides details for designing an impedance matching circuit to connect an ESP32-C6 microcontroller (input impedance: 35 + 0j Ω) to a 50-ohm antenna. The target operating frequency is 2.425 GHz.

---

## Objective
To design an L-network matching circuit to ensure efficient power transfer between the ESP32-C6 and the antenna by matching their impedances.

---

## Circuit Configuration
Given the antenna impedance (Ω50 Ω) is higher than the ESP32-C6 input impedance (Ω35 Ω), a **low-pass L-network** configuration is used:

- **Series Component**: Inductor (L)
- **Shunt Component**: Capacitor (C)

---

## Component Calculation


![resonant_frequency_calculation](https://github.com/user-attachments/assets/cb90a101-60c6-4cd1-bca9-735ea93a6af1)

---

## Final Component Values
- **Series Inductor (μL)**: **2.2 nH**
- **Shunt Capacitor (μC)**: **4 pF**

---

## Circuit Diagram
```
      Antenna     Series Inductor     ESP32-C6
      -----o---- L (2.2 nH) ----o-----
                 |                  |
                 C (4 pF)      C (4 pF) 
                 |                  |
                GND                GND
```

---

## Notes
1. Component tolerances can affect performance; use precision components for best results.
2. Ensure the PCB layout minimizes parasitic inductance and capacitance.
3. Verify the matching network performance with a vector network analyzer (VNA).


