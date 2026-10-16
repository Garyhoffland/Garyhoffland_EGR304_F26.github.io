---
title: Component Selection
---

# Component Selection - Pet Interaction & Audio Alert

## 1. Voltage Regulator Module

1. **L7805ABV-DG (5V 1.5A Linear Regulator)** *(Currently In-Stock)*

    * $0.88 / each
    * [STMicroelectronics L7805ABV-DG Datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/41/4f/b3/b0/12/d4/47/88/CD00000444.pdf)
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805ABV-DG/3945936)

    | Pros | Cons |
    | --- | --- |
    | Already available on hand (zero additional cost) | Requires thermal consideration under high current draw |
    | TO-220 package allows easy breadboard and through-hole PCB assembly | Linear topology dissipates excess voltage ($9\text{V} \rightarrow 5\text{V}$) as heat |
    | Provides stable $5\text{V DC}$ output up to $1.5\text{A}$, fully powering the PIC18, LM324, and speaker driver | |

2. **LM2596S-5.0 (Buck Switching Regulator)**

    * $2.50 / each
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/texas-instruments/LM2596S-5-0-NOPB/363497)

    | Pros | Cons |
    | --- | --- |
    | Highly efficient ($>80\%$) switching conversion | Requires external power inductor, catch diode, and filter capacitors |
    | Low heat generation | Higher component count and complex PCB layout footprint |

**Choice:** Option 1: STMicroelectronics L7805ABV-DG

**Rationale:** The L7805ABV-DG is already on hand. Because the subsystem consumes under $300\text{mA}$ total continuous current, power dissipation across the regulator is well within safe operating parameters for the TO-220 through-hole package without needing an extra heatsink.

---

## 2. Microcontroller

1. **PIC18F57Q43 Curiosity Nano Development Board** *(Currently In-Stock)*

    * Pre-selected Course Requirement
    * [PIC18F57Q43 Hardware User Guide](https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/UserGuides/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf)

    | Pros | Cons |
    | --- | --- |
    | Required development platform for EGR304 | DIP/through-hole header style occupies larger PCB footprint |
    | On-board PKOB4 programmer/debugger over USB | |
    | Integrated $12\text{-bit}$ ADC (`ADC1`), $8\text{-bit}$ DAC, Configurable Logic Cells (CLC), and PWM peripherals | |

**Choice:** Microchip PIC18F57Q43 Curiosity Nano Board

**Rationale:** Standardized required core processing board across all EGR304 team subsystems.

---

## 3. Motion / Pet Detection Sensor

1. **Kit Photoresistor / Light Dependent Resistor (LDR)** *(Currently In-Stock)*

    * $0.00 (Included in provided kit, Item 18)
    * Generic CdS Photoresistor

    | Pros | Cons |
    | --- | --- |
    | On hand; simple voltage divider interface with a $10\text{k}\Omega$ resistor | Sensitive to ambient light variations; requires calibration |
    | Detects light blockage when a pet approaches the feeding dish | Slower optical response time ($20\text{--}30\text{ms}$) |

2. **EKMC1601111 (Panasonic PIR Motion Sensor IC)**

    * $8.45 / each
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/panasonic-electric-works/EKMC1601111/6232149)

    | Pros | Cons |
    | --- | --- |
    | True passive infrared thermal motion detection | High cost per unit |
    | Integrated lens and digital output conditioning | Requires purchasing new parts and waiting for shipping |

**Choice:** Option 1: Kit Photoresistor (LDR)

**Rationale:** The kit photoresistor is readily available on hand. Configured in a voltage divider circuit into the LM324N non-inverting op-amp stage, it reliably registers pet proximity when the optical beam or overhead light path above the bowl is obstructed.

---

## 4. Signal Conditioning (Op-Amp)

1. **LM324N Quad General Purpose Operational Amplifier** *(Currently In-Stock)*

    * $0.82 / each
    * [TI LM324N Datasheet](https://www.ti.com/lit/ds/symlink/lm224.pdf)
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627)

    | Pros | Cons |
    | --- | --- |
    | On hand; 14-pin DIP through-hole package | Not a true rail-to-rail output swing (max output $\approx V_{CC} - 1.5\text{V}$) |
    | Four independent channels allow scaling multiple sensor inputs | Higher offset voltage compared to modern precision op-amps |
    | Operates directly from a single $+5\text{V}$ supply rail | |

2. **TLV2374IN (Texas Instruments Rail-to-Rail Quad Op-Amp)**

    * $2.15 / each
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/texas-instruments/TLV2374IN/379261)

    | Pros | Cons |
    | --- | --- |
    | True rail-to-rail input and output capability | Requires purchasing new component |
    | Low supply current ($560\mu\text{A/ch}$) | Higher unit price |

**Choice:** Option 1: Texas Instruments LM324N

**Rationale:** The LM324N is currently on hand in a DIP-14 package. Configured as a non-inverting amplifier, it buffers and scales the photoresistor voltage divider signal into the PIC18F57Q43 `RA0` (`ADC1`) input within the $0\text{--}3.5\text{V}$ dynamic range without requiring external purchases.

---

## 5. Audio Alert Output

1. **8-Ohm Dynamic Speaker** *(Currently In-Stock)*

    * $0.00 (On hand component)
    * Standard 8-Ohm, 0.25W Mylar/Paper Cone Speaker

    | Pros | Cons |
    | --- | --- |
    | On hand; capable of playing complex multi-tone audio meal chimes via PWM | Requires a transistor (PN2222A) driver stage due to low impedance ($8\Omega$) |
    | Richer tone and higher acoustic output than a piezo buzzer | Draws higher peak current ($\approx 100\text{mA}$) during tone generation |

2. **PS1240P02BT (TDK Piezoelectric Buzzer)**

    * $0.95 / each
    * [DigiKey Product Page](https://www.digikey.com/en/products/detail/tdk-corporation/PS1240P02BT/935922)

    | Pros | Cons |
    | --- | --- |
    | Very low power consumption ($<10\text{mA}$) | Limited frequency response; plays only high-pitched single tones |
    | Drives directly from GPIO | Requires separate purchase and shipping |

**Choice:** Option 1: 8-Ohm Dynamic Speaker (Driven by Kit PN2222A NPN Transistor)

**Rationale:** The 8-Ohm speaker is already on hand. Interfaced to pin `RA1` via a PN2222A NPN transistor (from the provided kit, Item 10)[cite: 4] with a current-limiting base resistor and flyback diode, it produces audible feeding alerts directly controlled by the PIC's PWM module.
