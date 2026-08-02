# Week 5 – Task 3: Pre-Layout Simulation

## Objective

Verify the functionality of the designed 2:1 Analog Multiplexer before layout generation using NGSpice.

---

## Testbench

The MUX was connected with:

- Supply Voltage: **1.8 V**
- Analog Input I0: Sine Wave
- Analog Input I1: Sine Wave
- Select Signal (SEL): Pulse waveform
- Output Load: Capacitive and Resistive load

The simulation was performed using a transient analysis.

---

## Simulation Command

```bash
cd week5_mux_design/spice
ngspice testbench.spice
```

---

## Waveform 1 – Analog Inputs (I0 and I1)

**Description**

This waveform shows both analog input signals applied to the multiplexer.

> <img width="710" height="555" alt="image" src="https://github.com/user-attachments/assets/9b747515-166f-4de3-b6d2-4e5ec736b3ed" />


---

## Waveform 2 – Select Signal (SEL)

**Description**

The select signal switches periodically between logic LOW (0 V) and HIGH (1.8 V), determining which input is connected to the output.

> <img width="745" height="557" alt="image" src="https://github.com/user-attachments/assets/bcecdd8c-2b16-4293-8812-487fa45869c8" />


---

## Waveform 3 – Output (OUT)

**Description**

The output follows:

- **I0** whenever **SEL = HIGH**
- **I1** whenever **SEL = LOW**

This confirms correct multiplexing operation.

> <img width="1147" height="801" alt="image" src="https://github.com/user-attachments/assets/c8d6bdcf-d119-4757-9e84-9762dcd32bfa" />


---

## Observation

The NGSpice transient simulation confirms that the analog multiplexer switches correctly between the two input signals based on the select signal.

The output waveform follows the selected input, verifying the expected functionality of the transmission-gate based analog MUX before physical layout implementation.

---

## Conclusion

The pre-layout functional verification of the 2:1 Analog Multiplexer was successfully completed using NGSpice. The simulation demonstrates correct switching behavior and validates the circuit before proceeding to Magic layout generation.
