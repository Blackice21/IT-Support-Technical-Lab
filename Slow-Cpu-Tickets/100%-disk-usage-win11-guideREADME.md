# 100% Disk Usage in Windows 11 — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"Disk is stuck at 100% in Windows 11."**  
> or  
> **"My PC is extremely slow and Task Manager shows 100% disk usage."**

This guide covers how IT support would diagnose and fix high disk usage in Windows 11.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"Computer is very slow"
or
"my apps freeze. computer is really slow."
```

Common symptoms include:

- PC feels extremely slow
- long boot times
- lag opening apps
- File Explorer freezing
- programs not responding
- constant hard drive activity
- loud HDD clicking/spinning
- Windows hangs while loading files
- Task Manager shows:

```text
Disk: 100%
```

even when CPU and RAM are low

---

# 1. Gather Information

Before troubleshooting, ask:

- When did the issue start?
- Is the slowdown constant or intermittent?
- Did anything change recently?
  - Windows update
  - software install
  - antivirus scan
  - driver update
  - new hardware

Also ask:

- HDD or SSD?
- How old is the drive?
- Does the issue happen:
  - immediately after boot?
  - only while opening programs?
  - randomly?

---

# 2. Confirm Disk Usage in Task Manager

Open:

```text
Ctrl + Shift + Esc
```

Then:

```text
Task Manager → Processes
```

Sort by:

```text
Disk
```

Identify which process is consuming disk resources.

Common offenders:

- Windows Update
- SysMain
- SearchIndexer
- Antimalware Service Executable
- OneDrive
- backup software
- browser cache
- third-party antivirus

---

# 3. Restart the Computer

Simple but effective first step.

Reboot the system and retest.

Temporary stuck processes often clear after restart.

---

# 4. Check Startup Applications

Open:

```text
Task Manager → Startup apps
```

Look for unnecessary startup items.

Disable anything not needed at boot.

Common examples:

- Teams auto-start
- Discord
- Steam
- Adobe updater
- cloud sync apps

---

# 5. Check Windows Update Activity

Open:

```text
Settings → Windows Update
```

Verify whether:

- updates are downloading
- updates are installing
- Windows is indexing after update

High disk activity is common during updates.

---

# 6. Disable SysMain (Superfetch) for Testing

SysMain commonly causes high disk usage on HDD systems.

Open Command Prompt as Administrator:

```cmd
net stop SysMain
```

Then test performance.

If disk drops immediately:

SysMain may be contributing.

---

# 7. Stop Windows Search Indexing for Testing

Open Command Prompt as Administrator:

```cmd
net stop WSearch
```

This temporarily disables indexing.

If disk usage improves:

Windows Search indexing may be the cause.

---

# 8. Check Disk Health

Run:

```cmd
chkdsk
```

or:

```cmd
wmic diskdrive get status
```

Expected healthy result:

```text
OK
```

If warnings appear:

Possible failing drive.

---

# 9. Run Check Disk Scan

Open Command Prompt as Administrator:

```cmd
chkdsk C: /f /r
```

This checks for:

- file system corruption
- bad sectors
- disk errors

May require reboot.

---

# 10. Run System File Checker

Check Windows system files.

Run:

```cmd
sfc /scannow
```

This scans for corrupted OS files and repairs them.

---

# 11. Run DISM Repair

If Windows image corruption is suspected:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

Then reboot.

---

# 12. Check Available Disk Space

Open:

```text
This PC
```

Verify free space.

If drive is nearly full:

Performance can degrade heavily.

Recommended:

- remove temporary files
- empty Recycle Bin
- clear Downloads folder
- uninstall unused software

---

# 13. Run Disk Cleanup

Open:

```text
Disk Cleanup
```

Clean:

- Temporary files
- Windows Update cleanup
- Recycle Bin
- Delivery Optimization files
- Thumbnails

---

# 14. Check Resource Monitor

Open:

```text
Task Manager → Performance → Open Resource Monitor
```

Then view:

```text
Disk
```

Review:

- highest disk activity
- read/write totals
- active time
- file paths generating activity

This helps identify exactly what is hammering the disk.

---

# 15. Scan for Malware

Malware can create constant disk activity.

Run:

- Windows Security quick scan
or
- Full scan

Look for:

- crypto miners
- background malware
- ransomware behavior
- suspicious scheduled tasks

---

# 16. Update Storage Drivers

Open:

```text
Device Manager
→ Disk drives
→ IDE ATA/ATAPI controllers
```

Then:

- Update driver

or

- uninstall storage controller
- reboot

---

# 17. Check Virtual Memory / Pagefile Usage

Heavy paging can cause constant disk activity.

If RAM is low:

Windows may constantly swap memory to disk.

Check:

```text
System Properties → Advanced → Performance → Virtual Memory
```

---

# 18. Check HDD vs SSD

If system uses an older HDD:

100% usage is much more common.

Common recommendation:

Upgrade:

```text
HDD → SSD
```

This is often the biggest performance improvement possible.

---

# 19. Replace Failing Drive if Needed

If SMART errors or bad sectors appear:

Replace drive immediately.

Warning signs:

- clicking noises
- slow file access
- freezes during file operations
- corrupted files
- chkdsk errors

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Confirm 100% disk in Task Manager
↓
Identify top disk process
↓
Restart PC
↓
Check startup apps
↓
Check Windows Update
↓
Disable SysMain
↓
Disable Search indexing
↓
Check disk health
↓
Run chkdsk
↓
Run SFC
↓
Run DISM
↓
Free disk space
↓
Disk Cleanup
↓
Resource Monitor review
↓
Malware scan
↓
Update drivers
↓
Check pagefile
↓
Evaluate HDD vs SSD
↓
Replace drive if failing
```

---

# Useful Commands Reference

## Stop SysMain

```cmd
net stop SysMain
```

---

## Stop Windows Search

```cmd
net stop WSearch
```

---

## Check disk status

```cmd
wmic diskdrive get status
```

---

## Run CHKDSK

```cmd
chkdsk C: /f /r
```

---

## Scan system files

```cmd
sfc /scannow
```

---

## Repair Windows image

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

## Open Task Manager

```text
Ctrl + Shift + Esc
```

---
