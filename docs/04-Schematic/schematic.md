---
title: Schematic
---

## Overview

This schematic is designed to support a non-contact optical sensing and signal-processing subsystem powered by a regulated 9V DC supply. Power enters through the J1 barrel jack—protected at the input entry point by a 0.5A inline fuse (F1) and decoupled via C1 (0.33uF)—before being stepped down to a stable +5V rail using an L7805 linear voltage regulator with output filtering (C2, 0.1uF). The system is controlled by a high-performance PIC18F57Q43 microcontroller, which interacts with an onboard debug interface consisting of a pushbutton switch on RD1 and a current-limited status LED on RD0.
Functionally, the system continuously monitors target proximity using an OPB732 reflective optical switch driven at approx. 17.3mA via R2 (220 ohm). The sensor's phototransistor output is conditioned through an LM324N operational amplifier buffer to provide a clean analog voltage swing into the PIC's RA0 ADC input pin (Pin 43) for software decoding and real-time serial debug logging to PuTTY via CDC_TX/CDC_RX. Upon detecting an active event, the microcontroller triggers local audible feedback via a PT-1407 piezo buzzer on PWM pin RA1 while simultaneously asserting digital pin RD2 (Pin 22) to send a high-level trigger pulse out through inter-board header J3 (Pin 1) to drive the downstream motor subsystem.


![schematic]<img width="1220" height="837" alt="image" src="https://github.com/user-attachments/assets/922a1397-30eb-4a03-b52f-2a74c1038bac" />

**Figure 1:** Schematic


## Resouces

The schematic as a PDF download is available [*here*](SubsystemDesign2.pdf), and the Zip folder of the project [*here*](EGR_304_Subsystem_Design.zip).
