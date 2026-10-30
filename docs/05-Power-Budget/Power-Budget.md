---
title: Power Budget
tags:
- Power Budget
- KiCad
- Subsystem
---

## Overview
A comprehensive Power Budget was performed for the custom non-contact optical sensing and signal processing subsystem (Team 104) to evaluate total current requirements across all active devices and operational states. Operating from a 9V PP3 transistor battery supply connected through a J1 barrel jack connector, the power rail feeds an LM7805 linear voltage regulator (U1) to establish a stable +5V rail. The power budget verifies that peak current consumption remains within safe bounds for the LM7805 regulator, preserves sufficient headroom for the 0.5A inline fuse (F1), and guarantees reliable continuous power delivery to the PIC18F57Q43 microcontroller, op-amp signal conditioning circuitry, optical sensor, and alert indicators.

## Pin Table

*Table 1: PIC18F57Q43 Pin Assignments and Subsystem Hardware Mapping.*

| PIC18F57Q43 Pin | Component | Function |
|:---|:---|:---|
| RA0 | LM324 Op-Amp (OPB732 Signal) | Analog input (ADC distance sensor signal) |
| RA1 | PT-1407 Piezo Buzzer (BZ1) | Digital output (PWM audio alert drive) |
| RD0 | Debug Red LED (D1) | Digital output (Status indicator) |
| RD1 | Pushbutton Switch (SW1) | Digital input (User debug button) |
| RD2 | Header Connector (J3 Pin 1) | Digital output (Trigger signal to motor board) |
| VDD | +5V Rail (L7805 Regulator) | +5V Power supply input |
| GND | Common Ground / Earth | Common system ground reference |


<img width="1163" height="655" alt="image" src="https://github.com/user-attachments/assets/c662ef32-3796-47ac-a0f9-0631cab1441f" />


## Summary Table

| Rail / Power Stage | Component / Section | Part Number | Supply Voltage Range | Qty | Max Current per Unit (mA) | Total Current (mA) | Unit |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **+5V Rail** | PIC Microcontroller | PIC18F57Q43 | +1.8V - 5.5V | 1 | 30.0 | 30.0 | mA |
| **+5V Rail** | Quad Op-Amp Buffer | LM324N | +3.0V - 32V | 1 | 3.0 | 3.0 | mA |
| **+5V Rail** | Reflective Optical Sensor | OPB732 | +5.0V | 1 | 17.3 | 17.3 | mA |
| **+5V Rail** | Piezoelectric Buzzer | PT-1407 | +3.0V - 15V | 1 | 15.0 | 15.0 | mA |
| **+5V Rail** | Debug Status LED (Red) | Standard LED | +1.4V - 2.0V | 1 | 9.1 | 9.1 | mA |
| **+5V Rail** | **Subtotal** | | | | | **74.4** | **mA** |
| **+5V Rail** | **Safety Margin (25%)** | | | | | **18.6** | **mA** |
| **+5V Rail** | **Total Current Required** | | | | | **93.0** | **mA** |
| **Regulator (+5V)** | LM7805 Regulator Output | LM7805 | +7.0V - 35V | 1 | 1000.0 | 1000.0 | mA |
| **Regulator (+5V)** | **Total Remaining Current** | | | | | **907.0** | **mA** |
| **External Source** | 9V Alkaline Battery | 6LR61 / PP3 | 9V DC | 1 | 500.0 | 500.0 | mA |
| **External Source** | **Total Remaining Current** | | | | | **407.0** | **mA** |

## Conclusions

From the prepared Power Budget, the subsystem draws a nominal total current of 74.4 mA across the +5V rail under full active operation. Applying a standard 25% engineering safety margin increases the design budget baseline to 93.0 mA.

Key findings from this analysis include:
1. **Regulator Capacity & Thermal Safety:** The onboard LM7805 linear regulator provides up to 1000 mA (1A) of continuous current. Operating at 93.0 mA leaves 907.0 mA of remaining current capacity, ensuring the regulator runs cool without requiring forced air or bulky heatsinking.
2. **Battery Life Expectancy:** Powered by a standard 9V alkaline battery (rated at ~550 mA capacity), the total system current requirement of 93.0 mA provides an expected continuous battery runtime of approximately 5.9 hours under full continuous operation.
3. **Fuse Protection Compatibility:** The input line's 0.5A (500 mA) fast-acting fuse (F1) operates at less than 20% of its blow rating during normal operation, eliminating thermal wear while offering rapid fault isolation during overcurrent conditions.

## Resources

The power budget as a PDF download is available [here](PowerBudgetExample.pdf), and a Microsoft Excel Sheet [here](PowerBudgetExample.xlsx).
