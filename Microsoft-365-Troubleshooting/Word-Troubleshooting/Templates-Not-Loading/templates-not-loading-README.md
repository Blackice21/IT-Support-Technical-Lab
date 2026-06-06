# Microsoft Word – Templates Not Loading

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "My company template isn't showing up."
>
> "Word opens a blank document instead of the template."
>
> "I can't access the shared templates."
>
> "The template used to load automatically but no longer does."

---

# Objective

Determine why Microsoft Word templates are not loading correctly and restore access to the required templates.

Common causes include:

* Missing template files
* Incorrect template paths
* Network connectivity issues
* Corrupted templates
* Permission problems
* Add-in conflicts
* Damaged Normal.dotm template
* Office configuration issues

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What template is missing?

2. Does the issue affect:

   * One template
   * Multiple templates
   * All templates

3. Is the template stored:

   * Locally
   * On a network share
   * In SharePoint
   * In OneDrive

4. When did the issue begin?

5. Has the computer recently been changed or replaced?

6. Are other users experiencing the same issue?

### Determine Scope

Ask:

> "Can other users access the same template successfully?"

This helps determine if the issue is:

* User-specific
* Template-specific
* Network-related
* Organization-wide

---

# Step 1: Verify the Template Exists

### Locate Template File

Determine where the template is stored.

Common file types:

* .dotx
* .dotm

### Verify

Confirm the file exists in the expected location.

### Results

#### Template Found

Continue troubleshooting.

#### Template Missing

Restore the template from backup or source location.

---

# Step 2: Verify Template Path Configuration

Word must know where to locate templates.

### Check Template Locations

1. Open Word.
2. Navigate to:

File → Options → Advanced

3. Scroll to:

General

4. Select:

File Locations

### Verify

Review:

* User Templates
* Workgroup Templates

### Results

#### Path Correct

Continue troubleshooting.

#### Path Incorrect

Update the template path.

---

# Step 3: Verify Access Permissions

The user must have permission to access the template location.

### Test Access

1. Browse to the template folder.
2. Attempt to open the template file.

### Results

#### Access Successful

Continue troubleshooting.

#### Access Denied

Correct permissions and retest.

---

# Step 4: Verify Network Connectivity

If templates are stored on a network location:

### Test Access

1. Open File Explorer.
2. Navigate to the shared location.

### Verify

* Share is accessible
* Network drive is connected
* File opens successfully

### Results

#### Network Available

Continue troubleshooting.

#### Network Unavailable

Resolve connectivity issues.

---

# Step 5: Test Template Manually

Determine whether the template itself is functional.

### Open Template Directly

1. Locate the template file.
2. Double-click the file.

### Results

#### Template Opens

Template is likely functional.

#### Template Fails

Template may be corrupted.

---

# Step 6: Verify Shared Template Location

For organization-wide templates:

### Review Workgroup Templates

1. Open:

File → Options → Advanced → File Locations

2. Verify:

Workgroup Templates

points to the correct location.

### Results

#### Correct Location

Continue troubleshooting.

#### Incorrect Location

Update the path.

---

# Step 7: Check Startup Folder Templates

Some templates load automatically during Word startup.

### Verify Startup Folder

Navigate to:

```text
%appdata%\Microsoft\Word\Startup
```

### Check

Confirm required template files exist.

### Results

#### Template Present

Continue troubleshooting.

#### Template Missing

Restore the template.

---

# Step 8: Launch Word in Safe Mode

Safe Mode disables add-ins and customizations.

### Open Safe Mode

Press:

Windows + R

Enter:

```text
winword /safe
```

### Test Template

Attempt to load the template.

### Results

#### Template Loads

An add-in conflict may exist.

#### Template Fails

Continue troubleshooting.

---

# Step 9: Check Add-ins

Add-ins can interfere with template loading.

### Open Add-ins

1. Navigate to:

File → Options → Add-ins

2. Review installed add-ins.

### Test

Disable nonessential add-ins temporarily.

### Results

#### Template Loads

Identify conflicting add-in.

#### Template Still Fails

Continue troubleshooting.

---

# Step 10: Rebuild Normal.dotm

A corrupted Normal template can affect template loading.

### Close Word

Navigate to:

```text
%appdata%\Microsoft\Templates
```

Locate:

```text
Normal.dotm
```

Rename to:

```text
Normal.old
```

### Restart Word

A new Normal.dotm file will be created automatically.

### Results

#### Template Loads

Issue resolved.

#### Template Still Fails

Continue troubleshooting.

---

# Step 11: Test Another User Profile

Determine whether the issue follows the user profile.

### Test

1. Sign into Windows using another account.
2. Open Word.
3. Attempt to access the template.

### Results

#### Template Loads

Issue is user-profile specific.

#### Template Fails

Issue is system-wide.

---

# Step 12: Verify OneDrive or SharePoint Sync

If templates are stored in cloud locations:

### Check Sync Status

Verify:

* OneDrive is syncing properly
* SharePoint libraries are accessible
* No sync errors exist

### Results

#### Sync Healthy

Continue troubleshooting.

#### Sync Errors Found

Resolve synchronization issues.

---

# Step 13: Repair Microsoft Office

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

Retest template loading.

---

# Step 14: Recreate Template Configuration

If settings appear corrupted:

### Reconfigure

1. Remove template paths.
2. Restart Word.
3. Re-add template paths.

### Test

Verify templates load correctly.

---

# Step 15: Reinstall Microsoft Office

If all previous steps fail:

### Remove Office

1. Open:

Settings → Apps

2. Uninstall Microsoft 365.

### Restart Computer

### Reinstall Office

Install the latest version.

### Test Again

Verify templates load properly.

---

# Quick Troubleshooting Flow

1. Verify template exists.
2. Verify template paths.
3. Check permissions.
4. Verify network access.
5. Open template manually.
6. Verify Workgroup Template location.
7. Check Startup folder.
8. Test Word Safe Mode.
9. Disable add-ins.
10. Rebuild Normal.dotm.
11. Test another user profile.
12. Verify OneDrive/SharePoint sync.
13. Repair Office.
14. Reconfigure template settings.
15. Reinstall Office.

---

# Expected Outcome

By following this process, a help desk technician can identify whether Word template loading issues are caused by:

* Missing template files
* Incorrect template paths
* Permission issues
* Network connectivity problems
* Add-in conflicts
* Corrupted Normal.dotm files
* OneDrive or SharePoint sync issues
* Office installation problems

and restore access to the required templates for the user.

