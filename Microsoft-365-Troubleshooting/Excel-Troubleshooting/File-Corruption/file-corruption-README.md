# Microsoft Excel – File Corruption

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "My Excel file won't open."
>
> "Excel says the workbook is corrupted."
>
> "The spreadsheet opens but data is missing."
>
> "Excel crashes when I try to open the file."

---

# Objective

Determine why an Excel workbook has become corrupted and recover the file or its contents whenever possible.

Common causes include:

* Unexpected system shutdowns
* Incomplete file saves
* Storage device failures
* Network interruptions during save operations
* Excel crashes
* Corrupted formulas or objects
* OneDrive synchronization issues
* Workbook file damage

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What happens when opening the workbook?

2. Is an error message displayed?

3. When was the file last working?

4. Where is the file stored?

   * Local computer
   * OneDrive
   * SharePoint
   * Network drive
   * USB drive

5. Has the file recently been moved or copied?

6. Does the issue affect:

   * One workbook
   * Multiple workbooks

### Determine Scope

Ask:

> "Can other Excel files be opened successfully?"

This helps determine if the issue is:

* File-specific
* Application-specific
* Storage-related

---

# Step 1: Create a Backup Copy

Before making any changes:

### Create Backup

1. Locate the workbook.
2. Copy the file.
3. Save the copy to a separate location.

### Verify

Perform all recovery attempts using the copy.

---

# Step 2: Attempt Normal Opening

### Open Workbook

1. Launch Microsoft Excel.
2. Open the workbook normally.

### Results

#### Workbook Opens Successfully

Save a new copy immediately.

#### Workbook Fails To Open

Continue troubleshooting.

---

# Step 3: Use Open and Repair

Excel includes a built-in repair feature.

### Open and Repair

1. Open Excel.
2. Select:

File → Open → Browse

3. Locate the workbook.
4. Click the arrow next to:

Open

5. Select:

Open and Repair

### Results

#### Repair Successful

Save the recovered workbook with a new name.

#### Repair Fails

Continue troubleshooting.

---

# Step 4: Open Excel in Safe Mode

Determine whether add-ins are causing the issue.

### Launch Safe Mode

Press:

Windows + R

Enter:

```text
excel /safe
```

### Open Workbook

Attempt to open the file.

### Results

#### Workbook Opens

Investigate Excel add-ins.

#### Workbook Fails

Continue troubleshooting.

---

# Step 5: Open on Another Computer

Determine whether the issue follows the file or the device.

### Test

1. Copy the workbook to another computer.
2. Open the file.

### Results

#### Workbook Opens

Issue is likely local to the original system.

#### Workbook Fails

File corruption is likely.

---

# Step 6: Restore Previous Version

If stored in OneDrive or SharePoint:

### Restore Version

1. Locate the file.
2. Right-click.
3. Select:

Version History

4. Review available versions.

### Results

#### Older Version Available

Restore the last known working version.

#### No Previous Versions

Continue troubleshooting.

---

# Step 7: Check AutoRecover Files

Excel may have saved recovery versions.

### Locate Recovery Files

1. Open Excel.
2. Select:

File → Info → Manage Workbook

3. Review available recovered files.

### Results

#### Recovery File Found

Open and save immediately.

#### No Recovery File Found

Continue troubleshooting.

---

# Step 8: Disable External Links and Connections

Corrupted links can prevent workbooks from opening correctly.

### Open Workbook Carefully

If the workbook partially opens:

1. Navigate to:

Data → Queries & Connections

2. Review:

   * External links
   * Data connections
   * Power Query connections

### Results

#### Problem Connection Found

Remove or repair the connection.

#### No Issues Found

Continue troubleshooting.

---

# Step 9: Check for Corrupted Worksheets

A specific worksheet may be damaged.

### Test

1. Create a new workbook.
2. Attempt to copy sheets individually from the damaged workbook.

### Results

#### Most Sheets Copy Successfully

Identify and isolate damaged sheets.

#### Copy Fails

Continue troubleshooting.

---

# Step 10: Save Workbook Under a New Name

If the workbook opens partially:

### Save As

1. Select:

File → Save As

2. Save using a different name.

### Test

Close and reopen the new file.

---

# Step 11: Save in Another Format

Attempt to recover data using another file format.

### Save As

Choose:

* .xlsx
* .xls
* .csv (for data recovery)

### Results

#### Data Preserved

Continue working from recovered file.

#### Save Fails

Continue troubleshooting.

---

# Step 12: Repair Microsoft Office

Corrupted Office components can contribute to workbook issues.

### Open Installed Apps

1. Open:

Settings → Apps

2. Locate:

Microsoft 365

or

Microsoft Office

3. Select:

Modify

### Run Repair

Choose:

Quick Repair

If necessary:

Online Repair

### Restart Computer

Retest workbook.

---

# Step 13: Verify Storage Location

Storage failures can cause file corruption.

### Check Storage

Verify:

* Local disk health
* USB drive accessibility
* Network drive connectivity
* OneDrive synchronization status

### Results

#### Storage Healthy

Continue troubleshooting.

#### Storage Issues Found

Resolve storage problems first.

---

# Step 14: Test Other Excel Files

Determine whether the issue is isolated.

### Test

1. Open several Excel workbooks.

### Results

#### Other Files Work

Issue is specific to the affected workbook.

#### Multiple Files Fail

Issue may involve Excel or storage.

---

# Step 15: Export Recoverable Data

If workbook contents remain accessible:

### Export

Copy important information into:

* New workbook
* CSV files
* Separate worksheets

### Verify

Preserve as much data as possible.

---

# Step 16: Reinstall Microsoft Office

If Excel continues experiencing corruption-related issues:

### Remove Office

1. Open:

Settings → Apps

2. Uninstall Microsoft 365.

### Restart Computer

### Reinstall Office

Install the latest version.

### Test Again

Attempt to open the workbook.

---

# Quick Troubleshooting Flow

1. Create backup copy.
2. Attempt normal opening.
3. Use Open and Repair.
4. Test Safe Mode.
5. Open on another computer.
6. Restore previous version.
7. Check AutoRecover files.
8. Review external links.
9. Isolate damaged worksheets.
10. Save under a new name.
11. Save in another format.
12. Repair Office.
13. Verify storage health.
14. Test other workbooks.
15. Export recoverable data.
16. Reinstall Office.

---

# Expected Outcome

By following this process, a help desk technician can identify whether Excel file corruption is caused by:

* Damaged workbook files
* Interrupted save operations
* Storage failures
* Corrupted worksheets
* External data connection issues
* OneDrive or SharePoint sync problems
* Office installation issues
* Hardware or file system problems

and recover the workbook or restore access to its contents whenever possible.

