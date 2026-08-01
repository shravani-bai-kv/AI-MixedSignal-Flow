# Transistor-Level Design of the New 2:1 Analog MUX

## Objective

Design a completely new transistor-level 2:1 analog multiplexer using SKY130 MOSFETs. The new design will replace the existing placeholder `AMUX2_3V` macro and will later be verified through simulation, layout generation, DRC, LVS, and OpenLane integration.

---

## Design Requirements

The new analog multiplexer should satisfy the following requirements:

- Technology: SKY130
- Double-height standard cell
- Two analog inputs
- One analog output
- One select signal
- Compatible with OpenLane integration
- DRC and LVS clean
- Legal pin placement for routing
- Suitable for post-layout extraction

---

## Circuit Selection

A transmission-gate-based architecture was selected for the new analog multiplexer.

Each transmission gate consists of:

- One NMOS transistor
- One PMOS transistor

The NMOS and PMOS operate together to pass both logic '0' and logic '1' efficiently, providing full voltage swing and improved analog signal integrity.

---

## Functional Operation

The multiplexer has two transmission gates.

### Transmission Gate 1

- Connects Input I0 to the output.
- Enabled when `SEL = 0`.

### Transmission Gate 2

- Connects Input I1 to the output.
- Enabled when `SEL = 1`.

To operate correctly, complementary control signals are required:

- SEL
- SEL̅ (inverted SEL)

The inverter generating SEL̅ will also be included in the transistor-level design.

---

## Proposed Block Diagram

```
          I0
           |
      Transmission Gate
           |
           +--------- OUT
           |
      Transmission Gate
           |
          I1

Control Signals

SEL
SEL̅
```

---

## Expected Advantages

Compared to the placeholder analog MUX, the proposed design aims to provide:

- Full rail-to-rail signal transmission
- Lower ON resistance
- Improved analog performance
- Better routing accessibility
- Clean physical implementation
- Compatibility with SKY130 design rules

---

## Design Summary

The transmission-gate architecture was selected because it offers reliable analog switching, good signal integrity, and straightforward implementation in the SKY130 process. This architecture will now be converted into a transistor-level SPICE netlist for functional verification using ngspice.
