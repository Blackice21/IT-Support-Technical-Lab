# Windows 11 Slow Login / Black Screen After Login — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting a Windows 11 system where login takes several minutes and the desktop loads slowly afterward.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"After I enter my password, Windows takes several minutes to load."
"After login, I only see my cursor for a while."
"The taskbar and apps take forever to appear."
```

Common symptoms include:

- login spinner stays for several minutes
- desktop loads slowly after credentials are entered
- black screen with only cursor visible
- taskbar takes a long time to appear
- startup apps load very slowly
- File Explorer is delayed
- system feels sluggish after reaching desktop
- icons, Start menu, and navbar take time to appear

---

# 1. Gather Information

Ask:

- When did the slow login start?
- Does it happen every login?
- Did it start after a Windows update?
- Is the user on a domain account or local account?
- Is the device connected to VPN, Wi-Fi, or Ethernet?
- Does it happen only when off the company network?
- Are network drives, printers, or OneDrive configured?

This issue is often caused by something delaying the user profile or desktop shell from loading.

---

# 2. Confirm Where the Delay Happens

Identify the exact delay point:

```text
Power on → normal
Login screen → normal
Enter credentials → long loading screen
Desktop appears → only cursor
Taskbar/apps load slowly
System feels sluggish afterward
```

This points toward:

```text
User profile loading issue
Startup app issue
Explorer shell delay
Network drive timeout
High disk usage
Windows update cleanup
OneDrive or sync delay
```

---

# 3. Open Task Manager After Login

Once the desktop or cursor appears, press:

```text
Ctrl + Shift + Esc
```

Check:

- CPU
- Memory
- Disk

Sort by:

```text
CPU
Disk
Memory
```

Look for high usage from:

- Windows Explorer
- Windows Update
- Antimalware Service Executable
- OneDrive
- SearchIndexer
- Teams
- startup apps
- Service Host processes

---

# 4. Check Disk Usage

Slow login is commonly caused by disk bottlenecks.

In Task Manager, check:

```text
Disk %
```

If disk is near:

```text
100%
```

the system may be struggling to load the user profile, desktop, taskbar, and startup programs.

Common causes:

- HDD instead of SSD
- Windows Update cleanup
- Defender scan
- Search indexing
- low storage
- failing disk

---

# 5. Restart Windows Explorer

If only the cursor appears or taskbar is missing:

Open Task Manager:

```text
Ctrl + Shift + Esc
```

Then:

```text
File → Run new task
```

Run:

```cmd
explorer.exe
```

If Explorer is already running:

```text
Task Manager → Windows Explorer → Restart
```

This can force the desktop, taskbar, and Start menu to reload.

---

# 6. Restart the Computer

Restart the system and test again.

A second reboot can clear:

- incomplete update tasks
- stuck startup processes
- hung Explorer shell
- pending login scripts
- temporary profile load issues

---

# 7. Check Startup Applications

Open:

```text
Task Manager → Startup apps
```

Disable unnecessary startup apps.

Common examples:

- Teams
- Discord
- Spotify
- Steam
- Adobe updater
- OneDrive
- printer utilities
- vendor support tools

Too many startup apps can delay the desktop and taskbar after login.

---

# 8. Check Windows Update Status

Open:

```text
Settings → Windows Update
```

Check for:

- pending updates
- update cleanup
- required restart
- recently installed updates

Windows may continue background work after the user logs in.

---

# 9. Check OneDrive or Cloud Sync

OneDrive can delay desktop and file loading.

Check:

- OneDrive sync status
- stuck syncing files
- Desktop/Documents/Pictures redirection
- large files syncing after login

Temporarily pause sync and retest.

---

# 10. Check Network Drives and Printers

Mapped drives and network printers can delay login if unreachable.

Check:

```text
This PC
```

Look for:

- disconnected mapped drives
- unavailable network shares
- slow network printers
- domain resources timing out

If a mapped drive points to an unavailable server, Windows may wait before finishing login.

---

# 11. Check Domain / VPN Related Delays

If this is a work computer, ask:

- Is the user logging in offsite?
- Are they connected to VPN before login?
- Are group policies or login scripts running?
- Are mapped drives configured by GPO?

Slow login can happen when Windows waits for domain resources that are not reachable.

---

# 12. Check Free Storage Space

Open:

```text
This PC
```

Verify the `C:` drive has enough free space.

Recommended:

```text
10–20% free space
```

Low storage can slow profile loading and startup apps.

---

# 13. Run Disk Cleanup

Open:

```cmd
cleanmgr
```

Clean:

- temporary files
- Windows Update cleanup
- Delivery Optimization files
- Recycle Bin
- thumbnails

---

# 14. Check Disk Health

Run:

```cmd
wmic diskdrive get status
```

Expected:

```text
OK
```

If not OK, escalate for possible drive failure.

---

# 15. Run System File Checker

Open Command Prompt as Administrator:

```cmd
sfc /scannow
```

This checks for corrupted Windows files that may affect login or Explorer.

---

# 16. Run DISM Repair

Run:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

Then reboot.

---

# 17. Test With Another User Profile

Log in with another local or domain user.

If another profile loads normally:

Possible issue:

```text
Corrupted user profile
Bad startup item
Profile-specific mapped drive
Profile-specific OneDrive issue
```

---

# 18. Escalate if Needed

Escalate if the issue continues after basic troubleshooting.

Possible causes:

- failing HDD or SSD
- corrupted Windows profile
- bad startup application
- unreachable domain resources
- slow Group Policy processing
- OneDrive sync issue
- Windows update corruption
- malware
- hardware performance limitation

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Confirm login delay point
↓
Open Task Manager
↓
Check CPU / RAM / Disk
↓
Restart Explorer
↓
Restart PC
↓
Review startup apps
↓
Check Windows Update
↓
Check OneDrive sync
↓
Check mapped drives / printers
↓
Check domain or VPN delays
↓
Check free storage
↓
Run Disk Cleanup
↓
Check disk health
↓
Run SFC
↓
Run DISM
↓
Test another user profile
↓
Escalate if needed
```

---

# Useful Commands & Tools

## Open Task Manager

```text
Ctrl + Shift + Esc
```

## Start Explorer manually

```cmd
explorer.exe
```

## Disk Cleanup

```cmd
cleanmgr
```

## Check disk health

```cmd
wmic diskdrive get status
```

## System File Checker

```cmd
sfc /scannow
```

## Repair Windows image

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

# Notes

This issue is usually caused by something delaying the desktop environment after login:

```text
High disk usage
Startup applications
OneDrive sync
Network drive timeouts
Group Policy delays
Windows Update background tasks
Corrupted user profile
Windows Explorer shell delay
```

The key question is:

```text
Is Windows slow before login,
or
is the user profile slow after credentials are entered?
```

In this case, the issue is happening after credentials are entered, so focus on profile loading, startup apps, Explorer, disk usage, and network resources.

---
