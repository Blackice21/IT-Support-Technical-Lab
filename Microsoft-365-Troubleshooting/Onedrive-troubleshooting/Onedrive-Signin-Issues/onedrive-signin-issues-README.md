# Microsoft 365 Help Desk Ticket: OneDrive Sign-In Issues

## Ticket Summary

**Issue:** User is unable to sign into OneDrive or OneDrive repeatedly prompts for credentials.

**User Complaint:**

> "OneDrive keeps asking me to sign in."
> "I enter my password, but OneDrive won't connect."
> "My files stopped syncing and OneDrive says I need to sign in."

**Service:** Microsoft OneDrive for Business
**Environment:** Microsoft 365 / Windows 10 or Windows 11
**Ticket Type:** Authentication / Sign-In Issue
**Priority:** Medium

---

# 1. Gather Information from the User

Before troubleshooting, collect information about the issue.

## Questions to Ask

* When did the problem begin?
* Are you receiving an error message?
* Did you recently change your password?
* Are you able to sign into Microsoft 365 online?
* Is Multi-Factor Authentication (MFA) enabled?
* Are other Microsoft applications working?
* Is the issue affecting only OneDrive or other Microsoft 365 services as well?
* Have you recently changed computers or profiles?

---

# 2. Verify Internet Connectivity

OneDrive requires internet access for authentication.

## Validation Steps

1. Open a web browser.
2. Visit:

```text
https://www.office.com
```

3. Confirm the website loads successfully.

### Expected Result

The user can access Microsoft 365 services online.

---

# 3. Test Microsoft 365 Account Access

Determine whether the issue is specific to OneDrive or the user's account.

## Validation Steps

1. Open:

```text
https://www.office.com
```

2. Sign in using the user's Microsoft 365 account.

### Expected Result

The user should successfully authenticate.

### If Sign-In Fails

Possible causes:

* Incorrect password
* Locked account
* Disabled account
* MFA failure
* Conditional Access policy

Proceed to account verification steps.

---

# 4. Verify User Account Status in Microsoft 365 Admin Center

Administrative Step

1. Sign into Microsoft 365 Admin Center.
2. Navigate to:

```text
Users > Active Users
```

3. Locate the user account.
4. Verify:

* Account is enabled
* License is assigned
* User is not blocked from sign-in

### Expected Result

The account is active and licensed.

---

# 5. Verify Password Functionality

A recent password change often causes OneDrive authentication failures.

## Validation Steps

1. Ask the user to sign into:

```text
https://portal.office.com
```

2. Verify successful login.

### If Password Is Incorrect

1. Reset the password.
2. Provide temporary credentials if necessary.
3. Have the user sign in again.

### Expected Result

The user can authenticate successfully.

---

# 6. Verify MFA Functionality

If MFA is enabled, verify it is functioning properly.

## Validation Steps

1. Attempt Microsoft 365 login.
2. Confirm MFA prompt appears.
3. Verify approval through Microsoft Authenticator.

### Common MFA Problems

* New phone
* Removed Authenticator app
* Incorrect device registered
* Expired authentication methods

### Resolution

Reset MFA registration if required.

---

# 7. Check OneDrive Account Configuration

Verify the correct account is configured.

## Validation Steps

1. Click the OneDrive cloud icon.
2. Open Settings.
3. Select the Account tab.

### Verify

* Correct email address
* Correct Microsoft 365 tenant
* No duplicate accounts

### Expected Result

The correct work account is configured.

---

# 8. Sign Out and Sign Back Into OneDrive

Refresh the authentication session.

## Steps

1. Click the OneDrive cloud icon.
2. Open Settings.
3. Select Account.
4. Click:

```text
Unlink this PC
```

5. Confirm the action.
6. Close OneDrive.
7. Reopen OneDrive.
8. Sign in again using the user's Microsoft 365 credentials.

### Expected Result

OneDrive reconnects successfully.

---

# 9. Remove Stored Windows Credentials

Corrupted credentials can cause authentication loops.

## Steps

1. Open:

```text
Control Panel
```

2. Select:

```text
Credential Manager
```

3. Open:

```text
Windows Credentials
```

4. Remove Microsoft 365 and OneDrive-related credentials.

Examples:

```text
MicrosoftOffice
OneDrive
ADAL
Office365
```

5. Restart the computer.
6. Sign into OneDrive again.

### Expected Result

Fresh credentials are created and authentication succeeds.

---

# 10. Restart OneDrive

Restart the OneDrive client.

## Steps

1. Click the OneDrive cloud icon.
2. Select:

```text
Quit OneDrive
```

3. Open the Start Menu.
4. Launch OneDrive again.

### Expected Result

OneDrive attempts a new authentication session.

---

# 11. Reset OneDrive

If sign-in issues persist, reset the OneDrive client.

## Steps

Press:

```text
Windows + R
```

Run:

```text
%localappdata%\Microsoft\OneDrive\onedrive.exe /reset
```

Wait several minutes.

If OneDrive does not restart automatically:

```text
%localappdata%\Microsoft\OneDrive\onedrive.exe
```

### Expected Result

OneDrive launches with a clean configuration.

---

# 12. Verify Synchronization

After successful sign-in:

## Validation Steps

1. Create a file:

```text
OneDriveLoginTest.txt
```

2. Save it to the OneDrive folder.
3. Verify it uploads successfully.
4. Confirm the file appears in OneDrive Online.

### Expected Result

Synchronization functions normally.

---

# 13. Document the Resolution

## Example Ticket Notes

```text
User reported that OneDrive repeatedly requested credentials and would not remain signed in.

Verified the Microsoft 365 account was active and licensed. Confirmed successful login through Office.com and validated MFA functionality. Removed stored Microsoft credentials from Credential Manager and unlinked the OneDrive account from the workstation.

Reconfigured OneDrive and signed the user back in successfully. Verified synchronization by creating a test file and confirming upload to OneDrive Online.

Issue resolved.
```

---

# Final Resolution

The OneDrive sign-in issue was caused by invalid cached credentials preventing successful authentication. Credentials were cleared, OneDrive was reconfigured, and synchronization functionality was restored.

---

# Skills Demonstrated

* Microsoft 365 Administration
* OneDrive for Business Support
* Authentication Troubleshooting
* MFA Troubleshooting
* Credential Manager Administration
* End User Support
* Synchronization Verification
* Help Desk Documentation
* Root Cause Analysis

