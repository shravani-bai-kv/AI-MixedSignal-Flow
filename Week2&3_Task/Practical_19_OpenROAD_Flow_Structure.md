# Practical 19 – OpenROAD Flow Structure

## Objective

To understand the directory structure of the OpenROAD-flow repository and identify the role of each important folder before executing the RTL-to-GDS flow.

---

# Software Used

- Ubuntu 26.04 (VirtualBox)
- Docker
- OpenROAD-flow
- Terminal

---

# Step 1 – Verify Current Directory

Command:

```bash
pwd
```

## Hands-on Screenshot

<img width="967" height="207" alt="image" src="https://github.com/user-attachments/assets/a605ce20-8311-43f2-902e-6e4cbe8786ea" />


---

# Step 2 – List Repository Contents

Command:

```bash
ls
```

## Hands-on Screenshot

<img width="1217" height="208" alt="image" src="https://github.com/user-attachments/assets/732b0992-de41-46c9-b67c-901beb352438" />


---

# Step 3 – Display Folder Structure

Command:

```bash
tree -L 2
```

## Hands-on Screenshot

<img width="1211" height="764" alt="image" src="https://github.com/user-attachments/assets/f5d9f057-885b-439a-9078-97d515ad0a4c" />


---

# Step 4 – Explore the Flow Directory

Commands:

```bash
cd flow
ls
```

## Hands-on Screenshot

<img width="856" height="115" alt="image" src="https://github.com/user-attachments/assets/08c03ffa-1539-445d-8797-3181daee9241" />


---

# Step 5 – Explore the Scripts Directory

Commands:

```bash
cd scripts
ls
```

## Hands-on Screenshot

<img width="1211" height="763" alt="image" src="https://github.com/user-attachments/assets/0d177f2c-0c92-43fb-bed6-ab8c5f13b981" />


---

# Step 6 – Return to Flow Directory

Commands:

```bash
cd ..
pwd
```

## Hands-on Screenshot

<img width="912" height="128" alt="image" src="https://github.com/user-attachments/assets/15d2adf5-31ed-4276-b568-381a85e8acd1" />


---

# Directory Structure Summary

| Folder | Purpose |
|----------|----------|
| flow | Main RTL-to-GDS automation flow |
| designs | RTL designs and configuration files |
| platforms | Technology libraries and PDK data |
| scripts | Tcl scripts controlling each flow stage |
| util | Utility scripts |
| test | Regression and test designs |
| logs | Execution logs |
| reports | Area, timing, and power reports |
| results | Generated implementation outputs |

---

# Learning Outcomes

- Understood the OpenROAD-flow repository structure.
- Identified the purpose of major directories.
- Explored the automation scripts used in the RTL-to-GDS flow.
- Learned where logs, reports, and final outputs are stored.

---

# Conclusion

This practical provided an overview of the OpenROAD-flow repository organization. Understanding the directory structure establishes the foundation for subsequent stages such as synthesis, floorplanning, placement, clock tree synthesis, routing, and GDS generation.
