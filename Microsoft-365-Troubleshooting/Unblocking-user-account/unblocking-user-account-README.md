# Unblocking a User Account in Microsoft 365

## Overview

This guide walks through how to unblock a user account in Microsoft 365 after the user is unable to sign in.

User account lockouts are a common help desk ticket and can happen for several reasons, including:

* Too many failed password attempts
* Temporary Microsoft smart lockout
* Sign-in blocked by an administrator
* Stale credentials stored on a device
* Authentication issues after a password change

---

## Symptoms

Users may report:

* "My account is locked"
* "I can't sign in to Outlook or Teams"
* "My password is correct but it still won't let me in"
* "Microsoft says I've tried too many times"
* Repeated login failures after entering the correct password

---

## Check if Sign-In Is Blocked by Admin

### 1. Sign in to Microsoft 365 Admin Center

Open:

`https://admin.microsoft.com`

Sign in with an administrator account.

---

### 2. Open Active Users

From the left menu:

**Users** → **Active users**

Search for the affected user and open their profile.

---

### 3. Open the Account Tab

Select:

**Account**

Locate:

**Block sign-in**

---

### 4. Unblock the User

If **Block sign-in** is enabled:

* Toggle **Block sign-in** to **Off**
* Select **Save changes**

The user should now be able to attempt sign-in again.

---

## If the User Is Not Showing as Blocked

Sometimes the account is not blocked by admin but is still unable to sign in.

Common causes include:

---

### Microsoft Smart Lockout

Microsoft may temporarily lock authentication after repeated failed login attempts.

This usually **does not appear as blocked** inside the Admin Center.

### Resolution:

* Wait several minutes and retry sign-in
  **or**
* Reset the user's password manually

---

### Reset Password

If the account still cannot sign in:

* Open the user profile
* Select **Reset password**
* Generate a temporary password
* Require password change at next sign-in

Then test sign-in again.

---

### Revoke Active Sessions

If old sessions are interfering:

Inside the user profile:

**Account** → **Sign out of all sessions**

This forces Microsoft 365 apps to reauthenticate.

---

## Post-Resolution Verification

After unblocking, verify the user can successfully access:

* Microsoft 365 portal
* Outlook
* Teams
* OneDrive

Recommended test URL:

`https://portal.office.com`

---

## Example Ticket Notes

```text
User unable to sign in to Microsoft 365 account.

Verified account status in Admin Center.

Confirmed account was not blocked by administrator.

Reviewed possible smart lockout due to repeated failed sign-in attempts.

Reset user password and revoked active sessions.

User successfully signed back into Microsoft 365 portal.

Issue resolved.
```

---

## Notes

Good help desk practice:

* Verify user identity before making account changes
* Check whether the account is truly blocked vs temporarily locked
* Reset password if needed
* Revoke sessions when troubleshooting persistent login issues
* Confirm user can sign in before closing the ticket

