# High RAM Usage in Windows 11 — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"Memory usage is really high."**  
> or  
> **"Windows feels slow and Task Manager shows RAM near 100%."**

This guide covers how IT support would diagnose and fix high memory usage in Windows 11.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"Computer is running slow and my apps keep freezing"
or
"Memory is at 100%"
```

Common symptoms include:

- slow performance
- browser tabs crashing
- apps freezing
- delayed typing or mouse movement
- "Not Responding" applications
- lag switching between apps
- system becomes sluggish over time
- Task Manager shows:

```text
Memory: 90–100%
```

---

# 1. Gather Information

Before troubleshooting, ask:

- When did the issue start?
- Is the slowdown constant or intermittent?
- Does it happen:
  - immediately after boot?
  - after several hours?
  - only while specific apps are open?

Also ask:

- How much RAM is installed?
- What applications were running when it happened?
- Has anything changed recently?
  - Windows update
  - software install
  - browser update
  - antivirus install

---

# 2. Confirm High Memory Usage in Task Manager

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
Memory
```

Identify which process is using the most RAM.

Common offenders:

- Chrome / Edge
- Teams
- Discord
- Outlook
- Windows Defender
- OneDrive
- Zoom
- Virtual machines
- memory leak from a stuck app

---

# 3. Restart the Computer

Most common first step.

Reboot the system and check memory usage again.

This clears:

- cached memory
- stuck processes
- memory leaks
- background application buildup

---

# 4. Close High-Memory Applications

Use Task Manager to identify heavy apps.

Then:

- select the process
- click **End Task**

Common examples:

- too many browser tabs
- Teams
- Adobe apps
- large spreadsheets
- background sync apps

---

# 5. Check Startup Applications

Open:

```text
Task Manager → Startup apps
```

Disable unnecessary startup programs.

Common examples:

- Teams auto-launch
- Discord
- Steam
- OneDrive
- Adobe updater
- Spotify

Reducing startup apps lowers RAM usage after login.

---

# 6. Check Browser Tab Usage

Browsers are a very common source of high memory use.

Check:

- number of tabs open
- streaming tabs
- extensions/plugins
- multiple browser windows

Chrome and Edge can consume large amounts of RAM with many tabs open.

---

# 7. Check for Memory Leaks

Look for:

- one process continuously increasing memory usage
- memory not freeing after app closes
- RAM climbing over time

Common signs:

```text
Memory usage keeps increasing even when system is idle
```

Often caused by:

- buggy application
- browser extension
- driver issue

---

# 8. Check Windows Update Activity

Open:

```text
Settings → Windows Update
```

Verify whether:

- updates are downloading
- updates are installing
- post-update background tasks are running

Windows updates can temporarily increase memory usage.

---

# 9. Check Available RAM

Open:

```text
Task Manager → Performance → Memory
```

Review:

- Total installed RAM
- Available RAM
- In use
- Cached
- Memory speed
- Slots used

Example:

```text
Installed: 8 GB
In Use: 7.5 GB
Available: 0.4 GB
```

---

# 10. Check Virtual Memory / Pagefile

If RAM is full, Windows may use disk as memory.

This causes:

- lag
- freezing
- high disk usage

Check:

```text
System Properties
→ Advanced
→ Performance
→ Settings
→ Advanced
→ Virtual Memory
```

Verify pagefile is enabled.

---

# 11. Update Windows

Install any pending Windows updates.

Open:

```text
Settings → Windows Update
```

Some updates fix:

- memory leaks
- driver problems
- performance bugs

---

# 12. Check for Background Sync Apps

Look for:

- OneDrive
- Dropbox
- Google Drive
- backup software
- file sync utilities

These can consume memory in the background.

---

# 13. Upgrade RAM (If Needed)

If usage is consistently high and workload is normal:

Hardware may be the limitation.

Example:

```text
4 GB → often too low
8 GB → usable
16 GB+ → preferred
```

Adding RAM is often the long-term fix.

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Open Task Manager
↓
Sort by memory usage
↓
Identify top process
↓
Restart PC
↓
Close heavy apps
↓
Review startup apps
↓
Check browser tabs
↓
Check for memory leak
↓
Check Windows Update
↓
Check pagefile
↓
Update Windows
↓
Upgrade Ram

---

# Useful Commands & Tools

## Open Task Manager

```text
Ctrl + Shift + Esc
```

---

## Open Windows Memory Diagnostic

```cmd
mdsched.exe
```

---

## Open Resource Monitor

```cmd
resmon
```

---

## View Memory Performance

```text
Task Manager → Performance → Memory
```

---

# Notes

High RAM usage is often caused by:

```text
Too many applications open
Too many browser tabs
Startup applications
Memory leaks
Background sync apps
Low physical RAM
```

Finding **which process is consuming memory first** is usually the fastest way to solve the ticket.

---
