# Practical 14 - Placement

## Objective

To understand how OpenLane places standard cells inside the floorplan.

---

# What is Placement?

Placement determines the physical location of every standard cell.

---

# Goals

- Reduce wire length
- Improve timing
- Reduce congestion
- Improve power

---

# Types

## Global Placement

Approximate positions.

---

## Detailed Placement

Legal positions.

No overlaps.

---

# Inputs

- Synthesized Netlist
- Floorplan
- LEF

---

# Outputs

Placed DEF

---

# Analog Macro

The analog macro

AMUX2_3V

remains fixed.

Only digital cells move around it.

---

# Learning Outcome

I understood how OpenLane optimizes standard cell positions while preserving analog macro placement.
