# Week 5 Task – Magic Layout Visualization

## Objective

The objective of this task is to open the generated **AMUX2_3V** layout in the **Magic VLSI Layout Editor** using the SKY130 technology file and verify that the layout has been generated successfully. This allows visual inspection of the physical implementation before performing extraction, DRC, LVS, and post-layout simulation.

---

# Opening the Layout in Magic

The generated layout file (`AMUX2_3V.mag`) was opened in Magic using the SKY130 technology file.

### Command Used

```bash
magic -T sky130A.tech AMUX2_3V.mag
```

> <img width="1053" height="768" alt="image" src="https://github.com/user-attachments/assets/92b00d44-579b-4c2d-9cbc-981579ce1a92" />


---

# Magic Layout Window

After executing the command, the Magic editor launched successfully and displayed the physical layout of the analog multiplexer.

The layout consists of various fabrication layers required for implementation, including:

- NMOS transistor regions
- PMOS transistor regions
- N-Well and P-Well regions
- Diffusion layers
- Polysilicon gates
- Metal routing layers
- Contacts and vias
- Input, Output, VDD, and GND connections

### Magic Layout Screenshot

<img width="963" height="632" alt="image" src="https://github.com/user-attachments/assets/f812238d-910d-480b-9324-8a3a63b601fc" />


<p align="center">
<b>Paste Magic Layout Screenshot Here</b>
</p>

---

# Inspecting the Layout

Once the layout is opened, Magic provides several useful features for inspecting the design.

### Zoom to Fit the Layout

Press:

```text
w
```

This fits the complete layout within the viewing window, making it easier to inspect the entire design.

---

### Checking Individual Layers

Magic allows inspection of different layout layers.

Command:

```text
:what
```

After entering the command, click on any region of the layout.

Magic displays the layer information for the selected object, allowing verification of:

- Diffusion layers
- Polysilicon gates
- Metal layers
- Contacts
- Well regions

><img width="978" height="604" alt="image" src="https://github.com/user-attachments/assets/72cd9095-89bd-4687-8d67-bc3464e912e3" />


---

### Verifying the Layout File

The `.mag` file can also be checked from the terminal to view the layers stored in the layout.

Command:

```bash
grep "<< " AMUX2_3V.mag
```

This command lists all layout layers present inside the Magic layout file.

### Output Screenshot

<img width="881" height="320" alt="image" src="https://github.com/user-attachments/assets/ec8a77ee-88bd-4629-9ddc-715e11cecd0d" />


<p align="center">
<b>Paste grep Output Screenshot Here</b>
</p>

---

# Observation

The AMUX2_3V layout was successfully opened in the Magic layout editor without any errors. The layout displayed all the expected transistor structures, routing layers, and well regions. The layer information stored in the `.mag` file confirms that the physical layout contains the required SKY130 CMOS fabrication layers. This indicates that the generated layout is valid and ready for further verification.

---

# Conclusion

Opening and inspecting the layout in Magic is an important verification step in the physical design flow. It confirms that the generated layout is complete, viewable, and compatible with the SKY130 technology. With the layout successfully verified, the design is ready for the next stages, including extraction, DRC checking, LVS verification, and post-layout simulation.
