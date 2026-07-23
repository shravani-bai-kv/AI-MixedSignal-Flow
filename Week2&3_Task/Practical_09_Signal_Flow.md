# Practical 09 - Complete Signal Flow Analysis

## Objective

The objective of this practical is to understand how signals travel through the mixed-signal design from the external SPI interface to the analog output.

---

# Overall Architecture

```
             External Inputs
        +----------------------+
        |  RST  SCK  SDI  CSB  |
        +----------+-----------+
                   |
                   v
            +--------------+
            |  raven_spi   |
            +--------------+
             |          |
             |          |
            I0         I1 (Reset Signal)
             \          /
              \        /
               v      v
            +--------------+
            |  AMUX2_3V    |
            +--------------+
                   |
                   |
                  OUT
```

---

## Step 1

External SPI signals enter the design through:

- RST
- SCK
- SDI
- CSB

These signals are connected to the Raven SPI controller.

---

## Step 2

The `raven_spi` module decodes SPI commands.

It controls:

- Reset
- PLL Enable
- Oscillator Enable
- Registers
- Analog Control Signals

---

## Step 3

The SPI controller generates two important outputs:

- I0
- I1

These become inputs to the analog multiplexer.

---

## Step 4

The signal `select` controls the analog multiplexer.

If:

```
select = 0
```

Output:

```
I0
```

If:

```
select = 1
```

Output:

```
I1
```

---

## Step 5

The selected signal appears at the final output pin.

```
OUT
```

---

# Signal Flow Summary

```
External SPI

↓

raven_spi

↓

I0 / I1

↓

AMUX2_3V

↓

Output
```

---

# Learning Outcome

I understood the complete signal path from the external SPI interface to the analog multiplexer output and learned how digital control logic interacts with analog IP in a mixed-signal chip.
