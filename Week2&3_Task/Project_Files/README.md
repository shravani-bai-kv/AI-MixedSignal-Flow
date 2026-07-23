# Mixed-Signal Design Project Files

## Objective

This folder contains the RTL source files and OpenLane configuration required for implementing the mixed-signal RTL-to-GDS flow.

---

## Files

### design_mux.v

Top-level module integrating the analog multiplexer with the SPI controller.

---

### AMUX2_3V.v

Behavioral Verilog model of the analog 2:1 multiplexer.

---

### raven_spi.v

SPI controller responsible for controlling the analog multiplexer.

---

### spi_slave.v

SPI slave interface handling communication between external SPI master and the design.

---

### config.tcl

OpenLane configuration file defining design name, Verilog sources, analog macro LEF, clock information and floorplanning parameters.

---

## Learning Outcome

Studied how digital RTL integrates with analog macros during physical design using the SKY130 PDK and OpenLane flow.
