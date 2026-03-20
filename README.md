# No-Show Tracker
**User Guide & Reference Manual** · Version 1.0 · HTML App · Winter Semester Sheet

---

## What Is This App?

The No-Show Tracker is a standalone HTML application that lets your team manage student no-show appointment records directly from your existing Excel file. There is nothing to install — just open the HTML file in a browser.

It reads your `No_show_tracking.xlsx` file, lets you view, add, edit, and delete records, then saves all changes back to the same Excel file on your computer. The Excel file keeps its original format and color-coding and can be shared with other team members normally.

---

## Files You Need

| File | Purpose |
|------|---------|
| `NoShow_Tracker_App.html` | The app — open this in your browser |
| `No_show_tracking.xlsx` | Your existing Excel data file |

---

## Getting Started

1. Save both files (the HTML app and your Excel file) anywhere on your computer
2. Double-click `NoShow_Tracker_App.html` to open it in your browser
3. The app opens to a welcome screen with two options: **Load Excel File** or **Connect a Shared Google Sheet**
4. Click **Load Excel File** (or drag and drop your `.xlsx` file onto the card)
5. Your records load instantly from the **Winter Semester** sheet

> **Best browser to use:** Chrome or Edge. These browsers support the File System Access API, which allows the app to save changes directly back to your original Excel file without downloading a new copy.

---

## Color Coding System

Every row is automatically colored based on how many times the same student appears in the data. This happens instantly — you do not need to set anything up.

| Color | No-Show Count | Meaning |
|-------|--------------|---------|
| 🟢 Green | 1 time | First no-show |
| 🟡 Yellow | 2 times | Repeat no-show |
| 🔴 Red | 3 or more times | Chronic no-show |

The **Follow-up** column (1st, 2nd, 3rd) is also calculated automatically based on the order the student appears in the data. You never need to type this manually.

---

## Adding a New Record

1. Click the **Add record** button in the top right of the toolbar
2. Fill in the student's **Last name** and **First name** (required)
3. Fill in the remaining fields: Email, Date, Time, Mode, and Advisor
4. The **Follow-up type** (1st, 2nd, 3rd) is shown automatically based on the name you enter
5. Click **Save record**

The new row appears immediately in the table with the correct color. The unsaved changes warning appears at the top to remind you to save.

---

## Editing a Record

1. Find the record in the table (use the search bar or filters if needed)
2. Click the **Edit** button on that row
3. The same form opens with the existing data pre-filled
4. Make your changes and click **Save record**

Colors and follow-up types update automatically after editing.

---

## Deleting a Record

1. Find the record in the table
2. Click the **Del** button on that row
3. A confirmation dialog appears — click **Delete** to confirm

> Deleting a record may change the color and follow-up type of other records with the same student name, since the total count changes.

---

## Saving Your Changes

### Save Back to File (Chrome / Edge Only)

When you load a file in Chrome or Edge, the browser acquires a file handle — a direct connection to the file on your computer. When you click **Save back to file**, the app overwrites the original Excel file with your updated data. No download dialog appears. The file is updated in place.

> **Important:** Chrome will ask for write permission the first time you save. Click **Allow** in the browser's permission bar at the top.

### Download Copy (All Browsers)

Click **Download copy** to download an updated `.xlsx` file. This works in all browsers including Firefox and Safari. The downloaded file has the same name as the original with `_copy` added.

> **To replace your original:** move the downloaded file to the same folder as your original and rename it to match.

### Unsaved Changes Warning

A yellow warning bar appears at the top of the tracker whenever you have unsaved changes. It disappears after you save. If you try to close the browser tab with unsaved changes, the browser will ask you to confirm before leaving.

---

## Searching and Filtering

| Control | What It Does |
|---------|-------------|
| Search bar | Searches across last name, first name, email, and advisor name as you type |
| Advisor filter | Shows only records assigned to a specific advisor |
| Count filter | Filters to show only 1×, 2×, or 3+ no-show students |
| Column headers | Click any column header to sort ascending or descending |

---

## Sharing the Excel File with Your Team

### Option 1: Shared Drive (Recommended)

This is the simplest approach for teams already using OneDrive, SharePoint, or Google Drive.

1. Upload your Excel file to a shared folder that everyone on the team can access
2. Share the HTML app file the same way (or send it by email)
3. Each team member opens the HTML app, loads the shared Excel file, makes changes, and saves back

> **Important:** Only one person should edit at a time to avoid conflicts. Coordinate with your team.

### Option 2: Google Sheets (Live Collaboration)

For real-time collaboration where multiple people may edit simultaneously, use Google Sheets.

1. Click **Share link** in the header of the app
2. Paste your Google Sheets URL in the dialog
3. In your Google Sheet, click **Share** and set access to **"Anyone with the link can edit"**
4. Send that link to your team — everyone can edit the same sheet at the same time
5. Use **Download copy** in the app to export as Excel whenever you need an offline backup

---

## Excel File Structure

The app reads from and writes to the **Winter Semester** sheet. The following columns are used:

| Column | Header | Description |
|--------|--------|-------------|
| A | Last name | Student's last name (stored in uppercase) |
| B | First name | Student's first name (stored in uppercase) |
| C | Email Address | Student's email or phone number |
| D | Appointment Date | Date in DD.MM.YY format (e.g. `20.03.26`) |
| E | Appointment Time | Time in 12-hour format (e.g. `10:00 AM`) |
| F | Appointment Mode | `VIRTUAL APT`, `IN PERSON`, or `Drop-in` |
| G | Follow up type | 1st, 2nd, or 3rd — calculated automatically by the app |
| H | Name of the advisor | Advisor name (Teresa, Zack, Qiuling, or other) |
| I | No-Show Count | Total times this student appears — calculated automatically |

---

## Troubleshooting

| Problem | Solution |
|---------|---------|
| Save back to file is not working | Use Chrome or Edge. Firefox and Safari do not support direct file overwrite. Use **Download copy** instead. |
| Colors are not updating | Make sure you have saved and re-loaded the file. Colors recalculate automatically when the page loads. |
| Student shows as 1st but should be 2nd | Check that the name is spelled exactly the same in both rows. The app matches on Last name + First name together. |
| File loads but shows 0 records | The app looks for a sheet named **Winter Semester**. If your sheet has a different name, it falls back to the first sheet. Check your sheet tab name in Excel. |
| Browser asks for permission to save | This is normal. Click **Allow** in the browser's permission bar. Chrome asks once per session. |
| Times show incorrectly after loading | Excel sometimes stores times as numbers. The app converts them automatically to 12-hour format. |

---

## Tips & Best Practices

- Always click **Save back to file** (or **Download copy**) after making changes before closing the app
- Use the search bar to quickly find a specific student before editing
- When adding a student for the second time, the Follow-up type preview in the form will show **2nd** automatically
- If two people need to edit at the same time, use Google Sheets (see Sharing section above)
- The No-Show Count column in the saved Excel file reflects the total across all rows, not just the current filtered view
- Bookmark the HTML file in your browser for quick access

---

*No-Show Tracker — User Guide · For questions, contact your system administrator*
