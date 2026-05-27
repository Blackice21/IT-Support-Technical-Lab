# High CPU Usage in Windows 11 — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"CPU usage is really high."**  
> or  
> **"Computer is slow and Task Manager shows CPU at 100%."**

This guide covers how IT support would diagnose and fix high CPU usage in Windows 11.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"Computer is lagging, i can hear ths fans."
or
"my apps keep on freezing. my laptop is hot"
```

Common symptoms include:

- computer feels sluggish
- fan running loudly
- laptop gets hot
- apps open slowly
- mouse lag
- delayed typing
- browser stuttering
- video calls lagging
- Task Manager shows:

```text
CPU: 90–100%
```

---

# 1. Gather Information

Before troubleshooting, ask:

- When did the issue start?
- Is CPU high constantly or only sometimes?
- Does it happen:
  - after boot?
  - while browsing?
  - while gaming?
  - during meetings or video calls?

Also ask:

- Did anything change recently?
  - Windows update
  - software install
  - antivirus update
  - browser update
  - new hardware

---

# 2. Confirm CPU Usage in Task Manager

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
CPU
```

Identify which process is consuming the most CPU.

Common offenders:

- Windows Update
- Windows Defender
- Chrome / Edge
- Teams / Zoom
- SearchIndexer
- background updater services
- third-party antivirus
- stuck application process

---

# 3. Restart the Computer

Most common first fix.

Reboot clears:

- stuck processes
- temporary high CPU spikes
- background task buildup
- pending updates waiting for reboot

Then recheck Task Manager.

---

# 4. End High CPU Processes

Use Task Manager to locate the top CPU process.

Then:

- right-click process
- **End Task**

Common examples:

- browser tab consuming CPU
- frozen app
- updater stuck in background
- runaway process

---

# 5. Check Startup Applications

Open:

```text
Task Manager → Startup apps
```

Disable unnecessary startup items.

Examples:

- Teams
- Discord
- Steam
- Adobe updater
- OneDrive
- vendor utility software

Too many startup apps can spike CPU after login.

---

# 6. Check Windows Update

Open:

```text
Settings → Windows Update
```

Verify whether:

- updates are downloading
- updates are installing
- post-update optimization is running

Windows updates often cause temporary CPU spikes.

---

# 7. Check Windows Defender / Antivirus Activity

High CPU can be caused by:

- active virus scan
- real-time protection scanning
- scheduled scan

Open:

```text
Windows Security
```

Check scan status and recent activity.

---

# 8. Check Browser Usage

Browsers are a very common CPU consumer.

Check for:

- many open tabs
- YouTube/streaming
- browser extensions
- hardware acceleration issues
- tabs running scripts or ads

---

# 9. Check Background Processes

Open:

```text
Task Manager → Background Processes
```

Look for:

- update agents
- sync software
- cloud backup
- browser helpers
- vendor utilities

---

# 10. Run Malware Scan

Malware often causes sustained high CPU usage.

Run:

- Quick Scan
or
- Full Scan

Look for:

- crypto miners
- suspicious background tasks
- browser hijackers
- malicious services

---

# 11. Check CPU Temperature / Overheating

High temperatures can cause:

- throttling
- fan noise
- reduced performance

Common symptoms:

- laptop hot to the touch
- loud fan
- CPU stuck high while performance feels poor

Check:

- airflow
- vents
- dust buildup
- fan operation

---

# 12. Update Drivers

Open:

```text
Device Manager
```

Update:

- chipset drivers
- CPU-related drivers
- BIOS (if applicable)
- graphics drivers

Outdated drivers can cause CPU spikes.

---

# 13. Update Windows

Install any pending updates.

Open:

```text
Settings → Windows Update
```

Updates often fix:

- performance bugs
- scheduler issues
- CPU spikes
- service problems

---

# 14. Disable Unneeded Background Apps

Open:

```text
Settings → Apps → Startup
```

Disable apps not needed in the background.

Examples:

- Teams
- Spotify
- game launchers
- Adobe Creative Cloud
- sync clients

---

# 15. Use Resource Monitor for Deeper Review

Open:

```cmd
resmon
```

Then review:

```text
CPU tab
```

Check:

- services using CPU
- average CPU load
- thread-level activity

Useful when Task Manager is not detailed enough.

---

# 16. Reboot and Retest

After changes:

- restart PC
- reopen Task Manager
- compare CPU percentage

Monitor for improvement.

---

# 17. Escalate if Hardware Related

If CPU remains high with no obvious process:

Possible causes:

- overheating
- failing cooling fan
- BIOS issue
- hardware fault
- failing motherboard/power issue

Escalate if needed.

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Open Task Manager
↓
Sort by CPU
↓
Identify top CPU process
↓
Restart PC
↓
End high CPU task
↓
Review startup apps
↓
Check Windows Update
↓
Check antivirus activity
↓
Check browser usage
↓
Run malware scan
↓
Check temperature / overheating
↓
Update drivers
↓
Update Windows
↓
Use Resource Monitor
↓
Retest
↓
Escalate if hardware suspected
```

---

# Useful Commands & Tools

## Open Task Manager

```text
Ctrl + Shift + Esc
```

---

## Open Resource Monitor

```cmd
resmon
```

---

## Run System File Checker

```cmd
sfc /scannow
```

---

## Repair Windows Image

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

# Notes

High CPU usage is commonly caused by:

```text
Windows Update
Antivirus scanning
Browser tabs
Background processes
Startup applications
Overheating
Malware
Driver issues
```

Finding **which process is consuming CPU first** is usually the fastest path to resolution.

---
