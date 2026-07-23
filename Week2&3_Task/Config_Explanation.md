# OpenLane config.tcl Explanation

## Purpose

The `config.tcl` file controls how OpenLane performs RTL-to-GDS implementation.

---

## Important Parameters

### DESIGN_NAME

```tcl
set ::env(DESIGN_NAME) design_mux
```

Defines the top-level design.

---

### VERILOG_FILES

Specifies the RTL files used during synthesis.

---

### VERILOG_FILES_BLACKBOX

Defines analog macro behavioral models.

These modules are not synthesized.

---

### EXTRA_LEFS

Provides LEF information for analog macros.

Without LEF, OpenLane cannot place the analog block.

---

### CLOCK_PERIOD

Defines timing constraint.

```
10 ns
```

---

### CLOCK_PORT

Specifies the clock input.

```
select
```

---

### FP_CORE_UTIL

Controls core utilization during floorplanning.

Lower values reduce congestion.

---

### PL_TARGET_DENSITY

Target placement density.

Lower density makes routing easier.

---

### FP_PDN parameters

Used to generate the power distribution network.

These define:

- Power strap spacing
- Offset
- Pitch

---

## Summary

The configuration file connects the RTL, analog macro information and floorplanning parameters together so OpenLane can generate the physical layout.
