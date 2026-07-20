# Week 1 - Understanding Mixed Signal Physical Design

## Objective

Today I focused on understanding the complete RTL-to-GDS flow before attempting to execute the repository.

---

## What is Mixed Signal Design?

A mixed signal IC combines digital logic and analog circuitry inside a single chip.

Examples of analog blocks include:

- ADC
- DAC
- PLL
- Operational Amplifier
- Analog Multiplexer (AMUX)

---

## What is OpenLane?

OpenLane is an open-source RTL-to-GDS automation flow.

It combines multiple open-source EDA tools to automate physical design.

Main tools include:

- Yosys
- OpenROAD
- Magic
- Netgen
- KLayout

---

## What is SKY130?

SKY130 is an open-source Process Design Kit (PDK).

It provides:

- Standard Cells
- DRC Rules
- Technology Files
- Timing Libraries
- Physical Layers

---

## Overall Design Flow

RTL

↓

Synthesis

↓

Floorplanning

↓

Placement

↓

Clock Tree Synthesis

↓

Routing

↓

DRC

↓

LVS

↓

Final GDS Layout

---

## Key Learning

The reference repository demonstrates how an existing analog macro is integrated into a digital RTL flow using OpenLane.
