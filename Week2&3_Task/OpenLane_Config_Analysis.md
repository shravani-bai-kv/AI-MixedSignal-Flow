# OpenLane Configuration Analysis

## Objective

The objective of this study is to understand the purpose of the OpenLane configuration file (`config.tcl`) and how it controls the mixed-signal physical design flow.

---

# Configuration Parameters

| Parameter | Description |
|-----------|-------------|
| `DESIGN_NAME` | Specifies the top-level design name (`design_mux`). |
| `VERILOG_FILES` | Points to the RTL source file used for synthesis. |
| `VERILOG_FILES_BLACKBOX` | Declares the analog macro as a black box so it is not synthesized. |
| `EXTRA_LEFS` | Provides the LEF file of the analog macro for floorplanning. |
| `CLOCK_PERIOD` | Sets the timing constraint to 10 ns (100 MHz). |
| `CLOCK_PORT` | Defines the signal used as the timing reference (`select`). |
| `FP_CORE_UTIL` | Sets the core utilization to 20% to reduce congestion. |
| `PL_TARGET_DENSITY` | Sets placement density to 40% for improved routing. |
| `FP_PDN_VOFFSET` | Vertical offset for the power distribution network. |
| `FP_PDN_VPITCH` | Vertical spacing between power rails. |
| `FP_PDN_HOFFSET` | Horizontal offset for the power distribution network. |
| `FP_PDN_HPITCH` | Horizontal spacing between power rails. |

---

# Important Observations

## DESIGN_NAME

Defines the top-level project used by OpenLane.

---

## VERILOG_FILES

Specifies the RTL file that will be synthesized by Yosys.

---

## VERILOG_FILES_BLACKBOX

The analog macro is treated as a black box.

Only its interface is visible during synthesis, while its implementation already exists in the layout.

---

## EXTRA_LEFS

Provides the physical abstract (size, pins, and routing information) of the analog macro.

This allows OpenLane to reserve space during floorplanning.

---

## CLOCK_PERIOD

A clock period of **10 ns** corresponds to an operating frequency of **100 MHz**.

---

## Floorplanning Parameters

The project uses:

- Core Utilization = 20%
- Placement Density = 40%

These values help reduce congestion and simplify routing for this small mixed-signal design.

---

## Power Distribution Network

The PDN parameters define the spacing and placement of power rails used to distribute VDD and GND across the chip.

---

# Learning Outcome

From this configuration file, I learned how OpenLane identifies the design, reads RTL files, integrates analog macros, applies timing constraints, performs floorplanning, and configures the power distribution network before beginning physical implementation.
