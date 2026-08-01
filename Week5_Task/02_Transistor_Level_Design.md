# Transistor-Level Design

## Objective

Design a completely new transistor-level 2:1 Analog Multiplexer using SKY130 MOSFETs. This design will replace the placeholder `AMUX2_3V` macro used in the repository.

---

## Design Requirements

The new analog multiplexer should satisfy the following requirements:

- SKY130 technology
- Double-height standard cell
- Two analog inputs
- One analog output
- One select signal
- Compatible with OpenLane integration
- DRC and LVS clean
- Suitable for post-layout extraction

---

## Selected Architecture

A transmission-gate-based architecture was selected because it provides:

- Rail-to-rail signal transmission
- Low ON resistance
- Improved analog performance
- Better signal integrity than a single-pass transistor implementation

Each transmission gate consists of:

- One NMOS transistor
- One PMOS transistor

Two transmission gates are used to implement the 2:1 analog multiplexer.

---

## Functional Operation

| Select | Connected Input |
|---------|-----------------|
| 0 | I0 |
| 1 | I1 |

An inverter generates the complementary control signal required to drive the PMOS devices.

---

## Design Workspace

A dedicated design workspace was created inside the cloned `vsdmixedsignalflow` repository.

```text
week5_mux_design/
├── extracted/
├── layouts/
├── netlists/
├── simulations/
└── spice/
```

### Screenshot

> <img width="1001" height="663" alt="image" src="https://github.com/user-attachments/assets/84f75bcc-3405-4282-bce6-00b8756f501f" />


---

## Outcome

The design environment for the new analog multiplexer has been prepared. The next step is to create the transistor-level SPICE netlist using SKY130 device models and verify its functionality using ngspice.
