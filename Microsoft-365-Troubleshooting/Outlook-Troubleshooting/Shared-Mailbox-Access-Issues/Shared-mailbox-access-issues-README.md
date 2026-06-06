# Shared Mailbox Access Issues - Troubleshooting Guide

## Overview

This guide documents the troubleshooting process for resolving issues where a user cannot access a shared mailbox in Microsoft Outlook or Outlook Web Access (OWA).

Common symptoms include:

* Shared mailbox missing from Outlook
* User receives "Cannot expand folder" errors
* User cannot open the shared mailbox
* User can see the mailbox but cannot send emails from it
* Access was recently granted but the mailbox has not appeared

---

# Ticket Information

### User Report

> I was granted access to a shared mailbox, but I can't see it in Outlook.

or

> The shared mailbox disappeared from Outlook.

or

> I can see the mailbox, but I can't open it.

or

> I can read emails but cannot send messages from the shared mailbox.

---

# Step 1 - Gather Information from the User

Before making changes, collect information about the issue.

### Questions to Ask

#### Mailbox Information

* What is the name of the shared mailbox?
* When did the issue begin?
* Has access worked previously?

#### Scope of Impact

* Are other users able to access the shared mailbox?
* Is the issue affecting one user or multiple users?
* Does the mailbox appear in Outlook Web Access?

#### Recent Changes

* Was access recently granted?
* Was the user recently added to a security group?
* Has the mailbox been renamed?

#### Error Messages

* Are any error messages displayed?
* Does Outlook display:

  * Cannot expand folder?
  * Cannot open mailbox?
  * Access denied?

---

# Information Gathered

### Example Findings

| Question                    | Response          |
| --------------------------- | ----------------- |
| Mailbox name                | HR Shared Mailbox |
| Access worked previously?   | No                |
| Recently granted access?    | Yes               |
| Other users can access?     | Yes               |
| Mailbox appears in Outlook? | No                |

### Initial Assessment

Because:

* Other users have access
* Shared mailbox is functioning
* User was recently granted permissions

The issue likely involves mailbox permissions, Outlook synchronization, or Auto-Mapping delays.

---

# Step 2 - Verify Shared Mailbox Exists

Sign into Exchange Admin Center.

Navigate to:

```text
Recipients → Mailboxes → Shared
```

Verify:

* Shared mailbox exists.
* Mailbox is not hidden or deleted.
* Mailbox is healthy.

---

# Step 3 - Verify User Permissions

Open the shared mailbox.

Select:

```text
Mailbox Delegation
```

Verify the user has appropriate permissions.

### Common Permission Types

#### Full Access

Allows user to:

* Open mailbox
* Read emails
* Manage folders

#### Send As

Allows user to:

* Send emails appearing as the shared mailbox

#### Send on Behalf

Allows user to:

* Send emails on behalf of the shared mailbox

Example:

```text
John Smith on behalf of HR Shared Mailbox
```

---

# Step 4 - Confirm Permission Replication

If permissions were recently assigned:

Verify:

```text
User added recently?
```

Exchange Online permission changes may require time to synchronize.

### Typical Delay

```text
15 minutes to several hours
```

depending on Microsoft 365 replication.

---

# Step 5 - Verify Outlook Web Access

Ask the user to sign into:

```text
https://outlook.office.com
```

Open the shared mailbox manually.

### Procedure

Right-click:

```text
Folders
```

Select:

```text
Add shared folder or mailbox
```

Enter the mailbox name.

### Results

#### Mailbox Opens Successfully

The issue is likely Outlook Desktop related.

#### Mailbox Does Not Open

Verify permissions again.

---

# Step 6 - Check Auto-Mapping

When Full Access permissions are assigned, Exchange may automatically add the mailbox to Outlook.

Verify whether:

* Mailbox appears in Outlook navigation pane.
* Mailbox appears after restarting Outlook.

### If Not Visible

Close Outlook completely.

Restart Outlook.

Allow several minutes for synchronization.

---

# Step 7 - Add Shared Mailbox Manually

If Auto-Mapping fails:

Open Outlook.

Navigate to:

```text
File → Account Settings → Account Settings
```

Select:

```text
Change → More Settings → Advanced
```

Choose:

```text
Add
```

Enter the shared mailbox name.

Restart Outlook.

Verify mailbox appears.

---

# Step 8 - Verify Cached Exchange Mode

Open:

```text
File → Account Settings
```

Verify:

```text
Use Cached Exchange Mode
```

is enabled.

Restart Outlook if changes are made.

---

# Step 9 - Create a New Outlook Profile

If permissions are correct but mailbox still does not appear:

Open:

```text
Control Panel → Mail
```

Select:

```text
Show Profiles
```

Create a new Outlook profile.

Configure the user's mailbox.

Launch Outlook and verify shared mailbox access.

---

# Step 10 - Test Send As Permissions

If the user can access the mailbox but cannot send email:

Create a new email.

Select:

```text
Options → From
```

Choose the shared mailbox address.

Send a test message.

### Possible Error

```text
You do not have permission to send as this user.
```

If displayed:

Verify:

```text
Send As
```

permission is assigned.

---

# Step 11 - Verify Resolution

Confirm:

* Shared mailbox appears in Outlook.
* User can open folders.
* User can read email.
* User can send email if required.
* No access errors occur.

---

# Root Cause

The issue was caused by missing Full Access permissions.

Although the mailbox existed and functioned normally, the user had not been granted the appropriate Exchange Online mailbox permissions.

As a result, Outlook could not display or access the shared mailbox.

---

# Resolution

The issue was resolved by:

1. Assigning Full Access permissions.
2. Restarting Outlook.
3. Allowing Exchange Online synchronization to complete.
4. Verifying mailbox visibility and access.

After permissions replicated successfully, the shared mailbox appeared automatically in Outlook.

---

# Skills Demonstrated

* User Interviewing and Ticket Intake
* Microsoft 365 Administration
* Exchange Online Administration
* Shared Mailbox Management
* Permission Troubleshooting
* Outlook Desktop Support
* Outlook Web Access Troubleshooting
* Root Cause Analysis
* Help Desk Documentation

---
