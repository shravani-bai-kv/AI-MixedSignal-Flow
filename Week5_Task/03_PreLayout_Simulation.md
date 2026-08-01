# Environment Preparation for Analog MUX Design

## Objective

Prepare the design environment required for implementing a new double-height 2:1 Analog Multiplexer using the SKY130 PDK and ngspice.

---

## Design Workspace

A dedicated workspace was created inside the cloned `vsdmixedsignalflow` repository to keep all design files organized.

```text
week5_mux_design/
├── extracted/
├── layouts/
├── netlists/
├── simulations/
└── spice/
```

---

## Creating the Design Workspace

The following commands were executed:

```bash
cd ~/Desktop/vsdmixedsignalflow

mkdir -p week5_mux_design

cd week5_mux_design

mkdir -p netlists spice layouts simulations extracted
```

---

## SKY130 PDK Verification

The installed SKY130 Process Design Kit (PDK) was located using:

```bash
find ~ -type d -name "sky130A" 2>/dev/null
```

The primary SKY130 installation was found at:

```text
/home/shravani/.ciel/ciel/sky130/versions/0fe599b2afb6708d281543108caf8310912f54af/sky130A
```

---

## ngspice Model Verification

The ngspice model library was verified using:

```bash
cd /home/shravani/.ciel/ciel/sky130/versions/0fe599b2afb6708d281543108caf8310912f54af/sky130A

find . -name "sky130.lib.spice"
```

The following model libraries were found:

```text
./libs.tech/ngspice/sky130.lib.spice
./libs.tech/combined/sky130.lib.spice
./libs.tech/combined/continuous/sky130.lib.spice
```

This confirms that the SKY130 ngspice models required for transistor-level simulation are available.

---

## Project Status

The following tasks have been completed:

- Repository analysis
- Existing MUX study
- Week 5 project setup
- Design workspace creation
- SKY130 PDK verification
- ngspice model verification

The project environment is now ready for transistor-level circuit implementation.

---

## Screenshots

### SKY130 PDK Detection

> <img width="996" height="391" alt="image" src="https://github.com/user-attachments/assets/4897f0db-ac8d-4e45-9aec-b08f43bd065b" />


### ngspice Model Verification

> <img width="1016" height="489" alt="image" src="https://github.com/user-attachments/assets/a9d77ee2-1084-4f66-b3c3-22e674087674" />


---

## Next Step

The next stage is to design a completely new transmission-gate-based 2:1 Analog Multiplexer using SKY130 transistors. The transistor-level SPICE netlist will then be created and verified using ngspice before proceeding to Magic layout generation.
