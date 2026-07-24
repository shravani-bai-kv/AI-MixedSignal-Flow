# Practical 20 – Synthesis Script Study

## Objective

To understand the synthesis stage of the OpenROAD RTL-to-GDS flow by exploring the synthesis scripts, configuration files, and generated synthesis reports.

---

# Software Used

- Ubuntu 26.04 (VirtualBox)
- Docker
- OpenROAD-flow
- Terminal

---

# Step 1 – Navigate to the Flow Directory

```bash
cd ~/OpenROAD-flow/flow
pwd
```

## Hands-on Screenshot

<img width="1210" height="132" alt="image" src="https://github.com/user-attachments/assets/0b894cf7-870c-4fc6-80f3-5ae5c2a1eec2" />


---

# Step 2 – Explore the Scripts Directory

```bash
cd scripts
ls
```

## Hands-on Screenshot

<img width="1183" height="412" alt="image" src="https://github.com/user-attachments/assets/ebeb2d3b-7ab1-45f0-8a4c-891887bc040a" />


---

# Step 3 – Locate the Synthesis Script

```bash
ls *synth*
```


## Hands-on Screenshot

<img width="982" height="101" alt="image" src="https://github.com/user-attachments/assets/d9c34297-4cb2-4bda-9c97-59c27d750b36" />


---

# Step 4 – View the Synthesis Script

Replace the filename below with the actual synthesis script name if different.



If the file is long:

```bash
less synth.tcl
```



## Hands-on Screenshot

><img width="775" height="40" alt="image" src="https://github.com/user-attachments/assets/3014e981-a35a-4e07-81ff-8e918b712be6" />

> <img width="1214" height="763" alt="image" src="https://github.com/user-attachments/assets/7a42e5fb-b28a-4280-9037-ea6a95fc10ae" />


---

# Step 5 – Identify Important Synthesis Commands

Look for commands similar to:

```tcl
read_verilog
link_design
read_liberty
synth
write_verilog
```

## Hands-on Screenshot

<img width="949" height="458" alt="image" src="https://github.com/user-attachments/assets/36a5524c-0b9d-45ef-b0b6-5212e7b32f52" />

> <img width="1094" height="759" alt="image" src="https://github.com/user-attachments/assets/34391243-0da9-490a-8214-18619686f007" />


---

# Step 6 – Return to the Flow Directory

```bash
cd ..
pwd
```

## Hands-on Screenshot

<img width="649" height="126" alt="image" src="https://github.com/user-attachments/assets/12899013-ae19-444b-b885-121aa2c5ab66" />


---

# Important Synthesis Commands

| Command | Purpose |
|----------|----------|
| read_verilog | Reads the RTL source files |
| read_liberty | Loads standard cell timing library |
| link_design | Links the top-level module |
| synth | Performs logic synthesis |
| write_verilog | Writes synthesized gate-level netlist |
| report_checks | Generates timing report |
| report_design_area | Reports synthesized design area |

---

# Learning Outcomes

- Explored the synthesis automation script.
- Understood the sequence of synthesis commands.
- Learned how RTL is converted into a gate-level netlist.
- Identified important synthesis-related Tcl commands.

---

# Conclusion

The synthesis stage converts RTL into an optimized gate-level netlist using the target technology library. The synthesis script automates this process and generates reports that are used for the subsequent physical design stages.

---

# Git Commit

```bash
git add .
git commit -m "Practical 20: Studied OpenROAD synthesis script"
git push origin main
```
