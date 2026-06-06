# Outlook Crashing / Corrupted Profile - Troubleshooting Guide

## Overview

This guide documents the troubleshooting process for resolving issues where Microsoft Outlook crashes during startup, freezes unexpectedly, fails to load mailboxes, or exhibits behavior consistent with a corrupted Outlook profile.

---

# Ticket Information

### User Report

> Outlook crashes every time I open it.

or

> Outlook opens but freezes on "Loading Profile."

or

> Outlook keeps crashing throughout the day and becomes unresponsive.

---

# Step 1 - Gather Information from the User

Before making changes, collect information to determine the scope and potential cause of the issue.

### Questions to Ask

#### Issue Details

* When did the issue begin?
* Does Outlook crash immediately or after opening?
* Does Outlook display an error message?
* Is Outlook freezing at "Loading Profile"?
* Does Outlook eventually open after waiting?

#### Recent Changes

* Has Outlook recently been updated?
* Were any Office updates installed?
* Has a new mailbox been added recently?
* Have any Outlook add-ins been installed?

#### Scope of Impact

* Is only Outlook affected?
* Are other Office applications working?
* Can the user access email through Outlook Web Access (OWA)?

#### Device Information

* Windows version
* Outlook version
* Company-managed device or personal device

---

# Information Gathered

### Example Findings

| Question                   | Response                          |
| -------------------------- | --------------------------------- |
| When did issue start?      | Today                             |
| Any recent changes?        | Office update installed yesterday |
| Can access Outlook Web?    | Yes                               |
| Outlook error?             | Crashes during startup            |
| Other Office apps working? | Yes                               |

### Initial Assessment

Because:

* Outlook Web works
* Exchange Online is accessible
* Only Outlook Desktop is affected

The issue is likely related to the local Outlook installation, add-ins, or user profile.

---

# Step 2 - Verify Microsoft 365 Service Status

Sign into Microsoft 365 Admin Center.

Navigate to:

```text
Health → Service Health
```

Verify:

* Exchange Online is operational.
* No active Microsoft service incidents exist.

---

# Step 3 - Test Outlook Web Access

Ask the user to sign into:

```text
https://outlook.office.com
```

Verify:

* Mailbox loads successfully.
* Email can be sent and received.

### Result

If Outlook Web works normally, focus troubleshooting on the workstation.

---

# Step 4 - Launch Outlook in Safe Mode

Safe Mode disables Outlook add-ins.

Press:

```text
Windows + R
```

Run:

```text
outlook.exe /safe
```

### Evaluate Results

#### Outlook Opens Successfully

Possible causes:

* Faulty add-in
* Corrupted extension
* Third-party integration

Proceed to Step 5.

#### Outlook Still Crashes

Possible causes:

* Corrupted Outlook profile
* Damaged Office installation
* Corrupted OST file

Proceed to Step 6.

---

# Step 5 - Disable Outlook Add-ins

Within Outlook:

```text
File → Options → Add-ins
```

At the bottom:

```text
Manage COM Add-ins → Go
```

Disable all add-ins.

Restart Outlook normally.

### Verify

* Outlook launches successfully.
* No crashes occur.
* User can access mailbox.

If Outlook remains stable, re-enable add-ins one at a time to identify the problematic extension.

---

# Step 6 - Create a New Outlook Profile

A corrupted Outlook profile is one of the most common causes of Outlook crashes.

Open:

```text
Control Panel → Mail
```

Select:

```text
Show Profiles
```

Choose:

```text
Add
```

Create a new profile.

Example:

```text
Outlook-New
```

Configure the user's mailbox.

Select:

```text
Always use this profile
```

Choose the newly created profile.

Launch Outlook.

---

# Step 7 - Rebuild Outlook Data File (OST)

If the issue persists:

Close Outlook.

Navigate to:

```text
C:\Users\%username%\AppData\Local\Microsoft\Outlook
```

Locate the OST file.

Rename:

```text
mailbox.ost
```

to:

```text
mailbox.old
```

Reopen Outlook.

A new OST file will be created automatically.

---

# Step 8 - Repair Microsoft Office

Open:

```text
Settings → Apps → Installed Apps
```

Locate:

```text
Microsoft 365 Apps
```

Select:

```text
Modify
```

Choose:

### Quick Repair

If unsuccessful:

### Online Repair

Allow the repair process to complete.

Restart the computer.

Test Outlook again.

---

# Step 9 - Verify Resolution

Confirm:

* Outlook opens normally.
* No crashes occur.
* Mailbox synchronizes successfully.
* User can send and receive email.
* Outlook remains stable after multiple launches.

---

# Root Cause

The issue was caused by a corrupted Outlook profile.

The profile contained damaged configuration settings that prevented Outlook from loading mailbox data correctly. Outlook crashed during startup while attempting to load the profile.

---

# Resolution

The issue was resolved by:

1. Creating a new Outlook profile.
2. Reconfiguring the user's mailbox.
3. Rebuilding Outlook data files.

After creating a new profile, Outlook launched successfully and mailbox functionality was restored.

---

# Skills Demonstrated

* User Interviewing and Ticket Intake
* Microsoft 365 Administration
* Exchange Online Support
* Outlook Profile Management
* OST File Rebuild Procedures
* Office Application Repair
* Add-in Troubleshooting
* Root Cause Analysis
* Help Desk Documentation

---
