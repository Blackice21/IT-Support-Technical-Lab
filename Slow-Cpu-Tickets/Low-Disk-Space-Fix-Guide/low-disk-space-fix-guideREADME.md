# Windows 11 Storage Almost Full — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting a Windows 11 machine that is running low on storage space.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"My storage is almost full"
or
"I'm getting a low disk space warning"
```

Common symptoms include:

- Windows notification:
  - **Low Disk Space**
  - **Storage Almost Full**
- slow performance
- Windows updates failing
- downloads failing
- applications crashing unexpectedly
- inability to save files
- File Explorer lagging
- browser download errors
- Outlook mailbox sync issues
- OneDrive sync failures

---

# 1. Gather Information

Start by asking:

- Which drive is full?
  - `C:`
  - `D:`
  - external drive
- When did this start?
- Has the user recently:
  - downloaded large files?
  - installed software?
  - copied media files?
  - run Windows updates?

Also ask:

- Is the issue affecting:
  - saving files
  - downloads
  - app performance
  - Windows updates

---

# 2. Check Disk Space

Open:

```text
This PC
```

Review available storage on all drives.

Example:

```text
Local Disk (C:)
450 MB free of 237 GB
```

Determine:

- how much free space remains
- which drive is affected

---

# 3. Open Storage Settings

Go to:

```text
Settings → System → Storage
```

Review usage by category.

Common categories:

- Installed Apps
- Temporary Files
- Documents
- Pictures
- Videos
- Downloads
- Other
- System & Reserved

This helps identify what is consuming space.

---

# 4. Empty Recycle Bin

A quick and common cleanup step.

Check:

```text
Recycle Bin
```

Then:

```text
Empty Recycle Bin
```

Large deleted files may still be consuming storage.

---

# 5. Run Disk Cleanup

Open:

```cmd
cleanmgr
```

Select drive:

```text
C:
```

Clean common items such as:

- Temporary files
- Windows Update Cleanup
- Delivery Optimization files
- Thumbnails
- Temporary Internet files
- Recycle Bin
- Error reports

---

# 6. Remove Temporary Files

Open:

```text
Settings → System → Storage → Temporary Files
```

Review and remove unnecessary files.

Common items:

- temporary files
- cache files
- update leftovers
- temp installer files

---

# 7. Check Downloads Folder

Open:

```text
C:\Users\<username>\Downloads
```

Look for large files such as:

- ISO files
- ZIP files
- installers
- videos
- screenshots
- duplicate downloads

Delete or move files if not needed.

---

# 8. Uninstall Unused Applications

Open:

```text
Settings → Apps → Installed Apps
```

Sort by:

```text
Size
```

Remove software no longer needed.

Common examples:

- games
- unused Adobe apps
- old VPN clients
- duplicate software
- trial software

---

# 9. Check Large User Files

Look in:

- Documents
- Desktop
- Downloads
- Pictures
- Videos

Large files often include:

- `.iso`
- `.zip`
- `.mp4`
- `.mov`
- `.psd`
- `.bak`
- `.vhdx`

Move to:

- external drive
- OneDrive
- network share
- cloud storage

---

# 10. Check OneDrive / Cloud Sync

Review whether:

- large files are syncing locally
- "Always keep on this device" is enabled

Consider:

```text
Free up space
```

for files already stored in OneDrive.

---

# 11. Check Windows Update Cleanup Files

Windows updates can leave large cleanup files behind.

Run:

```text
Disk Cleanup → Clean up system files
```

Then review:

```text
Windows Update Cleanup
```

This can sometimes recover several GB.

---

# 12. Check System Restore Usage

System restore points can consume storage.

Open:

```text
System Properties → System Protection
```

Review:

- restore point usage
- allocated space

Delete older restore points if appropriate.

---

# 13. Restart the Computer

Restart after cleanup.

This can release:

- temp files in use
- pending cleanup tasks
- update cache cleanup after reboot

---

# 14. Verify Free Space Again

Re-open:

```text
This PC
```

Confirm storage increased.

Recommended:

```text
10–20% free space
```

for healthy Windows performance.

---

# 15. Escalate if Space Keeps Filling Up

If storage keeps shrinking unexpectedly:

Possible causes:

- runaway log files
- failed backups
- sync cache growth
- Windows update loop
- Outlook OST/PST growth
- application cache issue
- malware

Escalate for deeper review if needed.

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Check disk space
↓
Open Storage settings
↓
Empty Recycle Bin
↓
Run Disk Cleanup
↓
Remove temporary files
↓
Review Downloads folder
↓
Uninstall unused apps
↓
Review large personal files
↓
Check OneDrive usage
↓
Clean Windows Update files
↓
Review System Restore usage
↓
Restart PC
↓
Verify free space
↓
Escalate if space keeps filling
```

---

# Useful Tools & Commands

## Open Disk Cleanup

```cmd
cleanmgr
```

---

## Open Storage Settings

```text
Settings → System → Storage
```

---

## View installed apps

```text
Settings → Apps → Installed Apps
```

---

## Check This PC storage

```text
This PC
```

---

# Notes

Storage usually fills up from one of these:

```text
Downloads folder
Temporary files
Windows Update cleanup files
Recycle Bin
Large media files
Installed applications
Cloud sync cache
Restore points
```

Low storage can cause:

```text
Slow performance
Update failures
Download issues
Application crashes
General system instability
```

Keeping **10–20% free disk space** is a good general rule for healthy Windows performance.

---
