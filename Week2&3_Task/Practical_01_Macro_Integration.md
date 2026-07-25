# Macro Integration in Mixed-Signal Physical Design

## Objective

The objective of this study is to understand how an existing analog macro is integrated into the OpenLane physical design flow.

---

# What is a Macro?

A macro is a pre-designed circuit block that is treated as a fixed component during physical implementation.

Examples include:

- SRAM
- PLL
- ADC
- DAC
- Analog Multiplexer (AMUX)

The reference project uses an Analog 2:1 Multiplexer (AMUX).

---

# Inputs Required

OpenLane requires the following files to integrate the analog macro:

| File | Purpose |
|------|---------|
| Verilog | Digital logic |
| LEF | Physical abstract |
| LIB | Timing information |
| GDS | Final layout |

---

# Integration Flow

```
Digital RTL
      │
      ▼
Synthesis
      │
      ▼
Read LEF
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
Final Chip Layout
```

---

# Why LEF is Required

The LEF file provides:

- Macro dimensions
- Pin locations
- Routing blockages

This information allows OpenLane to reserve space for the analog macro during floorplanning.

---

# Why GDS is Required

The GDS file contains the complete physical layout of the analog macro.

It is merged with the digital layout to generate the final manufacturable chip.

---

# Learning Outcome

I learned that OpenLane does not synthesize analog circuits. Instead, it integrates a pre-designed analog macro using LEF, LIB and GDS files while implementing the digital portion of the design.
