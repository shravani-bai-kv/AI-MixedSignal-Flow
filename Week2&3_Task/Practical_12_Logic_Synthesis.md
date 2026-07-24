# Practical 12 - Logic Synthesis

## Objective

To understand how Verilog RTL is converted into a gate-level netlist using Yosys during the OpenLane RTL-to-GDS flow.

---

# What is Logic Synthesis?

Logic synthesis is the first implementation stage of the physical design flow.

It converts the behavioral Verilog code into logic gates available in the SKY130 standard cell library.

Tool Used

- Yosys

---

# Input

RTL Files

- design_mux.v
- raven_spi.v
- spi_slave.v

Analog Macro

- AMUX2_3V.v (Black Box)

Technology Library

- SKY130 Standard Cell Library

---

# Output

Gate-Level Netlist

```
design_mux.synthesis.v
```

---

# Synthesis Flow

```
Verilog RTL

↓

Read Verilog

↓

Elaborate Design

↓

Logic Optimization

↓

Technology Mapping

↓

Gate-Level Netlist
```

---

# Why is AMUX2_3V a Black Box?

AMUX2_3V is an Analog Macro.

It already has a physical layout.

Therefore,

Yosys does not synthesize it.

Instead,

it only keeps the module interface.

This is why OpenLane uses

```
VERILOG_FILES_BLACKBOX
```

instead of including it in synthesis.

---

# Example

RTL

```verilog
assign out = (select) ? I1 : I0;
```

↓

Mapped Gates

```
MUX2

AND

OR

INV
```

using SKY130 standard cells.

---

# Learning Outcome

I understood how OpenLane uses Yosys to convert RTL into a gate-level implementation while preserving analog macros as black boxes.
