
# Practical 22 – Placement and Routing

## Objective

To understand the placement and routing stages of the OpenROAD physical design flow.

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


---

## Step 2 – Locate Placement Script

```bash
find . -iname "*place*"
```

## Hands-on Screenshot


> <img width="1296" height="495" alt="image" src="https://github.com/user-attachments/assets/5957edfd-917a-45e8-a041-10f92096db83" />


---

## Step 3 – Locate Routing Script

```bash
find . -iname "*route*"
```

## Hands-on Screenshot


> <img width="944" height="683" alt="image" src="https://github.com/user-attachments/assets/3e246e16-b386-48ee-86bb-680986da6dd9" />


---

## Step 4 – View Placement Script

```bash
cd scripts
head -40 macro_place.tcl
```



## Hands-on Screenshot


> <img width="935" height="763" alt="image" src="https://github.com/user-attachments/assets/8cdad523-6d2c-40ff-8c23-21517bd914d6" />


---

## Step 5 – View Routing Script

```bash
head -40 detail_route.tcl
```

(Replace with the actual filename if different.)

## Hands-on Screenshot


> <img width="898" height="535" alt="image" src="https://github.com/user-attachments/assets/44b5cb14-747f-4dfb-a9df-79e4b52e564e" />

> <img width="983" height="764" alt="image" src="https://github.com/user-attachments/assets/990b19a3-9b8a-4150-a44c-af2cafc185a7" />


---

## Important Commands

| Command | Purpose |
|----------|----------|
| global_placement | Performs global placement |
| detailed_placement | Legalizes standard-cell placement |
| global_route | Generates global routing |
| detailed_route | Creates final routed layout |

---

## Learning Outcomes

- Explored placement scripts.
- Explored routing scripts.
- Understood how physical connections are created.

---

## Conclusion

Placement determines the location of standard cells, while routing creates the metal interconnections required to implement the synthesized design.

---

## Git Commit

```bash
git add .
git commit -m "Practical 22: Studied placement and routing"
git push origin main
```
