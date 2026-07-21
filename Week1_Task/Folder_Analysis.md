# Folder Analysis

## Objective

The purpose of this document is to understand the role of each important folder in the reference repository instead of simply copying its contents.

Reference Repository:
https://github.com/praharshapm/vsdmixedsignalflow

---

# Repository Overview

The repository demonstrates a complete mixed-signal RTL-to-GDS flow by integrating an analog macro into a digital implementation flow using OpenLane and the SKY130 PDK.

Instead of manually creating every file, the repository provides the required files and configurations needed for OpenLane.

---

# Folder Analysis

## README.md

Purpose:
- Introduces the project.
- Explains the mixed-signal flow.
- Lists required tools.
- Describes execution steps.
- Shows expected outputs.

Importance:
The README is the starting point for understanding the complete project.

---

## verilog/

Purpose:
Contains the RTL source files.

Typical contents:
- Top module
- Wrapper module
- RTL logic

Importance:
These files describe the digital functionality of the design.

---

## openlane/

Purpose:
Contains configuration files for the OpenLane flow.

Typical contents:
- config.json
- config.tcl
- macro placement configuration
- PDN configuration

Importance:
Controls how the OpenLane flow executes.

---

## lef/

Purpose:
Stores the LEF (Library Exchange Format) files.

LEF contains:
- Macro dimensions
- Pin locations
- Routing blockages
- Metal layer information

Importance:
OpenLane uses LEF during floorplanning and placement.

---

## lib/

Purpose:
Contains Liberty timing files.

LIB provides:
- Timing
- Delay
- Power models

Importance:
Used for timing analysis.

---

## gds/

Purpose:
Contains the final layout of the analog macro.

Importance:
This layout is merged with the digital design to generate the final chip.

---

## mag/

Purpose:
Contains Magic layout files.

Importance:
Allows viewing and editing layouts using the Magic layout editor.

---

## docs / images

Purpose:
Contains documentation and screenshots.

Importance:
Helps understand intermediate and final outputs.

---

# Learning Outcome

Today I understood that every folder serves a specific role in the RTL-to-GDS flow. The Verilog files define the logic, LEF and LIB describe the analog macro, OpenLane configuration files control the implementation process, and the GDS file represents the final physical layout used for fabrication.
