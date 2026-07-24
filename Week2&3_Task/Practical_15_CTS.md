# Practical 15 - Clock Tree Synthesis (CTS)

## Objective

To understand how OpenLane distributes the clock signal uniformly across the chip.

---

# Why CTS?

Without CTS,

different registers receive the clock at different times.

This causes timing failures.

---

# Objectives

- Reduce clock skew
- Reduce latency
- Balance clock tree

---

# Tool

OpenROAD CTS Engine

---

# Flow

Clock Source

↓

Clock Buffers

↓

Clock Tree

↓

Registers

---

# Output

Balanced clock network.

---

# Learning Outcome

I understood the importance of CTS in ensuring reliable synchronous operation.
