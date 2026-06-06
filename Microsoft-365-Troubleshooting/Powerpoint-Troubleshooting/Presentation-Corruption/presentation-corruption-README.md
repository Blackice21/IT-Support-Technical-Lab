
# Microsoft PowerPoint – Presentation Corruption

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "My PowerPoint presentation won't open."
>
> "PowerPoint says the file is corrupted."
>
> "The presentation opens but some slides are missing."
>
> "PowerPoint crashes when I open the file."

---

# Objective

Determine why a PowerPoint presentation has become corrupted and recover the presentation or its contents whenever possible.

Common causes include:

* Unexpected system shutdowns
* Incomplete file saves
* Storage device failures
* Network interruptions during save operations
* PowerPoint crashes
* Corrupted embedded objects
* File transfer issues
* Presentation file damage

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What happens when opening the presentation?

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

   * One presentation
   * Multiple presentations

### Determine Scope

Ask:

> "Can other PowerPoint files be opened successfully?"

This helps determine if the issue is:

* File-specific
* Application-specific
* Storage-related

---

# Step 1: Create a Backup Copy

Before making any changes:

### Create Backup

1. Locate the presentation file.
2. Copy the file.
3. Save the copy to a separate location.

### Verify

Perform all recovery attempts using the copy.

---

# Step 2: Attempt Normal Opening

### Open Presentation

1. Launch PowerPoint.
2. Open the file normally.

### Results

#### File Opens Successfully

Save a new copy immediately.

#### File Fails To Open

Continue troubleshooting.

---

# Step 3: Use Open and Repair

PowerPoint includes a built-in repair feature.

### Open and Repair

1. Open PowerPoint.
2. Select:

File → Open → Browse

3. Select the presentation.
4. Click the arrow next to:

Open

5. Select:

Open and Repair

### Results

#### Repair Successful

Save the recovered file with a new name.

#### Repair Fails

Continue troubleshooting.

---

# Step 4: Open PowerPoint in Safe Mode

Determine whether add-ins are causing the issue.

### Launch Safe Mode

Press:

Windows + R

Enter:

```text
powerpnt /safe
```

### Open Presentation

Attempt to open the file.

### Results

#### Presentation Opens

Investigate PowerPoint add-ins.

#### Presentation Fails

Continue troubleshooting.

---

# Step 5: Open on Another Computer

Determine whether the issue follows the file or the device.

### Test

1. Copy presentation to another computer.
2. Open the file.

### Results

#### Presentation Opens

Issue is likely local to the original system.

#### Presentation Fails

File corruption is likely.

---

# Step 6: Open from PowerPoint Recovery

PowerPoint may have saved recovery versions.

### Check Recovery Files

1. Open PowerPoint.
2. Review:

Document Recovery

pane if available.

### Results

#### Recovery Version Found

Save the recovered version immediately.

#### No Recovery Version

Continue troubleshooting.

---

# Step 7: Restore Previous Version

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

# Step 8: Attempt to Extract Slides

If the file partially opens:

### Create New Presentation

1. Open PowerPoint.
2. Create a blank presentation.

### Reuse Slides

1. Select:

Home → New Slide → Reuse Slides

2. Browse to the damaged presentation.

### Results

#### Slides Imported

Save the new presentation.

#### Import Fails

Continue troubleshooting.

---

# Step 9: Check Embedded Media and Objects

Corrupted media files can damage presentations.

### Review Content

Look for:

* Videos
* Audio files
* Linked objects
* Embedded spreadsheets

### Test

Remove problematic content if identified.

---

# Step 10: Save Presentation Under a New Name

If the file opens partially:

### Save As

1. Open the presentation.
2. Select:

File → Save As

3. Save using a different name.

### Test

Close and reopen the new file.

---

# Step 11: Repair Microsoft Office

Corrupted Office components can contribute to file issues.

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

Retest presentation.

---

# Step 12: Verify Storage Location

File corruption can result from storage failures.

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

# Step 13: Test Another Presentation

Determine whether the issue is isolated.

### Test

1. Open several PowerPoint presentations.

### Results

#### Other Files Work

Issue is specific to the affected file.

#### Multiple Files Fail

Issue may involve PowerPoint or storage.

---

# Step 14: Export Recoverable Content

If slides can still be viewed:

### Export

Save content as:

* PDF
* Images
* New PowerPoint file

### Verify

Preserve as much content as possible.

---

# Step 15: Reinstall Microsoft Office

If PowerPoint continues to experience corruption-related issues:

### Remove Office

1. Open:

Settings → Apps

2. Uninstall Microsoft 365.

### Restart Computer

### Reinstall Office

Install the latest version.

### Test Again

Attempt to open the presentation.

---

# Quick Troubleshooting Flow

1. Create backup copy.
2. Attempt normal opening.
3. Use Open and Repair.
4. Test Safe Mode.
5. Open on another computer.
6. Check Document Recovery.
7. Restore previous version.
8. Reuse slides.
9. Check embedded objects.
10. Save under a new name.
11. Repair Office.
12. Verify storage health.
13. Test other presentations.
14. Export recoverable content.
15. Reinstall Office.

---

# Expected Outcome

By following this process, a help desk technician can identify whether presentation corruption is caused by:

* Damaged PowerPoint files
* Storage failures
* Interrupted save operations
* Corrupted embedded content
* OneDrive or SharePoint sync issues
* Office installation problems
* Hardware or file system issues

and recover the presentation or restore access to its contents whenever possible.
