---
title: Bill of Materials
tags:
- BOM
- KiCad
- Subsystem
---

## Overview
This Bill of Materials details all electronic components, connectors, power regulation stages, and electro-mechanical hardware required to assemble the custom non-contact optical sensing and processing subsystem. All unit pricing and vendor links correspond to active DigiKey stock items to support immediate procurement.

## Bill of Materials Example (as Table)

*Table 1: Subsystem Component Specifications and Procurement Details.*

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacture** | **Manufacturer #** | **Vendor Link** | **Datasheet Link** | **Schematic Reference Designators** |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|
| 2.1mm x 5.5mm DC Barrel Power Jack | 1 | $1.25 | $1.25 | CUI Devices | PJ-002AH | [DigiKey](https://www.digikey.com/en/products/detail/cui-devices/PJ-002AH/1640746) | [Datasheet](https://www.cuidevices.com/product/resource/pj-002ah.pdf) | J1 |
| 0.5A 250V Fast-Acting Cartridge Fuse | 1 | $0.85 | $0.85 | Littelfuse | 0217.500MXP | [DigiKey](https://www.digikey.com/en/products/detail/littelfuse-inc/0217-500MXP/777284) | [Datasheet](https://www.littelfuse.com/media?resourcetype=datasheets&itemid=1f6611f7-bc71-460b-ba62-258ba9c94f57&filename=littelfuse-fuse-217-datasheet.pdf) | F1 |
| 5V 1.5A Linear Voltage Regulator, TO-220 | 1 | $0.78 | $0.78 | STMicroelectronics | L7805CV | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) | [Datasheet](https://www.st.com/resource/en/datasheet/l7805.pdf) | U1 |
| 0.33 µF Aluminum Electrolytic Capacitor, 50V | 1 | $0.20 | $0.20 | Panasonic | ECA-1HHR33B | [DigiKey](https://www.digikey.com/en/products/detail/panasonic-electronic-components/ECA-1HHR33B/2688863) | [Datasheet](https://industrial.panasonic.com/ww/products/pt/aluminum-cap) | C1 |
| 0.1 µF Ceramic Capacitor, 50V, X7R, Through-Hole | 4 | $0.15 | $0.60 | KEMET | C315C104K5R5TA | [DigiKey](https://www.digikey.com/en/products/detail/kemet/C315C104K5R5TA/3722304) | [Datasheet](https://content.kemet.com/datasheets/KEM_C1049_GOLDMAX_300_X7R.pdf) | C2, C3, C4, C5 |
| 100 Ω Resistor, 1/2W (0.5W), 5%, Through-Hole | 1 | $0.10 | $0.10 | Yageo | CFR-50JB-52-100R | [DigiKey](https://www.digikey.com/en/products/detail/yageo/CFR-50JB-52-100R/13000) | [Datasheet](https://www.yageo.com/upload/3r/contents/files/CFR.pdf) | R1 |
| 220 Ω Resistor, 1/4W (0.25W), 1%, Through-Hole | 1 | $0.10 | $0.10 | Yageo | MFR-25FTE52-220R | [DigiKey](https://www.digikey.com/en/products/detail/yageo/MFR-25FTE52-220R/13012) | [Datasheet](https://www.yageo.com/upload/3r/contents/files/MFR.pdf) | R2 |
| 100 Ω Resistor, 1/4W (0.25W), 1%, Through-Hole | 2 | $0.10 | $0.20 | Yageo | MFR-25FTE52-100R | [DigiKey](https://www.digikey.com/en/products/detail/yageo/MFR-25FTE52-100R/13008) | [Datasheet](https://www.yageo.com/upload/3r/contents/files/MFR.pdf) | R3, R6 |
| 10 kΩ Resistor, 1/8W (0.125W), 1%, Through-Hole | 2 | $0.10 | $0.20 | Yageo | MFR-12FTE52-10K | [DigiKey](https://www.digikey.com/en/products/detail/yageo/MFR-12FTE52-10K/12984) | [Datasheet](https://www.yageo.com/upload/3r/contents/files/MFR.pdf) | R4, R5 |
| Reflective Optical Flag Sensor Module | 1 | $14.28 | $14.28 | TT Electronics | OPB732 | [DigiKey](https://www.digikey.com/en/products/detail/tt-electronics-optek-technology/OPB732/1637069) | [Datasheet](https://www.ttelectronics.com/TTElectronics/media/ProductFiles/Datasheet/OPB732.pdf) | J2 |
| General Purpose Quad Op-Amp, DIP-14 | 1 | $0.62 | $0.62 | Texas Instruments | LM324N | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277042) | [Datasheet](https://www.ti.com/lit/ds/symlink/lm324.pdf) | U2 (GH-LM324N1) |
| PIC18F57Q43 Curiosity Nano Evaluation Board | 1 | $21.85 | $21.85 | Microchip Technology | DM164150 | [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/DM164150/13540093) | [Datasheet](https://www.microchip.com/en-us/development-tool/dm164150) | U3 (GH-PIC18F57Q1) |
| Piezoelectric Audio Transducer Buzzer, 4kHz | 1 | $1.45 | $1.45 | Soberton Inc. | PT-1407 | [DigiKey](https://www.digikey.com/en/products/detail/soberton-inc/PT-1407/9924300) | [Datasheet](https://www.soberton.com/products/pt-1407) | BZ1 |
| Standard Red LED, 625nm, 20mA, 5mm Through-Hole | 1 | $0.25 | $0.25 | Kingbright | WP7113ID | [DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP7113ID/2478794) | [Datasheet](https://www.kingbrightusa.com/images/catalog/SPEC/WP7113ID.pdf) | D1 |
| SPST OFF-(ON) Tactile Pushbutton Switch | 1 | $0.32 | $0.32 | C&K | PTS645SM43SMTR92 LFS | [DigiKey](https://www.digikey.com/en/products/detail/c-k/PTS645SM43SMTR92-LFS/4177284) | [Datasheet](https://www.ckswitches.com/media/1471/pts645.pdf) | SW1 |
| 8-Pin Single Row 0.1" (2.54mm) Male Header | 1 | $0.48 | $0.48 | Amphenol CS | 68000-108HLF | [DigiKey](https://www.digikey.com/en/products/detail/amphenol-icc-fci/68000-108HLF/1086111) | [Datasheet](https://www.amphenol-cs.com/media/wysiwyg/files/drawing/68000.pdf) | J3 |

Note: Setting it up as a table is nice because it is completely viewable without scaling issues. <ins>Downside</ins> is that you have to do the math.

- You could also import your BOM via a screenshot of the spreadsheet created BOM

## Bill of Materials Example (as Image)
![](BOM-Screenshot.png){style width: "2000"}
**Figure 2:** Example Bill of Materials as a screenshot.
