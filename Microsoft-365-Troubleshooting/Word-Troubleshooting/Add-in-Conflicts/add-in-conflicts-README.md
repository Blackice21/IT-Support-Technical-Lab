
# Microsoft Word – Add-in Conflicts

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "Microsoft Word keeps crashing."
>
> "Word freezes when I open a document."
>
> "Certain features stopped working."
>
> "Word is extremely slow."
>
> "I receive errors when Word starts."

---

# Objective

Determine whether a Microsoft Word add-in is causing application instability, performance issues, startup errors, or feature malfunctions and restore normal functionality.

Common causes include:

* Corrupted add-ins
* Incompatible third-party add-ins
* Outdated add-ins
* Office updates causing compatibility issues
* Conflicting PDF add-ins
* Antivirus integration add-ins
* CRM or document management add-ins
* Startup template conflicts

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What issue is occurring?

   * Word crashes
   * Word freezes
   * Startup errors
   * Missing functionality
   * Performance problems

2. When did the issue begin?

3. Was any new software recently installed?

4. Does the issue occur:

   * In one document
   * In all documents

5. Has Microsoft Office recently been updated?

6. Are other Office applications affected?

### Determine Scope

Ask:

> "Does Word work correctly on another computer or under another user profile?"

This helps determine if the issue is:

* Add-in related
* User-specific
* Device-specific
* Office-related

---

# Step 1: Launch Word in Safe Mode

Safe Mode disables add-ins and customizations.

### Open Safe Mode

Press:

Windows + R

Enter:

```text
winword /safe
```

### Test Word

Open several documents and perform normal tasks.

### Results

#### Word Functions Normally

An add-in is likely causing the issue.

#### Issue Persists

The problem may not be add-in related.

Continue with general Word troubleshooting.

---

# Step 2: Review Installed Add-ins

### Open Add-ins Menu

1. Open Word.
2. Navigate to:

File → Options → Add-ins

### Review Installed Add-ins

Look for:

* PDF add-ins
* CRM add-ins
* Antivirus integrations
* Third-party productivity tools
* Document management software

### Verify

Identify recently installed add-ins.

---

# Step 3: Disable COM Add-ins

### Open COM Add-ins

1. Navigate to:

File → Options → Add-ins

2. At the bottom:

Manage → COM Add-ins

3. Select:

Go

### Disable Add-ins

Uncheck all add-ins.

### Restart Word

Test functionality.

### Results

#### Issue Resolved

An add-in conflict is confirmed.

#### Issue Persists

Continue troubleshooting.

---

# Step 4: Enable Add-ins One at a Time

Identify the problematic add-in.

### Test Process

1. Enable one add-in.
2. Restart Word.
3. Test functionality.

Repeat until the issue returns.

### Results

#### Problem Reappears

The most recently enabled add-in is likely responsible.

#### No Issue Found

Continue troubleshooting.

---

# Step 5: Check Disabled Items

Word automatically disables problematic add-ins.

### Review Disabled Items

1. Navigate to:

File → Options → Add-ins

2. At the bottom:

Manage → Disabled Items

3. Select:

Go

### Verify

Review any disabled add-ins.

### Results

#### Disabled Add-in Found

Investigate compatibility and update status.

#### No Disabled Items

Continue troubleshooting.

---

# Step 6: Verify Add-in Compatibility

Office updates may break older add-ins.

### Check Version Compatibility

Review:

* Add-in version
* Microsoft 365 version
* Vendor compatibility documentation

### Results

#### Incompatible Add-in

Update or remove the add-in.

#### Compatible Add-in

Continue troubleshooting.

---

# Step 7: Test Word With a New Document

Determine whether the issue affects all documents.

### Test

1. Create a new blank document.
2. Perform normal editing tasks.

### Results

#### New Document Works

Issue may involve a specific file.

#### New Document Fails

Continue troubleshooting.

---

# Step 8: Check Startup Templates

Corrupted templates can appear as add-in issues.

### Verify Normal Template

Close Word.

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

Word will create a new template automatically.

### Results

#### Issue Resolved

Template corruption was causing the problem.

#### Issue Persists

Continue troubleshooting.

---

# Step 9: Test Another User Profile

Determine whether the issue follows the user profile.

### Test

1. Sign into Windows using another account.
2. Open Word.
3. Test functionality.

### Results

#### Word Works

Issue is profile-specific.

#### Word Fails

Issue is system-wide.

---

# Step 10: Verify Office Updates

### Check Updates

1. Open Word.
2. Navigate to:

File → Account

3. Select:

Update Options → Update Now

### Restart Word

Retest functionality.

---

# Step 11: Check Event Viewer

Application crashes may generate useful logs.

### Open Event Viewer

1. Press:

Windows + X

2. Select:

Event Viewer

3. Navigate to:

Windows Logs → Application

### Review Errors

Look for:

* WINWORD.EXE
* Office-related errors
* Add-in names

### Results

#### Add-in Identified

Investigate or remove the add-in.

#### No Useful Information

Continue troubleshooting.

---

# Step 12: Disable Antivirus Office Integration

Some security products integrate directly into Word.

### Review Security Software

Check for:

* Email scanning add-ins
* Document protection add-ins
* Office integration modules

### Test

Temporarily disable integration if permitted by policy.

### Results

#### Issue Resolved

Antivirus integration may be responsible.

#### Issue Persists

Continue troubleshooting.

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

Retest Word.

---

# Step 14: Remove Problematic Add-in

If a specific add-in has been identified:

### Remove Add-in

1. Open:

File → Options → Add-ins

2. Disable or uninstall the add-in.

### Restart Word

Verify normal operation.

---

# Step 15: Reinstall Microsoft Office

If issues continue:

### Remove Office

1. Open:

Settings → Apps

2. Uninstall Microsoft 365.

### Restart Computer

### Reinstall Office

Install the latest version.

### Test Again

Verify Word functionality.

---

# Quick Troubleshooting Flow

1. Launch Word in Safe Mode.
2. Review installed add-ins.
3. Disable COM add-ins.
4. Enable add-ins one at a time.
5. Check Disabled Items.
6. Verify add-in compatibility.
7. Test a new document.
8. Rebuild Normal.dotm.
9. Test another user profile.
10. Verify Office updates.
11. Review Event Viewer.
12. Check antivirus integrations.
13. Repair Office.
14. Remove problematic add-ins.
15. Reinstall Office.

---

# Expected Outcome

By following this process, a help desk technician can identify whether Word issues are caused by:

* Corrupted add-ins
* Incompatible third-party extensions
* Office update conflicts
* Startup template corruption
* Antivirus integrations
* User profile issues
* Office installation problems

and restore normal Microsoft Word functionality for the user.
