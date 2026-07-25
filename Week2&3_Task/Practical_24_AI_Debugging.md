# Practical 24 – AI-Assisted Debugging

## Objective

To understand how Artificial Intelligence (AI) can assist in debugging errors encountered during the OpenROAD RTL-to-GDS flow.

---

# Software Used

- Ubuntu 26.04
- Docker
- OpenROAD-flow
- Git
- ChatGPT (AI Assistant)

---

# Step 1 – Observe the Error

Run the flow.

```bash
make
```

The following error was observed:

```text
YOSYS_EXE is set to '/home/shravani/Desktop/openlane/OpenROAD-flow/tools/install/yosys/bin/yosys', but it is either not found or not executable.
```

## Hands-on Screenshot

> <img width="505" height="68" alt="image" src="https://github.com/user-attachments/assets/518af003-356c-4459-aed3-6f005efc4339" />


---

# Step 2 – Identify the Cause

Commands used:

```bash
ls tools
```

```bash
ls -la tools/yosys
```

```bash
ls -la tools/OpenROAD
```

Observation:

- OpenROAD and Yosys directories were present.
- Executable binaries were missing.
- The repository submodules were not fully initialized.

## Hands-on Screenshot

> <img width="773" height="391" alt="image" src="https://github.com/user-attachments/assets/5020604c-8dbb-4c66-9785-c2a01364987a" />


---

# Step 3 – AI-Based Analysis

Using ChatGPT, the error was analyzed.

Possible causes identified:

- Missing Git submodules
- Missing tool installation
- Incorrect repository setup
- Missing executable binaries

AI suggested verifying:

```bash
git submodule status
```

and

```bash
git submodule update --init --recursive
```

## Hands-on Screenshot

> <img width="757" height="55" alt="image" src="https://github.com/user-attachments/assets/34be0d26-55f1-4c6c-a053-ed507f420074" />


---

# Step 4 – Learning from Debugging

The debugging process highlighted the importance of:

- Reading terminal error messages carefully.
- Verifying repository structure.
- Checking tool installation.
- Using AI assistance for troubleshooting.

---

# Learning Outcomes

- Understood common OpenROAD installation issues.
- Learned systematic debugging.
- Used AI to analyze terminal errors.
- Improved troubleshooting skills.

---

# Conclusion

Although the OpenROAD flow could not be executed completely due to missing tool binaries, the debugging process successfully identified the root cause. AI-assisted debugging helped in understanding installation issues and suggested appropriate corrective actions.

---

# Git Commit

```bash
git add .
git commit -m "Practical 24: AI-assisted debugging"
git push origin main
```
