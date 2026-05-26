# Performance Troubleshooting (Help Desk)

A collection of practical help desk troubleshooting guides for diagnosing and fixing **slow computer / performance-related tickets**.

This section focuses on common tickets involving:

- High CPU usage
- High memory (RAM) usage
- 100% disk usage
- Applications freezing or not responding
- Slow or lagging Windows performance
- Laptop overheating
- Slow performance after Windows updates
- Full storage / low disk space

---

# Goal

The goal of these notes is to provide a **repeatable IT support workflow** for troubleshooting performance issues on Windows systems.

These guides are written from a **real help desk perspective** and are meant to help with:

- triaging performance tickets
- identifying the bottleneck quickly
- knowing what questions to ask the user
- narrowing down hardware vs software issues
- applying fixes in a logical order
- documenting troubleshooting steps clearly

---

# Common Performance Tickets

---

## 1. HDD / Disk at 100%

### Common Symptoms

- computer extremely slow
- File Explorer freezing
- long boot times
- apps hang while opening
- constant hard drive activity
- Task Manager shows:

```text
Disk: 100%
```

### Common Causes

- SysMain / Superfetch
- Windows Search indexing
- Windows Update
- antivirus scanning
- failing HDD
- low disk space
- excessive paging

### Troubleshooting Focus

- Task Manager → Disk column
- Resource Monitor
- `chkdsk`
- `wmic diskdrive get status`
- `sfc /scannow`

---

## 2. RAM / Memory at 100%

### Common Symptoms

- apps freezing
- browser tabs crashing
- computer lagging
- delayed typing/clicking
- "Out of memory" errors

### Common Causes

- too many apps open
- browser tabs consuming memory
- memory leak
- Teams / Chrome / Edge
- low physical RAM
- background startup applications

### Troubleshooting Focus

- Task Manager → Memory tab
- Startup apps review
- close heavy processes
- reboot system
- check pagefile usage
- possible RAM upgrade

---

## 3. CPU at 100%

### Common Symptoms

- fans spinning loudly
- PC lagging
- apps respond slowly
- mouse stuttering
- slow boot/login
- Task Manager shows:

```text
CPU: 100%
```

### Common Causes

- Windows Update
- browser tabs
- antivirus scans
- runaway process
- driver issue
- malware
- overheating / thermal throttling

### Troubleshooting Focus

- Task Manager → CPU sort
- background process review
- restart machine
- malware scan
- update drivers
- check temperatures

---

## 4. Applications Freezing / Not Responding

### Common Symptoms

- "Not Responding" window
- spinning blue circle
- delayed clicks
- app crashes

### Common Causes

- insufficient RAM
- high disk usage
- CPU spikes
- corrupt app install
- outdated app version
- storage nearly full

### Troubleshooting Focus

- Task Manager → End Task
- reboot system
- reinstall application
- update application
- check Event Viewer
- verify free disk space

---

## 5. Slow / Lagging Computer

### Common Symptoms

- slow login
- lag opening folders
- delayed typing
- mouse lag
- overall sluggish performance

### Common Causes

- high CPU
- high RAM
- high disk usage
- too many startup programs
- old HDD
- overheating
- pending Windows updates

### Troubleshooting Focus

- Task Manager review
- startup app cleanup
- reboot
- Windows Update check
- malware scan
- disk cleanup

---

## 6. Laptop Overheating

### Common Symptoms

- laptop hot to the touch
- fan constantly running
- performance slows under load
- random shutdowns
- keyboard or bottom panel hot

### Common Causes

- blocked vents
- dust buildup
- high CPU usage
- failing fan
- thermal throttling
- charging heat
- heavy background tasks

### Troubleshooting Focus

- CPU usage review
- Task Manager
- check airflow/vents
- clean fans
- BIOS updates
- monitor temperature

---

## 7. Slow After Windows Update

### Common Symptoms

- PC slower than normal after update
- long login
- high CPU or disk after reboot
- update stuck running in background

### Common Causes

- Windows indexing
- update cleanup tasks
- background update installs
- driver conflicts
- update corruption

### Troubleshooting Focus

- Windows Update status
- reboot again
- allow update to finish
- check disk usage
- `sfc /scannow`
- `DISM /Online /Cleanup-Image /RestoreHealth`

---

## 8. Storage Full / Low Disk Space

### Common Symptoms

- "Low disk space" warning
- Windows updates failing
- slow performance
- apps crashing due to lack of space

### Common Causes

- Downloads folder
- Temp files
- Recycle Bin
- OneDrive sync cache
- old installers
- Windows Update cache

### Troubleshooting Focus

- Disk Cleanup
- Storage Settings
- uninstall unused apps
- empty Recycle Bin
- clear temp folders
- move files to external/cloud storage

---

# General Performance Troubleshooting Workflow

When working a slow computer ticket:

```text
Gather information
↓
Reproduce issue
↓
Open Task Manager
↓
Check CPU / RAM / Disk usage
↓
Identify top resource consumer
↓
Restart computer
↓
Check startup apps
↓
Check disk space
↓
Check Windows Update
↓
Run malware scan
↓
Run disk cleanup
↓
Update drivers
↓
Test again
↓
Escalate if hardware issue suspected
```

---

# Helpful Tools

---

## Task Manager

Open:

```text
Ctrl + Shift + Esc
```

Used to check:

- CPU
- Memory
- Disk
- Startup apps
- top processes

---

## Resource Monitor

Open:

```text
resmon
```

Used for:

- detailed CPU usage
- disk activity
- memory usage
- file-level disk access

---

## Disk Cleanup

Open:

```text
cleanmgr
```

Used to remove:

- temp files
- update cache
- recycle bin contents

---

## System File Checker

```cmd
sfc /scannow
```

Scans and repairs system files.

---

## DISM Repair

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

Repairs Windows image corruption.

---

## Check Disk

```cmd
chkdsk C: /f /r
```

Checks disk health and bad sectors.

---

# Folder Structure

Example:

```text
performance-troubleshooting/
│
├── README.md
├── hdd-100-percent.md
├── ram-100-percent.md
├── cpu-100-percent.md
├── apps-freezing.md
├── slow-computer.md
├── laptop-overheating.md
├── slow-after-windows-update.md
└── storage-full.md
```

---

# Notes

Performance issues are often caused by one of four things:

```text
CPU
Memory
Disk
Temperature
```

Finding **which resource is bottlenecked first** usually makes troubleshooting much faster.

---
