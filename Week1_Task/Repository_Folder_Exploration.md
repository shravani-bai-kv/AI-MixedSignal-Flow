# Repository Folder Exploration

## Objective

The objective of this study is to understand the purpose of each major folder in the reference repository instead of simply executing the provided scripts.

Reference Repository:
https://github.com/praharshapm/vsdmixedsignalflow

---

## Repository Structure

The repository demonstrates the implementation of a mixed-signal RTL-to-GDS flow using OpenLane and the SKY130 PDK. It contains digital RTL, analog macro files, OpenLane configuration files, and documentation.

---

## Major Folders

### README.md

Provides project overview, setup instructions, execution flow, and expected outputs.

---

### designs/

Contains the project-specific design files, including configuration and references to the analog macro.

---

### src/

Contains the Verilog RTL files that describe the digital functionality of the design.

---

### openlane/

Contains configuration files that control synthesis, floorplanning, placement, routing, and other implementation stages.

---

### lef/

Contains LEF files describing the physical abstract view of the analog macro.

---

### lib/

Contains Liberty timing libraries used for timing analysis.

---

### gds/

Contains the completed physical layout of the analog macro.

---

### mag/

Contains Magic layout files for viewing and editing layouts.

---

## Learning Outcome

I understood that each folder contributes to a different stage of the RTL-to-GDS flow. Together, these files allow OpenLane to integrate an analog macro with digital logic and generate the final chip layout.
