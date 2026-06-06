# Microsoft Teams – Teams Won't Launch

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "Microsoft Teams won't open."
>
> "Nothing happens when I click Teams."
>
> "Teams starts and immediately closes."
>
> "Teams is stuck on the loading screen."

---

# Objective

Determine why Microsoft Teams is not launching and restore application functionality.

Common causes include:

* Corrupted Teams cache
* Hung Teams processes
* Corrupted installation
* Windows profile issues
* Missing updates
* Damaged application files
* Authentication problems
* System resource limitations

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What happens when you open Teams?
2. Do you receive an error message?
3. Did Teams work previously?
4. When did the issue start?
5. Have any updates recently been installed?
6. Are other Microsoft 365 applications working?

### Determine Scope

Ask:

> "Are other users experiencing the same issue?"

This helps determine if the issue is:

* User-specific
* Device-specific
* Organization-wide

---

# Step 1: Verify Teams Is Not Already Running

Sometimes Teams is running in the background but not displaying properly.

### Open Task Manager

1. Press:

Ctrl + Shift + Esc

2. Locate:

* Microsoft Teams
* Teams
* ms-teams

### If Found

1. Right-click the process.
2. Select:

End Task

3. Launch Teams again.

### Results

#### Teams Opens

Issue resolved.

#### Teams Still Fails

Continue troubleshooting.

---

# Step 2: Restart the Computer

Temporary Windows or application issues can prevent Teams from launching.

### Restart

1. Save open work.
2. Reboot the computer.
3. Attempt to launch Teams again.

### Results

#### Teams Opens

Temporary issue resolved.

#### Teams Still Fails

Continue troubleshooting.

---

# Step 3: Verify Internet Connectivity

Teams requires access to Microsoft 365 services.

### Test Connectivity

Open a browser and visit:

* https://www.office.com
* https://portal.office.com

### Results

#### Sites Load Properly

Network connectivity is functioning.

#### Sites Fail To Load

Investigate:

* Internet connectivity
* VPN issues
* DNS problems
* Firewall restrictions

---

# Step 4: Launch Teams From Browser

Determine whether the issue is application-specific.

### Test

1. Open browser.
2. Navigate to:

https://teams.microsoft.com

3. Sign in.

### Results

#### Browser Version Works

Issue likely exists with the Teams desktop application.

#### Browser Version Fails

Issue may involve:

* Authentication
* Account access
* Microsoft service availability

---

# Step 5: Verify Sign-In Works

### Test Microsoft 365 Authentication

1. Open an InPrivate or Incognito browser.
2. Navigate to:

https://portal.office.com

3. Sign in.

### Results

#### Login Successful

Account is functioning.

#### Login Fails

Investigate:

* Password issues
* MFA issues
* Account lockout
* Licensing problems

---

# Step 6: Clear Teams Cache

Corrupted cache is one of the most common causes of launch failures.

### Fully Close Teams

1. Right-click Teams in the system tray.
2. Select:

Quit

### Open Cache Location

Press:

Windows + R

Enter:

```text
%appdata%\Microsoft\Teams
```

Delete contents of:

* Cache
* databases
* GPUCache
* IndexedDB
* Local Storage
* tmp

### Relaunch Teams

Attempt to start Teams.

---

# Step 7: Run Teams as Administrator

### Launch As Administrator

1. Locate Teams shortcut.
2. Right-click.
3. Select:

Run as Administrator

### Results

#### Teams Opens

Possible permissions issue.

#### Teams Still Fails

Continue troubleshooting.

---

# Step 8: Verify Teams Is Updated

Older versions can fail after Microsoft service changes.

### Check For Updates

If Teams opens partially:

1. Click:

Settings and More (...)

2. Select:

Check for Updates

### If Teams Will Not Open

Proceed to reinstall.

---

# Step 9: Repair Teams Application

### Open Installed Apps

1. Open:

Settings → Apps → Installed Apps

2. Locate:

Microsoft Teams

3. Select:

Advanced Options

### Repair

Click:

Repair

Allow Windows to complete the process.

### Test Teams Again

Attempt launch.

---

# Step 10: Reset Teams Application

If repair does not work:

### Reset

1. Open:

Settings → Apps → Installed Apps

2. Locate:

Microsoft Teams

3. Select:

Advanced Options

4. Click:

Reset

### Relaunch Teams

Sign in if prompted.

---

# Step 11: Check System Resources

Insufficient resources can prevent Teams from starting.

### Open Task Manager

Review:

* CPU usage
* Memory usage
* Disk usage

### If Resources Are High

Close unnecessary applications and retry.

---

# Step 12: Test Another User Profile

Determine whether the issue is profile-related.

### Test

1. Sign into Windows using another account.
2. Launch Teams.

### Results

#### Teams Works

Issue likely exists within the original user profile.

#### Teams Fails

Issue is likely system-wide.

---

# Step 13: Reinstall Teams

Corrupted installations often require a reinstall.

### Remove Teams

1. Open:

Settings → Apps

2. Uninstall:

* Microsoft Teams
* Teams Machine-Wide Installer

### Restart Computer

Reboot the device.

### Install Latest Version

Install the newest Teams client.

### Test Again

Attempt launch.

---

# Step 14: Verify Windows Updates

Missing Windows updates can cause application compatibility issues.

### Check For Updates

1. Open:

Settings → Windows Update

2. Select:

Check for Updates

3. Install all available updates.

### Restart Computer

Retest Teams.

---

# Step 15: Check Microsoft 365 Service Health

If multiple users report launch issues:

### Microsoft 365 Admin Center

Navigate to:

Health → Service Health

Review incidents involving:

* Microsoft Teams
* Authentication Services
* Microsoft 365 Apps

### Results

#### Service Incident Exists

Monitor Microsoft's resolution.

#### No Incident Exists

Continue local troubleshooting.

---

# Quick Troubleshooting Flow

1. End Teams processes in Task Manager.
2. Restart computer.
3. Verify internet connectivity.
4. Test Teams Web App.
5. Verify Microsoft 365 sign-in.
6. Clear Teams cache.
7. Run Teams as Administrator.
8. Repair Teams.
9. Reset Teams.
10. Check system resources.
11. Test another Windows profile.
12. Reinstall Teams.
13. Install Windows updates.
14. Check Microsoft 365 Service Health.

---

# Expected Outcome

By following this process, a help desk technician can identify whether Teams fails to launch because of:

* Corrupted cache
* Hung processes
* Installation issues
* Authentication problems
* Windows profile corruption
* System resource limitations
* Missing updates
* Microsoft service issues

and restore Teams functionality for the user.

