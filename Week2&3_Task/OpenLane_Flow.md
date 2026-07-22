# OpenLane RTL-to-GDS Flow

## Objective

To understand each stage of the OpenLane physical design flow used in the mixed-signal implementation.

---

# Flow

```
RTL

↓

Synthesis

↓

Floorplanning

↓

PDN

↓

Placement

↓

CTS

↓

Routing

↓

DRC

↓

LVS

↓

Final GDS
```

---

## 1. RTL

The digital functionality is described using Verilog HDL.

Output:

RTL source files.

---

## 2. Synthesis

Tool:

Yosys

Purpose:

Converts RTL into a gate-level netlist using SKY130 standard cells.

---

## 3. Floorplanning

Defines:

- Die size
- Core size
- IO locations
- Macro placement

The analog macro area is reserved during this stage.

---

## 4. Power Distribution Network

Creates power and ground rails required for all cells.

---

## 5. Placement

Places standard cells while avoiding the reserved analog macro area.

---

## 6. Clock Tree Synthesis

Builds a balanced clock distribution network.

---

## 7. Routing

Creates metal connections between all placed cells.

---

## 8. Design Rule Check

Checks the layout against fabrication design rules.

---

## 9. Layout Versus Schematic

Verifies that the physical layout matches the intended circuit.

---

## 10. Final GDS

The digital layout is merged with the analog macro layout to produce the final manufacturable chip.

---

# Learning Outcome

I learned the purpose of each OpenLane stage and understood how the analog macro is preserved while the digital implementation is completed around it.
