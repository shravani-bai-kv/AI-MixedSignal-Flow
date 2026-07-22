# Practical 06 – Docker Installation

## Objective

Install Docker to prepare the environment for executing the OpenLane mixed-signal RTL-to-GDS flow.

---

## Commands Used

```bash
sudo apt update
sudo apt install docker.io
docker --version
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
```

---

## Issues Encountered

### Issue 1

Incorrect system date caused:

```
Release file is not valid yet
```

### Fix

Corrected the system date and synchronized the VM clock.

---

### Issue 2

Temporary DNS resolution failure.

### Fix

Verified internet connectivity using:

```bash
ping -c 4 8.8.8.8
ping -c 4 google.com
```

Both commands were successful.

---

## Docker Status

```
Active: active (running)
```

Docker service started successfully.

---

## Learning Outcome

Docker is the container platform used by OpenLane. Successfully installing and starting Docker prepares the Linux environment for executing the mixed-signal physical design flow.
