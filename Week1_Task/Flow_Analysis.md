# RTL-to-GDS Flow Analysis

## Objective

To understand the complete physical design flow used in the reference repository.

---

# Complete Flow

```

RTL (Verilog)
│
▼
Synthesis (Yosys)
│
▼
Gate-Level Netlist
│
▼
Floorplanning
│
▼
Analog Macro Integration
│
▼
Placement
│
▼
Clock Tree Synthesis
│
▼
Routing
│
▼
Design Rule Check (DRC)
│
▼
Layout Versus Schematic (LVS)
│
▼
Final GDSII Layout

```

---

# Step 1 – RTL Design

The digital functionality is written in Verilog.

Example:
- Top module
- Wrapper
- Controller

Output:
RTL Source Files

---

# Step 2 – Synthesis

Tool:
Yosys

Purpose:
Converts RTL into a gate-level netlist using the SKY130 standard cell library.

Output:
Gate-level netlist

---

# Step 3 – Floorplanning

Purpose:
Defines

- Die area
- Core area
- Macro locations
- IO placement

The analog macro is reserved during this stage.

---

# Step 4 – Analog Macro Integration

The analog macro already exists.

Required files:

- LEF
- GDS
- LIB

OpenLane reads these files and reserves space for the macro.

---

# Step 5 – Placement

Purpose:

Place standard cells inside the available core area while respecting the reserved analog macro region.

---

# Step 6 – Clock Tree Synthesis

Purpose:

Distribute the clock signal with minimal skew and delay.

---

# Step 7 – Routing

Purpose:

Connect all placed cells using the available routing layers.

---

# Step 8 – DRC

Purpose:

Check whether the layout satisfies all fabrication design rules.

---

# Step 9 – LVS

Purpose:

Verify that the physical layout matches the intended circuit schematic.

---

# Step 10 – Final GDS

The digital layout and analog macro layout are merged to produce the final manufacturable chip.

---

# Learning Outcome

The repository demonstrates how an existing analog macro is integrated into a digital implementation flow using OpenLane. Understanding each stage helps in debugging and verifying the physical design process.
