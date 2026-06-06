# Microsoft PowerPoint – Sharing Problems

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "I can't share my PowerPoint presentation."
>
> "My coworker can't open the file I shared."
>
> "The Share button isn't working."
>
> "People are getting access denied when opening the presentation."

---

# Objective

Determine why a PowerPoint presentation cannot be shared properly and restore access for the intended recipients.

Common causes include:

* Incorrect sharing permissions
* OneDrive synchronization issues
* SharePoint access problems
* Broken sharing links
* External sharing restrictions
* File ownership issues
* Network connectivity problems
* Microsoft 365 service issues

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. How is the file being shared?

   * OneDrive
   * SharePoint
   * Email attachment
   * Microsoft Teams
   * Network drive

2. What error message is displayed?

3. Who is unable to access the file?

   * Internal users
   * External users
   * Specific individuals

4. Has sharing worked previously?

5. When did the issue begin?

6. Is the issue affecting:

   * One file
   * Multiple files

### Determine Scope

Ask:

> "Can other users access the presentation successfully?"

This helps determine if the issue is:

* User-specific
* File-specific
* Permission-related
* Organization-wide

---

# Step 1: Verify File Location

Determine where the presentation is stored.

### Check Storage Location

Verify whether the file is located in:

* OneDrive
* SharePoint
* Teams
* Local device
* Network share

### Results

#### File Location Known

Continue troubleshooting.

#### File Location Unknown

Locate the source file before proceeding.

---

# Step 2: Verify User Access

Confirm the affected user has permission to access the file.

### Check Permissions

1. Locate the presentation.
2. Right-click the file.
3. Select:

Manage Access

or

Share

### Verify

Ensure the user appears in the permissions list.

### Results

#### User Has Access

Continue troubleshooting.

#### User Missing

Grant appropriate access.

---

# Step 3: Verify Sharing Link

Broken or expired links can prevent access.

### Check Link

1. Open:

Manage Access

2. Review existing sharing links.

### Verify

* Link is active
* Link has not expired
* Link permissions are correct

### Results

#### Link Valid

Continue troubleshooting.

#### Link Invalid

Create a new sharing link.

---

# Step 4: Test Access Yourself

Determine whether the issue is user-specific.

### Test

1. Open the shared link.
2. Verify access.

### Results

#### Access Successful

Issue may affect specific users.

#### Access Fails

Investigate file permissions and sharing settings.

---

# Step 5: Verify OneDrive Synchronization

If the file is stored in OneDrive:

### Check Sync Status

1. Click the OneDrive icon in the system tray.
2. Verify:

* Sync completed successfully
* No sync errors exist

### Results

#### Sync Healthy

Continue troubleshooting.

#### Sync Errors Found

Resolve OneDrive synchronization issues.

---

# Step 6: Verify SharePoint Permissions

If the file is stored in SharePoint:

### Check Site Permissions

1. Open SharePoint site.
2. Review:

Site Permissions

### Verify

User has access to:

* Site
* Library
* Folder
* File

### Results

#### Permissions Correct

Continue troubleshooting.

#### Permissions Missing

Grant required access.

---

# Step 7: Verify External Sharing Policies

External users may be blocked by organization policies.

### Review Sharing Settings

Check:

* SharePoint sharing policies
* OneDrive sharing policies
* External sharing restrictions

### Results

#### External Sharing Allowed

Continue troubleshooting.

#### External Sharing Blocked

Adjust policy if appropriate.

---

# Step 8: Test Different Sharing Method

Determine whether the issue involves the sharing platform.

### Test Alternatives

Share using:

* New sharing link
* Email attachment
* Teams chat
* Different OneDrive link

### Results

#### Alternative Method Works

Issue likely involves original sharing method.

#### Alternative Method Fails

Continue troubleshooting.

---

# Step 9: Verify File Is Not Locked

Files being edited can occasionally create access issues.

### Check File Status

Verify:

* File is not checked out
* File is not locked by another application
* Co-authoring is functioning properly

### Results

#### File Available

Continue troubleshooting.

#### File Locked

Close active editing sessions.

---

# Step 10: Test Another User

Determine whether the issue affects one person or multiple users.

### Test

Grant access to another user.

### Results

#### Other User Can Access

Issue is specific to the affected user.

#### Other User Cannot Access

Issue likely involves permissions or sharing configuration.

---

# Step 11: Verify Microsoft 365 Service Health

Sharing services rely on Microsoft 365 infrastructure.

### Microsoft 365 Admin Center

Navigate to:

Health → Service Health

Review incidents affecting:

* OneDrive
* SharePoint Online
* Microsoft 365

### Results

#### Service Incident Exists

Monitor Microsoft updates.

#### No Incident Exists

Continue troubleshooting.

---

# Step 12: Verify User Sign-In Status

Authentication issues can block file access.

### Test Login

1. Open:

https://portal.office.com

2. Sign in.

### Results

#### Login Successful

Continue troubleshooting.

#### Login Fails

Investigate:

* Password issues
* MFA issues
* Account lockouts

---

# Step 13: Check Browser Access

Determine whether the issue is application-specific.

### Test

1. Open the file in a browser.
2. Attempt access through:

PowerPoint Online

### Results

#### Browser Access Works

Issue may involve desktop application.

#### Browser Access Fails

Issue likely involves permissions or sharing.

---

# Step 14: Repair Microsoft Office

If desktop-only access issues occur:

### Open Installed Apps

1. Open:

Settings → Apps

2. Locate:

Microsoft 365

3. Select:

Modify

### Run Repair

Choose:

Quick Repair

If necessary:

Online Repair

### Restart Computer

Retest access.

---

# Step 15: Recreate the Shared File

If sharing remains unsuccessful:

### Create New Copy

1. Save a copy of the presentation.
2. Upload the new file.
3. Configure sharing permissions again.

### Test Access

Verify whether recipients can open the new copy.

---

# Quick Troubleshooting Flow

1. Verify file location.
2. Check user permissions.
3. Verify sharing link.
4. Test access yourself.
5. Verify OneDrive sync status.
6. Verify SharePoint permissions.
7. Review external sharing policies.
8. Test another sharing method.
9. Check for file locks.
10. Test another user.
11. Check Microsoft 365 Service Health.
12. Verify sign-in status.
13. Test browser access.
14. Repair Office.
15. Recreate the shared file.

---

# Expected Outcome

By following this process, a help desk technician can identify whether PowerPoint sharing issues are caused by:

* Permission problems
* Broken sharing links
* OneDrive synchronization issues
* SharePoint access restrictions
* External sharing policies
* Authentication failures
* File locking conflicts
* Microsoft 365 service issues

and restore access to the presentation for the intended users.

