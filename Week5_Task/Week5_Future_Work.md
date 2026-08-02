# Future Work

The following tasks remain for complete integration into the mixed-signal RTL-to-GDS flow:

- Perform Netgen LVS between schematic and extracted layout.
- Run post-layout ngspice simulations including extracted parasitics.
- Compare pre-layout and post-layout timing.
- Generate LEF view for OpenLane integration.
- Generate GDS for signoff.
- Generate Liberty (.lib) characterization.
- Generate SPEF parasitic file.
- Create Verilog black-box model.
- Replace placeholder AMUX2_3V macro.
- Execute complete OpenLane physical design flow.
- Verify placement and routing.
- Perform final chip-level DRC and LVS.

These tasks complete the full analog macro integration into the digital RTL-to-GDS flow.
