# Analog IP Study - avsdmux2x1_3v3 Repository

## Repository

Reference Repository:
https://github.com/prithivjp/avsdmux2x1_3v3

---

# Objective

The purpose of studying this repository is to understand how the Analog 2:1 Multiplexer (AMUX) IP is designed, verified, and prepared before being integrated into a mixed-signal RTL-to-GDS flow using OpenLane.

Unlike digital circuits, analog circuits are manually designed and verified before integration.

---

# What is an Analog IP?

An Analog Intellectual Property (IP) block is a reusable analog circuit that performs a specific function.

Examples include:

- Analog Multiplexer (AMUX)
- Operational Amplifier (Op-Amp)
- ADC
- DAC
- PLL

The repository focuses on an **Analog 2:1 Multiplexer (AMUX)**.

---

# Design Flow

The analog design follows the workflow below:

```
Circuit Design
      │
      ▼
SPICE Simulation
      │
      ▼
Layout Design (Magic)
      │
      ▼
Design Rule Check (DRC)
      │
      ▼
Layout Extraction
      │
      ▼
Post-Layout Simulation
      │
      ▼
Generate LEF, GDS and LIB
      │
      ▼
Ready for Mixed-Signal Integration
```

---

# Repository Contents

## Characteristics/

Contains simulation results and electrical characteristics of the analog multiplexer.

Purpose:

- Verify switching operation
- Analyze performance
- Measure delays
- Validate functionality

---

## Layout/

Contains the physical layout of the analog multiplexer.

The layout consists of:

- PMOS transistors
- NMOS transistors
- Metal layers
- Contacts
- Vias

This represents the actual physical implementation of the circuit.

---

## MAGIC/

Contains files related to the Magic VLSI layout editor.

Magic is used for:

- Layout creation
- Layout editing
- Design Rule Checking (DRC)
- Layout extraction

---

## NETLIST/

Contains SPICE netlists used for analog simulation.

The netlists describe:

- Transistor connections
- Device models
- Electrical behaviour

These files are simulated using NGSPICE.

---

## Step Images/

Contains screenshots of different design stages, including:

- Circuit schematic
- Layout
- Simulation waveforms
- Final outputs

---

# Output Files Generated

After completing the analog design flow, the following files are generated:

### LEF

Provides the abstract physical information of the analog macro.

Used during floorplanning.

---

### GDS

Contains the complete physical layout.

Used during final layout merging.

---

### LIB

Contains timing and power information.

Used during timing analysis.

---

# Relation to Mixed-Signal Flow

This repository creates the analog macro.

The generated files:

- LEF
- LIB
- GDS

are later used by the **vsdmixedsignalflow** repository during OpenLane execution.

```
Analog IP Repository
        │
        ▼
Generate LEF
Generate LIB
Generate GDS
        │
        ▼
Mixed-Signal Repository
        │
        ▼
OpenLane Flow
        │
        ▼
Final Chip Layout
```

---

# Learning Outcome

From this repository, I learned that the analog block is designed and verified independently before being integrated into the digital physical design flow. The generated LEF, LIB, and GDS files act as the interface between the analog design and the OpenLane mixed-signal implementation.
