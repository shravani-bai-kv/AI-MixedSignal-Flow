# Practical 10 - OpenLane Directory Structure

## Objective

The objective of this practical is to understand the directory structure of the OpenLane project and the purpose of each folder used during RTL-to-GDS implementation.

---

# OpenLane Directory

```
OpenROAD-flow/
│
├── docs/
├── flow/
├── tools/
├── docker/
├── etc/
├── OpenROAD/
├── README.md
├── setup.sh
└── build_openroad.sh
```

---

## Folder Description

### docs/

Contains documentation related to OpenLane and OpenROAD.

---

### flow/

Contains the complete RTL-to-GDS automation flow.

This is the most important directory because it executes:

- Synthesis
- Floorplanning
- Placement
- Clock Tree Synthesis
- Routing
- DRC
- LVS
- GDS Generation

---

### tools/

Contains scripts and utilities required during the flow.

Examples:

- Python scripts
- TCL scripts
- Helper utilities

---

### docker/

Contains Docker configuration files used to create a consistent OpenLane environment.

---

### etc/

Stores configuration files used by the flow.

---

### setup.sh

Shell script used to initialize the OpenLane environment.

---

### build_openroad.sh

Build script used to compile the OpenROAD tool from source.

---

## Importance

The OpenLane directory is organized so that each stage of physical design is separated into different folders, making the RTL-to-GDS flow modular and easier to maintain.

---

## Learning Outcome

I explored the OpenLane project directory and understood the purpose of the major folders and scripts required for the RTL-to-GDS implementation flow.
