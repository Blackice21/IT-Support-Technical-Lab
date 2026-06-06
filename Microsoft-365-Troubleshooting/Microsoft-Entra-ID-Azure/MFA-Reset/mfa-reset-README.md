# MFA Reset in Microsoft Entra ID - Troubleshooting Guide

## Overview

This guide documents the troubleshooting process for resolving Multi-Factor Authentication (MFA) issues by resetting a user's MFA registration in Microsoft Entra ID.

Common scenarios include:

* User lost or replaced their phone
* Microsoft Authenticator was deleted or reinstalled
* User cannot approve MFA requests
* User is locked out of their account
* User no longer has access to their registered authentication methods
* MFA registration is corrupted or outdated

---

# Ticket Information

### User Report

> I got a new phone and can't sign in.

or

> My Microsoft Authenticator app isn't working.

or

> I am not receiving MFA prompts.

or

> I accidentally deleted Microsoft Authenticator and now I'm locked out.

---

# Step 1 - Gather Information from the User

Before making changes, collect information about the issue.

### Questions to Ask

#### Device Information

* Did you recently get a new phone?
* Was your phone lost, stolen, or replaced?
* Did you reinstall Microsoft Authenticator?

#### Authentication Questions

* Are you receiving MFA prompts?
* Can you receive text messages?
* Do you have access to your old device?
* Have you changed your phone number recently?

#### Scope of Impact

* Can you access any Microsoft 365 services?
* Are you locked out of all Microsoft applications?
* Can you sign in using a backup authentication method?

#### Error Messages

Ask the user to provide:

* Screenshots
* Error codes
* Exact wording of any authentication messages

---

# Information Gathered

### Example Findings

| Question                 | Response |
| ------------------------ | -------- |
| New phone received?      | Yes      |
| Access to old phone?     | No       |
| Authenticator installed? | Yes      |
| Receiving prompts?       | No       |
| Able to sign in?         | No       |

### Initial Assessment

Because:

* User recently changed devices
* No MFA prompts are being received
* User cannot access their account

The MFA registration is likely tied to the previous device and must be reset.

---

# Step 2 - Verify User Identity

Before resetting MFA, verify the user's identity according to company procedures.

Examples include:

* Employee ID verification
* Manager confirmation
* Security questions
* Internal verification process

### Important

Never reset MFA without confirming the user's identity.

---

# Step 3 - Verify User Account Status

Sign into the Microsoft Entra Admin Center.

Navigate to:

```text
Identity → Users → All Users
```

Select the affected user.

Verify:

* Account is enabled
* User is licensed
* No account lockout issues exist

---

# Step 4 - Review Authentication Methods

Navigate to:

```text
Identity → Users → Select User
→ Authentication Methods
```

Review registered methods such as:

* Microsoft Authenticator
* Mobile Phone
* Office Phone
* Email Authentication
* Temporary Access Pass (if configured)

Verify whether outdated devices are present.

---

# Step 5 - Reset MFA Registration

Within the user's account:

Navigate to:

```text
Identity → Users → Select User
→ Authentication Methods
```

Select:

```text
Require re-register multifactor authentication
```

or remove outdated authentication methods.

### Result

The user's existing MFA registration is cleared.

During the next sign-in:

* User must configure MFA again.
* New authentication methods can be registered.

---

# Step 6 - Optional: Issue a Temporary Access Pass

If enabled in your environment:

Navigate to:

```text
Identity → Users → Select User
→ Authentication Methods
→ Add Authentication Method
→ Temporary Access Pass
```

Create a Temporary Access Pass (TAP).

Provide the code to the verified user.

### Benefits

Allows the user to:

* Sign in immediately
* Register a new phone
* Reconfigure Microsoft Authenticator

without needing the old device.

---

# Step 7 - User Re-Registration Process

Direct the user to:

```text
https://mysignins.microsoft.com/security-info
```

or

```text
https://aka.ms/mfasetup
```

The user should:

1. Sign in.
2. Complete MFA registration.
3. Configure Microsoft Authenticator.
4. Verify notifications work correctly.

---

# Step 8 - Test Authentication

Have the user:

1. Sign out.
2. Sign back in.
3. Approve an MFA request.

Verify:

* Authentication succeeds.
* MFA prompts arrive correctly.
* Microsoft 365 applications are accessible.

---

# Step 9 - Verify Resolution

Confirm:

* User can sign in successfully.
* MFA notifications are received.
* Microsoft Authenticator functions correctly.
* Microsoft 365 services are accessible.
* No additional MFA errors occur.

---

# Root Cause

The issue was caused by outdated MFA registration information associated with a previous mobile device.

Because Microsoft Entra ID was attempting to send authentication requests to an unavailable device, the user could not complete MFA verification.

---

# Resolution

The issue was resolved by:

1. Verifying the user's identity.
2. Resetting MFA registration.
3. Removing outdated authentication methods.
4. Re-registering Microsoft Authenticator on the user's new device.

After re-registration, authentication requests were delivered successfully and account access was restored.

---

# Alternative Root Causes

Common causes of MFA reset requests include:

* New mobile phone
* Lost or stolen device
* Microsoft Authenticator removed
* Device factory reset
* Phone number change
* Corrupted MFA registration
* Expired authentication methods
* User enrollment errors
---

# Skills Demonstrated

* User Interviewing and Ticket Intake
* Microsoft Entra ID Administration
* MFA Administration
* Microsoft Authenticator Support
* Identity Verification Procedures
* User Account Recovery
* Authentication Troubleshooting
* Temporary Access Pass Administration
* Root Cause Analysis
* Help Desk Documentation

---

**Difficulty:** Beginner to Intermediate

**Category:** Microsoft Entra ID, Authentication, MFA, Identity Management
