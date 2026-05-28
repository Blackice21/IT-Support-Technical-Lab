# Computer Slow After Windows Update — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting a Windows 11 computer that became slow after installing updates.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"My computer became slow after the Windows update"
or
"Everything was fine before the update, now it's slow"
```

Common symptoms include:

- slow startup after update
- lag opening apps
- delayed login
- File Explorer sluggish
- browser feels slower than normal
- fan running harder after update
- CPU or disk usage stays high after reboot
- system feels slow for hours after updating

---

# 1. Gather Information

Start by asking:

- When was the update installed?
- Did the issue start immediately after the update?
- Is the slowdown:
  - constant?
  - intermittent?
  - only after boot?
  - only while using certain apps?

Also ask:

- Has the PC been restarted since the update finished?
- Was it a:
  - Windows cumulative update
  - feature update
  - driver update

---

# 2. Restart the Computer Again

Very common first step.

After Windows updates, background processes often continue running until another reboot.

Restart the PC and retest.

This can clear:

- pending update tasks
- incomplete update installs
- temporary service issues

---

# 3. Check Windows Update Status

Open:

```text
Settings → Windows Update
```

Verify whether Windows is still:

- downloading updates
- installing updates
- finishing configuration
- waiting for restart

Sometimes updates appear finished but continue working in the background.

---

# 4. Open Task Manager

Open:

```text
Ctrl + Shift + Esc
```

Review:

- CPU
- Memory
- Disk

Look for resource spikes after the update.

---

# 5. Check for High Disk Usage

In Task Manager:

Sort by:

```text
Disk
```

Look for:

```text
100% Disk Usage
```

Common update-related causes:

- Windows Update service
- TrustedInstaller
- Search indexing
- update cleanup tasks
- Defender scanning updated files

---

# 6. Check for High CPU Usage

Sort by:

```text
CPU
```

Look for:

- Windows Modules Installer Worker
- Service Host processes
- Windows Defender
- SearchIndexer.exe
- browser processes
- update services consuming CPU

---

# 7. Check Memory Usage

Sort by:

```text
Memory
```

Look for:

- apps using large amounts of RAM
- background apps reloading after update
- memory pressure after login

---

# 8. Let Windows Finish Background Optimization

After updates Windows may continue:

- indexing files
- rebuilding search index
- optimizing updates
- cleaning update files
- running maintenance tasks

This can last minutes to hours depending on hardware.

If system is usable, allow time for it to complete.

---

# 9. Check Startup Applications

Open:

```text
Task Manager → Startup apps
```

Disable unnecessary startup programs.

Examples:

- Teams
- Discord
- OneDrive
- Adobe updater
- Steam
- vendor utilities

Too many startup apps make post-update slowdowns worse.

---

# 10. Check Available Disk Space

Open:

```text
This PC
```

Low free storage after update can impact performance.

Recommended:

```text
Keep at least 10–20% free disk space
```

Large updates often consume additional storage temporarily.

---

# 11. Run Disk Cleanup

Open:

```text
cleanmgr
```

Remove:

- Temporary files
- Windows Update Cleanup
- Delivery Optimization files
- Recycle Bin contents
- temporary update leftovers

---

# 12. Run System File Checker

Open Command Prompt as Administrator:

```cmd
sfc /scannow
```

Checks for:

- corrupted Windows system files
- damaged files after update

Repairs automatically where possible.

---

# 13. Run DISM Repair

If update corruption is suspected:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

Repairs the Windows image.

Restart afterward.

---

# 14. Check Drivers

Some Windows updates affect drivers.

Open:

```text
Device Manager
```

Check for issues with:

- display driver
- storage controller
- chipset
- Wi-Fi
- audio

Update drivers if needed.

---

# 15. Check for Windows Defender Scans

Open:

```text
Windows Security
```

Verify whether Defender is scanning after update.

This often causes temporary:

- CPU spikes
- disk usage spikes
- fan noise
- slowdown

---

# 16. Test Performance After Some Time

If update completed recently:

Wait 30–60 minutes and retest.

Windows often needs time to finish:

- indexing
- cache rebuilding
- update cleanup
- background maintenance

---

# 17. Escalate if Performance Remains Poor

If slowdown continues long after update:

Possible causes:

- corrupted update
- driver conflict
- failed update install
- failing storage device
- hardware issue exposed by update

Escalate if needed.

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Restart PC again
↓
Check Windows Update status
↓
Open Task Manager
↓
Check CPU / RAM / Disk usage
↓
Allow background optimization to complete
↓
Review startup apps
↓
Check free disk space
↓
Run Disk Cleanup
↓
Run SFC
↓
Run DISM
↓
Check drivers
↓
Check Defender activity
↓
Retest performance
↓
Escalate if issue continues
```

---

# Useful Commands & Tools

## Open Task Manager

```text
Ctrl + Shift + Esc
```

---

## Disk Cleanup

```cmd
cleanmgr
```

---

## System File Checker

```cmd
sfc /scannow
```

---

## Repair Windows Image

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

## Windows Update

```text
Settings → Windows Update
```

---

# Notes

Computers often feel slow after Windows updates because Windows may still be running background maintenance such as:

```text
Search indexing
Windows Update cleanup
File optimization
Defender scanning
Startup app reload
Driver configuration
```

A second reboot + time for background tasks to finish often resolves the issue.

If not, check:

```text
CPU
Memory
Disk
Drivers
Storage space
```

to isolate the bottleneck.

---
