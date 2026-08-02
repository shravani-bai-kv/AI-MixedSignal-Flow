# Week 5 Command Log

## ngspice

```bash
ngspice amux2_tg.spice
```

---

## Magic

```bash
magic -T sky130A.tech
```

```tcl
load amux2_tg
```

```tcl
drc check
```

```tcl
drc why
```

```tcl
extract all
```

```tcl
ext2spice lvs
```

```tcl
ext2spice
```

---

## Verification

```bash
grep "<<" AMUX2_3V.mag
```

```bash
find . -name "*.mag"
```

```bash
find . -name "*.spice"
```

---

# Notes

All commands executed during layout generation, DRC checking, extraction, and verification are documented above.
