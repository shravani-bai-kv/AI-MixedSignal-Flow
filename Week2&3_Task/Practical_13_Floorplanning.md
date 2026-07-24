# Practical 13 - Floorplanning

## Objective

To understand how OpenLane determines the physical arrangement of the chip before placement.

---

# What is Floorplanning?

Floorplanning determines

- Chip size
- Core size
- IO locations
- Macro positions
- Standard cell region

---

# Inputs

- Gate-level netlist
- LEF files
- Technology information
- config.tcl

---

# Outputs

- DEF file
- Floorplan database

---

# Important Parameters

```
FP_CORE_UTIL
```

Controls utilization.

Lower utilization

↓

Less congestion

↓

Better routing

---

```
PL_TARGET_DENSITY
```

Controls placement density.

---

# Analog Macro Placement

Unlike standard cells,

Analog Macros

- cannot move
- cannot rotate freely
- already have layout

Their LEF tells OpenLane

- size
- pins
- blockage

---

# Why LEF?

LEF provides

- Width
- Height
- Pin locations

without revealing transistor details.

---

# Learning Outcome

I understood how floorplanning creates the initial chip layout and reserves space for analog macros before standard cell placement.
