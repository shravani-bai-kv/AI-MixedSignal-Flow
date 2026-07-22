# Practical 02 - Tool Availability Check

## Objective

Verify the availability of the required software tools before executing the OpenLane mixed-signal flow.

---

## Git Verification

### Command

```bash
git --version
```

### Output

```
git version 2.53.0
```

**Status:** ✅ Installed

---

## Docker Verification

### Command

```bash
docker --version
```

### Output

```
Command 'docker' not found
```

**Status:** ❌ Docker is not installed.

---

## Observation

Git is available and can be used for cloning and managing the repository.

Docker is currently not installed. Since OpenLane primarily runs inside Docker containers, Docker installation is required before attempting the RTL-to-GDS flow.

This issue was identified during the environment verification stage and will be addressed before executing the OpenLane flow.
