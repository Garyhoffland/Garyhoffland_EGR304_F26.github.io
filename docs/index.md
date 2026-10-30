---
title: Welcome
tags:
- Gary Hoffland
- Datasheet
- Optical Sensor Subsystem
---

<center>
<font size= "6">Gary Hoffland Datasheet</font><br>
as part of<br>
<font size= "8"> Advanced Innovation Project</font><br>
for<br>
<font size= "5"> Team 101 </font><br>

**Submission: Month Day, 2026**
</center>

## Introduction

This datasheet serves as the comprehensive technical documentation for a non-contact optical sensing and signal-processing subsystem. It details the complete hardware architecture, schematic layouts, bill of materials, power budget calculations, and signal routing specifications required to build, test, and integrate this module within the broader team architecture.

### Project Summary

The overall team project focuses on developing an integrated autonomous navigation platform capable of real-time environmental sensing, precision obstacle detection, and coordinated motor actuation. 

My specific contribution to the system is the optical proximity and position sensing module. This subsystem utilizes an OPB732 reflective optical switch to continuously detect target presence and signal conditioned operational amplifier stages to process analog voltage swings into the central PIC18F57Q43 microcontroller. Upon processing an active event, the subsystem generates localized audio alerts via a piezo transducer while simultaneously asserting digital inter-board control triggers to drive downstream actuation modules.

For a complete overview of the overarching system architecture, collaborative goals, and full team integration testing, please visit our [team report.](https://embedded-systems-design.github.io/EGR304TeamTemplate/)

### My Contribution

Below is a direct guide to navigating the core sections of my subsystem design and technical documentation:

- **System Schematic & Rationale:** To review the complete circuit design, component selection rationales (including the OPB732 and PIC18F57Q43), and fuse placement analysis, refer to the ["Schematic"](https://embedded-systems-design.github.io/EGR304DataSheetTemplate/02-Schematic/Schematic/) section.
- **Bill of Materials (BOM):** To review the detailed breakdown of all passive and active components, procurement costs, vendor specifications, and reference designators, you can review them in the ["BOM"](https://embedded-systems-design.github.io/EGR304DataSheetTemplate/03-BOM/BOM/) section of the datasheet.
- **Power Budget & Rail Analysis:** To analyze the power consumption profiles, $9\text{V}$ battery runtime calculations, linear regulator thermal dissipation, and safety margin evaluations, explore the ["Power Budget"](https://embedded-systems-design.github.io/EGR304DataSheetTemplate/05-Power-Budget/Power-Budget/) section.
- **Microcontroller Pin Mapping:** To check the exact pin allocations, hardware interconnects, and signal functions for the $PIC18F57Q43$, check the ["Pin Table"](https://embedded-systems-design.github.io/EGR304DataSheetTemplate/04-Pin-Table/Pin-Table/) section.
