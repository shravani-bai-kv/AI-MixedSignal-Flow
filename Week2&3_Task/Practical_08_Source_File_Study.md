# Practical 08 - Source File Study

## Objective

The objective of this practical is to understand the source files used in the mixed-signal RTL-to-GDS project.

---

## Source Folder

Project_Files/src/

---

## Files Present

| File | Description |
|-------|-------------|
| design_mux.v | Top level module integrating analog and digital blocks |
| AMUX2_3V.v | Analog multiplexer macro |
| raven_spi.v | SPI controller |
| spi_slave.v | SPI slave implementation |

---

# File 1 : design_mux.v

Purpose:

Acts as the top module.

Responsibilities

- Instantiates Analog MUX
- Instantiates Raven SPI
- Connects both modules
- Defines chip I/O

Inputs

- select
- RST
- SCK
- SDI
- CSB
- trap
- mask_rev_in

Output

- out

---

# File 2 : AMUX2_3V.v

Purpose

Implements a 2:1 Analog Multiplexer.

Working

select = 0

Output = I0

select = 1

Output = I1

This module is treated as an Analog IP Macro.

---

# File 3 : raven_spi.v

Purpose

Implements the SPI controller.

Functions

- Register Control
- Reset Control
- PLL Control
- Clock Enable
- Communication Interface

---

# File 4 : spi_slave.v

Purpose

Implements SPI Slave Protocol.

Features

- Receives SPI Data
- Generates SPI Output
- Read Registers
- Write Registers
- Address Decoder

---

## Learning Outcome

I understood the role of each Verilog source file and how the top-level module integrates analog and digital blocks for mixed-signal chip implementation.
