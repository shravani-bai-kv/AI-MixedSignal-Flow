# RTL Analysis of design_mux

## Objective

The objective of this study is to understand the RTL hierarchy of the mixed-signal design and identify how the analog macro is integrated with the digital logic.

---

# RTL Files Studied

| File | Purpose |
|------|---------|
| AMUX2_3V.v | Analog multiplexer interface (black box) |
| design_mux.v | Top-level design module |
| raven_spi.v | SPI controller |
| spi_slave.v | SPI slave communication module |

---

# RTL Hierarchy

```
design_mux
│
├── AMUX2_3V
│
└── raven_spi
      │
      └── spi_slave
```

The `design_mux` module is the top-level module used by OpenLane.

---

# 1. AMUX2_3V.v

Purpose:

Represents the Analog 2:1 Multiplexer.

Inputs

- I0
- I1
- select

Output

- out

The module behaves like a 2:1 multiplexer.

```
select = 0 → out = I0

select = 1 → out = I1
```

This module is treated as a **black box** during synthesis because the actual implementation already exists as an analog layout.

---

# 2. design_mux.v

This is the top-level module specified in `config.tcl`.

Main inputs

- RST
- SCK
- SDI
- CSB
- trap
- select

Main output

- out

The module instantiates:

- AMUX2_3V
- raven_spi

The SPI controller generates digital signals that are connected to the analog multiplexer.

---

# 3. raven_spi.v

Purpose

Implements the SPI controller.

Responsibilities

- Receive SPI commands
- Store configuration values
- Generate control signals
- Generate reset signal
- Control PLL and oscillator signals

It communicates with the SPI slave module.

---

# 4. spi_slave.v

Purpose

Implements the SPI communication protocol.

Responsibilities

- Receive serial data
- Decode commands
- Read/write registers
- Transfer data between SPI master and raven_spi

This module acts as the communication interface.

---

# Complete Data Flow

```
SPI Master

↓

spi_slave

↓

raven_spi

↓

I0 / I1 Signals

↓

AMUX2_3V

↓

Output
```

---

# Learning Outcome

I understood the RTL hierarchy of the mixed-signal design. The top-level module (`design_mux`) connects the digital SPI controller with the analog multiplexer. The analog macro is instantiated as a black box, while the digital modules are synthesized by OpenLane.
