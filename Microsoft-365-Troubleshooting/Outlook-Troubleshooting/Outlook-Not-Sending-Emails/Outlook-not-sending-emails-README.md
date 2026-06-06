# Outlook Not Sending Emails - Troubleshooting Guide

## Overview

This guide documents the troubleshooting process for resolving issues where a user can receive email in Microsoft Outlook but cannot send messages.

---

# Ticket Information

### User Report

> I can receive emails, but none of my emails are sending.

or

> My emails are stuck in the Outbox.

or

> Outlook gives me an error whenever I try to send a message.

---

# Step 1 - Gather Information from the User

Before making any changes, gather information about the issue.

### Questions to Ask

#### Issue Details

* When did the problem begin?
* Are all emails failing to send?
* Does the issue occur with every recipient?
* Are there any error messages displayed?

#### Message Details

* Is the email large?
* Does it contain attachments?
* Are attachments larger than 25 MB?
* Is the email stuck in the Outbox?

#### Scope of Impact

* Can the user receive emails?
* Does Outlook Web Access (OWA) work?
* Are other users experiencing the same issue?

#### Recent Changes

* Password recently changed?
* New mailbox added?
* Outlook profile recently modified?
* New Outlook add-ins installed?

---

# Information Gathered

### Example Findings

| Question              | Response         |
| --------------------- | ---------------- |
| Can receive email?    | Yes              |
| Can send email?       | No               |
| Outlook Web works?    | Yes              |
| Error displayed?      | No               |
| Attachments included? | Yes (40 MB file) |

### Initial Assessment

Because:

* Incoming mail works
* Outlook Web works
* Issue only affects Outlook Desktop

The problem is likely local to the workstation or Outlook client.

---

# Step 2 - Verify Microsoft 365 Service Health

Sign into Microsoft 365 Admin Center.

Navigate to:

```text
Health → Service Health
```

Verify:

* Exchange Online is operational.
* No active Microsoft incidents exist.

---

# Step 3 - Determine Whether the Problem Is Outlook or Exchange

Have the user sign into:

```text
https://outlook.office.com
```

Send a test email.

### Results

#### Email Sends Successfully

This indicates:

* Mailbox is healthy.
* Exchange Online is functioning.
* Issue is likely within Outlook Desktop.

#### Email Fails in Outlook Web

Investigate:

* Mailbox restrictions
* Exchange Online issues
* Sending limits
* Account permissions

---

# Step 4 - Check the Outbox

In Outlook:

```text
Send/Receive → Outbox
```

Verify whether messages are stuck.

### Common Indicators

* Messages remain in Outbox indefinitely.
* Send/Receive errors appear.
* Outlook displays synchronization errors.

---

# Step 5 - Verify Outlook Is Online

Look at the Outlook status bar.

Possible statuses:

```text
Connected
```

```text
Disconnected
```

```text
Trying to Connect...
```

```text
Working Offline
```

If Outlook is offline:

```text
Send/Receive → Work Offline
```

Disable Work Offline mode.

---

# Step 6 - Test with a New Email

Create a simple test message:

```text
To: your test account
Subject: Outlook Test
Body: Testing email functionality.
```

Do not include:

* Attachments
* Images
* Signatures

Attempt to send.

### Results

#### Email Sends

The issue may involve:

* Large attachments
* Corrupted message
* Malformed signature

#### Email Fails

Continue troubleshooting.

---

# Step 7 - Check Attachment Size

Exchange Online typically limits message sizes.

Verify whether the email contains:

* Large PDF files
* ZIP archives
* Multiple attachments

### Test

Remove attachments and resend.

If the message sends successfully, attachment size was likely the cause.

---

# Step 8 - Launch Outlook in Safe Mode

Press:

```text
Windows + R
```

Run:

```text
outlook.exe /safe
```

Attempt to send a test message.

### Results

#### Email Sends Successfully

Possible cause:

* Faulty Outlook add-in
* Third-party email integration

Proceed to disable add-ins.

---

# Step 9 - Disable Outlook Add-ins

Navigate to:

```text
File → Options → Add-ins
```

Select:

```text
Manage COM Add-ins → Go
```

Disable all add-ins.

Restart Outlook.

Retest email sending.

---

# Step 10 - Create a New Outlook Profile

If the issue persists:

Open:

```text
Control Panel → Mail
```

Select:

```text
Show Profiles
```

Create a new profile.

Configure the user's mailbox.

Launch Outlook using the new profile.

Retest email sending.

---

# Step 11 - Verify Mailbox Storage

In Microsoft 365 Admin Center:

```text
Users → Active Users → Select User
```

Verify mailbox storage usage.

Potential issues:

* Mailbox quota exceeded
* Send restrictions applied

---

# Step 12 - Run a Message Trace

If Outlook and OWA both fail:

Navigate to:

```text
Exchange Admin Center
→ Mail Flow
→ Message Trace
```

Search for:

* Sender address
* Recipient address
* Date and time

Determine whether Exchange attempted delivery.

---

# Step 13 - Verify Resolution

Confirm:

* Test emails send successfully.
* Messages leave Outbox.
* Recipients receive messages.
* No send errors appear.

---

# Root Cause

The issue was caused by Outlook operating in Offline Mode.

While the user could view previously synchronized emails, Outlook was unable to establish a connection to Exchange Online for outgoing mail.

---

# Resolution

The issue was resolved by:

1. Disabling Work Offline mode.
2. Reconnecting Outlook to Exchange Online.
3. Performing a successful Send/Receive cycle.
4. Verifying delivery through a test message.

After reconnection, messages immediately left the Outbox and were delivered successfully.

---

# Skills Demonstrated

* User Interviewing and Ticket Intake
* Microsoft 365 Administration
* Outlook Desktop Support
* Exchange Online Troubleshooting
* Message Trace Analysis
* Mail Flow Troubleshooting
* Outlook Profile Management
* Root Cause Analysis
* Help Desk Documentation
