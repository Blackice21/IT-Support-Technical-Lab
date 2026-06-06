# Microsoft Teams – Cannot Sign In
## Help Desk Troubleshooting Guide

### Ticket Example
**User Report:**
> "I can't sign into Microsoft Teams. It keeps asking me to sign in again, gives an error message, or won't load."

---

# Objective

Determine why the user cannot sign into Microsoft Teams and restore access as quickly as possible.

Common causes include:

- Incorrect username or password
- MFA (Multi-Factor Authentication) issues
- Account lockout
- License problems
- Teams service outages
- Corrupted Teams cache
- Conditional Access restrictions
- Network connectivity issues

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. What error message are you receiving?
2. Are you using:
   - Teams Desktop App
   - Teams Web App
   - Mobile App
3. Did Teams work previously?
4. When did the issue start?
5. Have you recently changed your password?
6. Are you able to sign into:
   - Outlook
   - Office.com
   - OneDrive

### Determine Scope

Ask:

> "Are other users experiencing the same issue?"

This helps determine if the issue is:

- User-specific
- Device-specific
- Organization-wide

---

# Step 1: Verify Internet Connectivity

Teams requires access to Microsoft 365 services.

### Test Connectivity

1. Open a browser.
2. Visit:
   - https://www.office.com
   - https://portal.office.com
3. Confirm websites load properly.

### If Internet Is Not Working

Troubleshoot:

- Wi-Fi connection
- Ethernet connection
- VPN connection
- DNS issues

Resolve connectivity problems before continuing.

---

# Step 2: Verify User Credentials

### Test Microsoft 365 Login

1. Open an InPrivate/Incognito browser.
2. Navigate to:
   https://portal.office.com
3. Attempt sign-in.

### Results

#### Login Successful

Credentials are valid.

Proceed to Teams-specific troubleshooting.

#### Login Failed

Possible causes:

- Incorrect password
- Expired password
- Account locked
- Disabled account

Reset password or investigate account status.

---

# Step 3: Check User Account Status

### Microsoft 365 Admin Center

1. Open Microsoft 365 Admin Center.
2. Navigate to:

Users → Active Users

3. Locate the affected user.

Verify:

- Account is active
- Sign-in is not blocked
- User has proper licensing

### If Sign-In Is Blocked

1. Open user account.
2. Select:

Block Sign-In

3. Ensure sign-in is allowed.

---

# Step 4: Verify Teams License Assignment

Users require a valid Teams license.

### Check Licensing

1. Open user account.
2. Select:

Licenses and Apps

3. Verify:

- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5
- Other Teams-enabled license

### If No License Exists

Assign an appropriate license.

Allow several minutes for replication.

---

# Step 5: Check Microsoft Service Health

The issue may be Microsoft-side.

### Check Service Health

1. Open Microsoft 365 Admin Center.
2. Navigate to:

Health → Service Health

3. Look for incidents involving:

- Microsoft Teams
- Azure Active Directory
- Authentication Services

### If Outage Exists

Inform user:

> "Microsoft is currently experiencing a service issue. We are monitoring the incident and will provide updates."

Document the incident number.

---

# Step 6: Test Teams Web Version

Determine if the issue is application-specific.

### Test

1. Open browser.
2. Navigate to:

https://teams.microsoft.com

3. Attempt login.

### Results

#### Web Version Works

Issue likely exists with:

- Desktop app
- Teams cache
- Local profile

Proceed to cache troubleshooting.

#### Web Version Fails

Issue is likely:

- Account related
- Authentication related
- Licensing related

Continue investigating account settings.

---

# Step 7: Clear Teams Cache

Corrupted cache commonly causes sign-in issues.

### Close Teams Completely

1. Right-click Teams icon in system tray.
2. Select:

Quit

### Delete Cache

Press:

Windows + R

Enter:

```text
%appdata%\Microsoft\Teams
```

Delete contents of:

- Cache
- databases
- GPUCache
- IndexedDB
- Local Storage
- tmp

### Relaunch Teams

Attempt sign-in again.

---

# Step 8: Remove and Re-Add Work Account

Corrupted Windows authentication tokens can prevent login.

### Disconnect Account

1. Open:

Settings → Accounts → Access Work or School

2. Select connected account.
3. Click Disconnect.

### Reconnect

1. Restart computer.
2. Return to:

Settings → Accounts → Access Work or School

3. Connect account again.

Test Teams login.

---

# Step 9: Verify MFA Functionality

Authentication failures often involve MFA.

### Ask User

- Are MFA prompts appearing?
- Are prompts being denied?
- Is Microsoft Authenticator working?

### Common MFA Problems

- New phone
- Deleted Authenticator app
- Incorrect time on device
- MFA registration corruption

### Admin Verification

Microsoft Entra Admin Center:

Users → Authentication Methods

Verify:

- Correct phone number
- Authenticator registration exists

Reset MFA registration if necessary.

---

# Step 10: Review Conditional Access Policies

Some organizations restrict access based on:

- Device compliance
- Location
- VPN usage
- Risk level

### Check Entra Sign-In Logs

Microsoft Entra Admin Center:

Users → Sign-In Logs

Review:

- Failure reason
- Conditional Access results
- MFA failures

### Common Findings

- Device not compliant
- Blocked location
- Failed MFA
- Risk-based sign-in block

---

# Step 11: Reinstall Microsoft Teams

If all account checks pass:

### Remove Teams

1. Open:

Settings → Apps

2. Uninstall:
   - Microsoft Teams
   - Teams Machine-Wide Installer (if present)

### Reboot

Restart computer.

### Reinstall

Install latest Teams client.

Attempt sign-in again.

---

# Step 12: Test on Another Device

Determine whether issue follows:

- User account
- Computer

### Results

#### User Can Sign In Elsewhere

Issue is local device-related.

Focus on:

- Cache
- Windows profile
- Installed Teams client

#### User Cannot Sign In Anywhere

Issue is account-related.

Investigate:

- Licensing
- MFA
- Account status
- Conditional Access

---

# Quick Troubleshooting Flow

1. Verify internet connectivity.
2. Test login at portal.office.com.
3. Confirm account is active.
4. Verify Teams license assignment.
5. Check Microsoft Service Health.
6. Test Teams web version.
7. Clear Teams cache.
8. Reconnect work account.
9. Verify MFA functionality.
10. Review Entra sign-in logs.
11. Reinstall Teams.
12. Escalate if unresolved.
