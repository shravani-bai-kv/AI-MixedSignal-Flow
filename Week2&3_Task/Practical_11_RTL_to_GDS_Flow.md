# Practical 11 - RTL to GDSII Flow

## Objective

The objective of this practical is to understand the complete RTL-to-GDSII physical design flow followed by OpenLane.

---

# What is RTL-to-GDSII?

RTL-to-GDSII is the process of converting a Verilog RTL design into a manufacturable chip layout.

The final output is a GDSII file, which is sent to the semiconductor fabrication plant for chip manufacturing.

---

# Complete OpenLane Flow

```
RTL (Verilog)

↓

Logic Synthesis

↓

Floorplanning

↓

Power Distribution Network (PDN)

↓

Placement

↓

Clock Tree Synthesis (CTS)

↓

Routing

↓

DRC Check

↓

LVS Check

↓

GDSII Generation
```

---

# Stage 1 - RTL

Input Files

- design_mux.v
- raven_spi.v
- spi_slave.v
- AMUX2_3V.v

These describe the functionality of the design.

---

# Stage 2 - Logic Synthesis

Tool

Yosys

Purpose

- Convert RTL into gate-level netlist
- Optimize logic
- Map logic to SKY130 standard cells

Output

```
design_mux.synthesis.v
```

---

# Stage 3 - Floorplanning

Purpose

Determine the physical arrangement of blocks inside the chip.

Activities

- Chip size
- Core area
- IO placement
- Macro placement

Output

Floorplan DEF

---

# Stage 4 - Power Distribution Network

Purpose

Create VDD and GND power rails.

Without PDN, the chip cannot operate reliably.

---

# Stage 5 - Placement

Purpose

Place all standard cells inside the floorplan.

Goal

- Reduce wirelength
- Improve timing
- Reduce congestion

---

# Stage 6 - Clock Tree Synthesis

Purpose

Distribute the clock signal evenly across the chip.

Objectives

- Minimize clock skew
- Minimize clock latency

---

# Stage 7 - Routing

Purpose

Connect all placed cells using metal layers.

Output

Fully connected physical design.

---

# Stage 8 - DRC

Design Rule Check

Checks whether the layout satisfies fabrication rules.

Examples

- Minimum spacing
- Minimum width
- Via rules

---

# Stage 9 - LVS

Layout Versus Schematic

Checks whether

Physical Layout

=

RTL Netlist

If both match, the design is functionally correct.

---

# Stage 10 - GDSII Generation

Final output

```
design_mux.gds
```

This file is sent for chip fabrication.

---

# Learning Outcome

I understood every stage involved in converting a Verilog RTL design into a manufacturable GDSII layout using the OpenLane physical design flow.
