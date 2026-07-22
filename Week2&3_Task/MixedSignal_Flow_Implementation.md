# Mixed-Signal Flow Implementation

## Objective

To understand how a pre-designed analog macro is integrated into the OpenLane digital implementation flow.

---

# Overall Flow

```
Analog Design
     │
     ├── LEF
     ├── LIB
     └── GDS
            │
            ▼
      OpenLane Flow
            ▲
            │
        Verilog RTL
            │
            ▼
      Final Mixed-Signal Chip
```

---

# Inputs Required

## Digital Inputs

- Verilog RTL

---

## Analog Inputs

- LEF
- LIB
- GDS

---

# Macro Integration

The analog macro is treated as a fixed block.

OpenLane uses the LEF file to reserve space during floorplanning and later merges the GDS file to generate the final chip layout.

---

# Flow

RTL

↓

Synthesis

↓

Floorplanning

↓

Reserve Macro Area

↓

Placement

↓

CTS

↓

Routing

↓

Merge Analog GDS

↓

Final GDS

---

# Observation

The analog macro is not synthesized. Instead, it is integrated into the digital implementation using LEF, LIB, and GDS files.

---

# Learning Outcome

I understood that OpenLane performs the complete digital implementation while preserving the analog macro as a fixed physical block.
