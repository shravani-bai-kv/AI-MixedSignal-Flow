# Existing Analog MUX Analysis

## Objective

The first step of Week 5 was to analyze the existing placeholder analog multiplexer (`AMUX2_3V`) used in the repository. This analysis helps identify the current implementation and the design views that will be replaced by the newly designed analog MUX.

---

## Repository Exploration

The repository was searched to locate all files related to `AMUX2_3V` and to identify where the macro is referenced in the OpenLane flow.

Commands used:

```bash
find . -name "AMUX2_3V.v"

ls -lh $(find . -name "AMUX2_3V.v")

cat $(find . -name "AMUX2_3V.v")

wc -l $(find . -name "AMUX2_3V.v")

grep -rn "AMUX2_3V" .
```

### Screenshot

> <img width="1138" height="695" alt="image" src="https://github.com/user-attachments/assets/43b34e17-a44d-43f5-a496-3d70ff8dfdfe" />
> <img width="1133" height="670" alt="image" src="https://github.com/user-attachments/assets/3112a4b0-784b-4c17-8b8a-df18501dbef7" />


---

## Observations

Three copies of the Verilog model were found in the repository.

| File | Description |
|------|-------------|
| `Verilog/AMUX2_3V.v` | Behavioral Verilog model |
| `openlane/src/AMUX2_3V.v` | Source used during OpenLane flow |
| `openlane/verilog/AMUX2_3V.v` | Verilog copy used for synthesis/integration |

Each file contains the same behavioral implementation and consists of 23 lines.

---

## Existing Verilog Model

The Verilog file implements a behavioral 2:1 multiplexer.

### Ports

**Inputs**

- I0
- I1
- select

**Output**

- out

The functionality is:

| Select | Output |
|---------|--------|
| 0 | I0 |
| 1 | I1 |
| Unknown | NaN |

The module serves as a behavioral representation of the analog multiplexer during simulation.

---

## Existing Macro Views

The placeholder analog MUX is represented using multiple design views.

- Verilog (`.v`)
- SPICE Netlist (`.spice`)
- Magic Layout (`.mag`)
- LEF
- GDS
- Liberty (`.lib`)
- DEF (where available)

These views will be replaced with the newly designed double-height analog MUX developed in this assignment.

---

## Conclusion

The existing `AMUX2_3V` macro was successfully analyzed. The behavioral Verilog implementation, repository locations, and available design views were identified. This analysis provides the foundation for designing and integrating a completely new analog multiplexer in the subsequent stages of the project.

### Screenshot

> <img width="1127" height="746" alt="image" src="https://github.com/user-attachments/assets/d82fd061-18be-46d7-b777-ddd78594ea29" />
