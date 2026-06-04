# Microsoft 365 Help Desk Ticket: OneDrive Storage Full

## Ticket Summary

**Issue:** User is unable to upload or synchronize files because their OneDrive storage quota has been reached.

**User Complaint:**

> "My files won't upload to OneDrive anymore, and I'm getting messages saying my storage is full."

**Service:** Microsoft OneDrive for Business
**Environment:** Microsoft 365 / Windows 10 or Windows 11
**Ticket Type:** Storage Quota / Synchronization Issue
**Priority:** Medium

---

# 1. Gather Information from the User

Before making changes, gather information about the issue.

## Questions to Ask

* When did the issue begin?
* What error message is being displayed?
* Are all files affected or only certain files?
* Have large files recently been uploaded?
* Is synchronization completely stopped?
* Has the user recently deleted files?
* Are files being backed up from Desktop, Documents, or Pictures?

---

# 2. Verify the Issue

Confirm that OneDrive storage is actually full.

## Check OneDrive Notifications

1. Click the **OneDrive cloud icon** in the system tray.
2. Review any warning messages.

Common messages include:

```text
Your OneDrive is full.
```

```text
Can't sync files.
```

```text
Storage quota exceeded.
```

### Expected Result

A storage-related warning confirms the issue.

---

# 3. Verify Storage Usage Online

1. Open a browser.
2. Sign into Microsoft 365.
3. Open OneDrive.
4. Click the **Settings** gear icon.
5. Select **OneDrive Settings**.
6. Review available storage.

### Example

```text
Used: 995 GB
Available: 5 GB
```

### Expected Result

Determine whether the user has reached or exceeded their storage limit.

---

# 4. Identify Large Files Consuming Storage

Locate files using the most storage.

## Using OneDrive Online

1. Open OneDrive.
2. Navigate through folders.
3. Sort by file size if available.

## Using File Explorer

1. Open the user's OneDrive folder.
2. Change view to Details.
3. Sort by Size.

### Common Storage Consumers

* Videos
* ISO files
* Virtual machine files
* ZIP archives
* PST files
* Backup files

### Expected Result

Identify files contributing significantly to storage usage.

---

# 5. Check the OneDrive Recycle Bin

Many users delete files but forget that deleted files continue consuming storage.

## Recovery and Cleanup

1. Open OneDrive Online.
2. Select **Recycle Bin**.
3. Review deleted files.
4. Permanently delete unnecessary items.

### Important

Files remain in the OneDrive Recycle Bin and continue counting against storage until permanently removed.

### Expected Result

Storage usage decreases after emptying the Recycle Bin.

---

# 6. Remove Unnecessary Files

Work with the user to determine what can be deleted or archived.

## Examples

Files that may be removed:

```text
Old backup files
Archived projects
Duplicate files
Large video recordings
Unused ISO images
```

### Best Practice

Confirm with the user before deleting business-related content.

---

# 7. Move Large Files to Alternate Storage

If files must be retained, consider moving them elsewhere.

## Options

* External storage device
* Network file share
* SharePoint document library
* Department archive location

### Expected Result

Storage is reduced without deleting important data.

---

# 8. Verify Synchronization Resumes

After storage has been freed:

1. Click the OneDrive cloud icon.
2. Verify status changes to:

```text
Syncing...
```

Then:

```text
Up to date
```

### Expected Result

Previously stalled files begin synchronizing.

---

# 9. Test File Upload

Verify functionality by uploading a test file.

## Validation Steps

1. Create a file named:

```text
StorageTest.txt
```

2. Save it inside the OneDrive folder.
3. Wait for synchronization.
4. Verify the file appears in OneDrive Online.

### Expected Result

The file uploads successfully.

---

# 10. Verify Available Storage

Confirm storage levels after cleanup.

## Example

Before Cleanup:

```text
995 GB Used
5 GB Free
```

After Cleanup:

```text
850 GB Used
150 GB Free
```

### Expected Result

Sufficient storage is available for future synchronization.

---

# 11. Educate the User

Provide recommendations to help prevent future storage issues.

## Best Practices

* Regularly review large files.
* Empty the OneDrive Recycle Bin periodically.
* Avoid storing unnecessary backups in OneDrive.
* Move large archive files to long-term storage.
* Monitor storage usage monthly.

---

# 12. Document the Resolution

## Example Ticket Notes

```text
User reported that OneDrive was no longer uploading files and displayed a storage quota warning.

Verified that the user's OneDrive storage allocation was fully utilized. Reviewed storage usage and identified several large video files and archived ZIP files consuming significant space. Emptied the OneDrive Recycle Bin and removed unnecessary files after user approval.

Verified available storage increased and confirmed OneDrive synchronization resumed successfully. Uploaded a test file and verified successful synchronization.

Issue resolved.
```

---

# Final Resolution

The user's OneDrive storage quota had been exceeded, preventing synchronization and file uploads. Storage was reclaimed by removing unnecessary files and clearing the OneDrive Recycle Bin. Synchronization functionality was restored and verified.

---

# Skills Demonstrated

* Microsoft 365 Administration
* OneDrive for Business Support
* Storage Management
* End User Support
* File Analysis
* Synchronization Troubleshooting
* Customer Communication
* Help Desk Documentation
* Root Cause Analysis

