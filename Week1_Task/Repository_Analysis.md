# Repository Analysis - Day 1

## Reference Repository

**Repository:** https://github.com/praharshapm/vsdmixedsignalflow

## Objective

The objective of the reference repository is to demonstrate a complete **AI-assisted Mixed Signal RTL-to-GDS physical design flow** using open-source EDA tools.

Unlike a purely digital design, this project integrates an already-designed analog macro into a digital implementation flow using OpenLane and the SKY130 Process Design Kit (PDK).

---

# What Problem Does This Repository Solve?

Modern System-on-Chips (SoCs) often contain both:

- Digital Logic
- Analog Blocks

Digital logic can be synthesized from Verilog, whereas analog circuits are manually designed at the transistor level.

This repository shows how an existing analog block can be integrated with digital logic to generate a final chip layout.

---

# Overall Design Flow

```
Verilog RTL
      │
      ▼
Synthesis (Yosys)
      │
      ▼
Gate-Level Netlist
      │
      ▼
OpenLane Physical Design
      │
      ▼
Floorplanning
      │
      ▼
Macro Placement
      │
      ▼
Standard Cell Placement
      │
      ▼
Clock Tree Synthesis
      │
      ▼
Routing
      │
      ▼
DRC / LVS
      │
      ▼
Final GDSII Layout
```

The analog macro is integrated during the physical design stage using LEF, GDS and LIB files.

---

# Main Concepts Learned

## 1. Mixed Signal Design

Mixed Signal design combines:

- Digital Circuits
- Analog Circuits

inside a single integrated circuit.

Examples of analog macros include:

- ADC
- DAC
- PLL
- Analog Multiplexer (AMUX)
- Operational Amplifier

The reference project uses an Analog Multiplexer (AMUX).

---

## 2. OpenLane

OpenLane is an open-source RTL-to-GDS automation flow.

It coordinates several open-source tools including:

- Yosys
- OpenROAD
- Magic
- Netgen
- KLayout

OpenLane itself does not perform all design tasks; instead, it manages the complete implementation flow.

---

## 3. SKY130 PDK

The project uses the SKY130 open-source Process Design Kit.

The PDK provides:

- Standard Cell Libraries
- Technology Files
- Design Rules
- Layer Information
- Timing Libraries
- Device Models

Without a PDK, physical implementation cannot be performed.

---

# Expected Repository Structure

Although folder names may vary slightly, the repository mainly contains:

| Folder | Purpose |
|---------|----------|
| README | Project documentation |
| verilog | RTL source files |
| openlane | OpenLane configuration files |
| lef | Physical abstract view of macros |
| lib | Timing libraries |
| gds | Final layout of analog macro |
| mag | Magic layout files |
| docs/images | Screenshots and documentation |

---

# Important Input Files

## Verilog (.v)

Describes the digital functionality of the design.

Example:

- Module definition
- Inputs
- Outputs
- RTL logic

---

## LEF (.lef)

Library Exchange Format.

Contains:

- Macro dimensions
- Pin locations
- Routing blockages
- Metal layer information

OpenLane uses LEF during floorplanning and placement.

---

## LIB (.lib)

Liberty Timing Library.

Contains:

- Timing information
- Delay models
- Power information

Used during timing analysis.

---

## GDS (.gds)

Graphic Database System.

Contains the complete physical layout of the analog macro.

This file is merged with the digital layout to generate the final chip.

---

## Configuration Files

Configuration files specify:

- Core utilization
- Die size
- Macro placement
- Power distribution
- Clock configuration
- Routing parameters

These files control how OpenLane executes the flow.

---

# High-Level Workflow

```
Digital RTL
      │
      ▼
Synthesis
      │
      ▼
Floorplanning
      │
      ▼
Read Analog LEF
      │
      ▼
Reserve Macro Area
      │
      ▼
Placement
      │
      ▼
Routing
      │
      ▼
Merge Analog GDS
      │
      ▼
Generate Final Chip
```

---

# AI-Assisted Learning Strategy

Instead of directly copying the reference repository, I followed an AI-assisted learning approach.

The workflow consisted of:

1. Understanding the repository architecture.
2. Learning the purpose of each file.
3. Understanding the complete RTL-to-GDS flow.
4. Studying OpenLane and SKY130.
5. Preparing AI prompts for each implementation stage.
6. Planning to verify all AI-generated outputs using open-source EDA tools.

---

# Key Observations

- Mixed-signal physical design is mainly an integration problem.
- Analog blocks are already designed before entering OpenLane.
- OpenLane performs digital implementation around the analog macro.
- LEF, LIB and GDS files are essential for integrating analog IP.
- Understanding the complete flow is more important than memorizing tool commands.

---

# Next Steps

- Explore every folder in the repository.
- Study OpenLane configuration files.
- Understand LEF, LIB and GDS in detail.
- Install OpenLane and SKY130.
- Attempt the complete RTL-to-GDS flow.
- Document all AI prompts, observations and debugging steps.

---

## Day 1 Summary

Today I focused on understanding the purpose of the reference repository instead of immediately executing it. I learned how OpenLane automates the RTL-to-GDS flow, why SKY130 is required, and how an analog macro is integrated into a digital physical design. This understanding forms the foundation for the practical implementation in the coming days.
