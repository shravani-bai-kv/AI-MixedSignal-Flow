
# Practical 21 – Floorplanning Script Study

## Objective

To study the floorplanning stage of the OpenROAD flow and understand how the floorplan is created before placement.

---

## Software Used

- Ubuntu 26.04
- Docker
- OpenROAD-flow

---

## Step 1 – Navigate to Flow Directory

```bash
cd ~/OpenROAD-flow/flow
```

## Hands-on Screenshot


> <img width="967" height="207" alt="image" src="https://github.com/user-attachments/assets/282d3037-b9f9-4628-a658-7b16e8757813" />


---

## Step 2 – Go to Scripts Folder

```bash
cd scripts
ls
```

## Hands-on Screenshot


> <img width="1086" height="323" alt="image" src="https://github.com/user-attachments/assets/76b31cb2-49fc-4405-b23c-e7518e45a6b9" />


---

## Step 3 – Locate Floorplan Script

```bash
find . -iname "*floor*"
```

## Hands-on Screenshot


> <img width="718" height="63" alt="image" src="https://github.com/user-attachments/assets/8679bcc3-e82c-4410-a1ca-f42cdc731077" />


---

## Step 4 – View the Script

```bash
head -50 floorplan.tcl
```



## Hands-on Screenshot


> <img width="727" height="176" alt="image" src="https://github.com/user-attachments/assets/f4ef74b0-d94b-496f-8a7f-cce986f877d0" />

> <img width="1168" height="749" alt="image" src="https://github.com/user-attachments/assets/68492a64-203b-4ef8-a8c6-d29e5611320d" />


---

## Step 5 – Identify Floorplanning Commands

Look for commands similar to:

```tcl
initialize_floorplan
place_pins
tapcell
pdngen
```

## Hands-on Screenshot


> <img width="1221" height="753" alt="image" src="https://github.com/user-attachments/assets/1ec6f3f9-9785-4b9d-91ae-22200f7decc7" />


---

## Important Commands

| Command | Purpose |
|----------|----------|
| initialize_floorplan | Creates die/core area |
| place_pins | Places IO pins |
| tapcell | Inserts tap cells |
| pdngen | Generates power distribution network |

---

## Learning Outcomes

- Studied floorplanning automation.
- Understood die and core initialization.
- Learned how IO pins and power network are generated.

---

## Conclusion

Floorplanning defines the physical layout before standard-cell placement and establishes the foundation for the remaining implementation stages.

---

## Git Commit

```bash
git add .
git commit -m "Practical 21: Studied floorplanning script"
git push origin main
```
