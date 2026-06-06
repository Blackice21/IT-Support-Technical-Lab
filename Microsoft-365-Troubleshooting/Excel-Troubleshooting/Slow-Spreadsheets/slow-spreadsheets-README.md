# Microsoft Excel – Slow Spreadsheets

## Help Desk Troubleshooting Guide

### Ticket Example

**User Report:**

> "My spreadsheet is running very slowly."
>
> "Excel freezes when I make changes."
>
> "The workbook takes a long time to open."
>
> "Calculations are taking forever to complete."

---

# Objective

Determine why an Excel workbook is performing slowly and restore acceptable performance.

Common causes include:

* Large datasets
* Excessive formulas
* Volatile functions
* Conditional formatting overload
* External data connections
* Large numbers of worksheets
* Corrupted workbook elements
* Insufficient system resources

---

# Information Gathering

Before troubleshooting, ask the user:

### Basic Questions

1. When does the slowdown occur?

   * Opening the workbook
   * Saving the workbook
   * Entering data
   * Running formulas
   * Filtering or sorting

2. Does the issue affect:

   * One workbook
   * Multiple workbooks

3. Approximately how large is the workbook?

4. Has performance recently changed?

5. Are macros being used?

6. Are external data sources connected?

### Determine Scope

Ask:

> "Do other Excel files perform normally?"

This helps determine if the issue is:

* Workbook-specific
* Excel-related
* System-related

---

# Step 1: Verify System Resources

Determine whether the computer is resource constrained.

### Open Task Manager

Press:

```text
Ctrl + Shift + Esc
```

Review:

* CPU usage
* Memory usage
* Disk usage

### Results

#### Resources Normal

Continue troubleshooting.

#### Resources High

Close unnecessary applications and retest.

---

# Step 2: Test Other Workbooks

Determine whether the issue is isolated.

### Test

1. Open another Excel workbook.
2. Perform common tasks.

### Results

#### Other Files Perform Normally

Issue is likely workbook-specific.

#### Multiple Files Are Slow

Issue may involve Excel or the system.

---

# Step 3: Check Workbook File Size

Large workbooks often experience performance issues.

### Verify File Size

1. Locate the workbook.
2. Review file properties.

### Results

#### Large File Size

Investigate formulas, formatting, and embedded content.

#### Normal File Size

Continue troubleshooting.

---

# Step 4: Check Calculation Mode

Automatic calculations can impact performance.

### Review Calculation Settings

1. Open:

Formulas → Calculation Options

### Verify

Current setting:

* Automatic
* Automatic Except Data Tables
* Manual

### Results

#### Automatic Mode

Temporarily test with Manual mode.

#### Manual Mode

Performance issue may have another cause.

---

# Step 5: Review Formula Usage

Large numbers of formulas can slow performance.

### Check For

* Complex nested formulas
* Array formulas
* Excessive lookup formulas
* Repeated calculations

### Common Examples

* VLOOKUP
* XLOOKUP
* INDEX/MATCH
* SUMPRODUCT

### Results

#### Excessive Formula Usage

Optimize formulas where possible.

#### Formula Usage Normal

Continue troubleshooting.

---

# Step 6: Check for Volatile Functions

Volatile functions recalculate frequently.

### Review Workbook

Look for:

* NOW()
* TODAY()
* RAND()
* RANDBETWEEN()
* OFFSET()
* INDIRECT()

### Results

#### Volatile Functions Found

Reduce usage if possible.

#### None Found

Continue troubleshooting.

---

# Step 7: Review Conditional Formatting

Excessive formatting can affect workbook speed.

### Open Conditional Formatting Rules

1. Select:

Home → Conditional Formatting → Manage Rules

### Verify

* Duplicate rules
* Large ranges
* Complex conditions

### Results

#### Excessive Rules Found

Simplify or remove unnecessary rules.

#### Rules Normal

Continue troubleshooting.

---

# Step 8: Check External Data Connections

External connections may delay workbook operations.

### Review Connections

1. Select:

Data → Queries & Connections

### Verify

* Database connections
* Power Query connections
* Linked workbooks

### Results

#### Problem Connection Found

Disable or repair connection.

#### No Issues Found

Continue troubleshooting.

---

# Step 9: Review Hidden Worksheets

Hidden sheets may contain significant data.

### Check Worksheets

1. Right-click worksheet tab.
2. Select:

Unhide

### Verify

Review hidden sheets for:

* Excessive data
* Unused calculations
* Large datasets

---

# Step 10: Check Pivot Tables

Large pivot tables can impact performance.

### Review Pivot Tables

Verify:

* Data source size
* Refresh frequency
* Number of pivot tables

### Results

#### Large Pivot Tables Found

Optimize data sources and refresh settings.

#### No Issues Found

Continue troubleshooting.

---

# Step 11: Remove Excess Formatting

Formatting entire worksheets can increase file size.

### Check Used Range

1. Press:

```text
Ctrl + End
```

2. Verify the actual used range.

### Results

#### Excess Blank Rows/Columns Included

Remove unused rows and columns.

#### Range Appears Normal

Continue troubleshooting.

---

# Step 12: Open Excel in Safe Mode

Determine whether add-ins are causing slow performance.

### Launch Safe Mode

Press:

Windows + R

Enter:

```text
excel /safe
```

### Test Workbook

### Results

#### Performance Improves

Investigate Excel add-ins.

#### No Improvement

Continue troubleshooting.

---

# Step 13: Disable Unnecessary Add-ins

### Open Add-ins

1. Select:

File → Options → Add-ins

2. Review installed add-ins.

### Test

Disable nonessential add-ins temporarily.

### Results

#### Performance Improves

Identify problematic add-in.

#### No Improvement

Continue troubleshooting.

---

# Step 14: Save Workbook as New File

Workbook corruption can impact performance.

### Save As

1. Select:

File → Save As

2. Save with a new name.

### Test

Open the new workbook and verify performance.

---

# Step 15: Repair Microsoft Office

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

Retest workbook.

---

# Step 16: Upgrade Workbook Design

For extremely large workbooks:

### Consider

* Splitting data into multiple files
* Using Power Query
* Using Power Pivot
* Moving data into a database solution

### Verify

Performance improves after redesign.

---

# Quick Troubleshooting Flow

1. Verify system resources.
2. Test other workbooks.
3. Check workbook size.
4. Review calculation mode.
5. Review formulas.
6. Check volatile functions.
7. Review conditional formatting.
8. Check external connections.
9. Review hidden worksheets.
10. Check pivot tables.
11. Remove excess formatting.
12. Test Safe Mode.
13. Disable add-ins.
14. Save as a new workbook.
15. Repair Office.
16. Consider workbook redesign.

---

# Expected Outcome

By following this process, a help desk technician can identify whether Excel performance issues are caused by:

* Large datasets
* Excessive formulas
* Volatile functions
* Conditional formatting overload
* External connections
* Pivot table complexity
* Add-in conflicts
* Workbook corruption
* Insufficient system resources

and restore acceptable workbook performance for the user.

