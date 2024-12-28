# Personal Time Tracker

## 📚 Overview
This Google Apps Script project helps manage personal time tracking directly from a Google Spreadsheet. It allows users to start and stop timers for tasks, log time records, and send summary reports via email.

## 🚀 Features
- Start and stop task timers.
- Automatically log task durations in a dedicated sheet.
- Generate and send time tracking reports via email.
- Customizable email templates with placeholders.
- Dynamic configuration through a Google Sheets "Settings" sheet.

## 📂 Project Structure

- **util.js**
   - `_getUi_`: Access the Spreadsheet UI.
   - `_toast_`: Display toast messages.
   - `_createAlert_`: Create custom alert dialogs.
   - `_createConfirm_`: Create confirmation dialogs.
   - `_updateTextWithPlaceholders_`: Replace placeholders in text with actual values.
   - `_exportSpreadsheetAsPdf_`: Export a spreadsheet as a PDF.
   - `_try_`: Handle and display errors gracefully.

- **code.js**
   - `refreshTimer`: Refreshes the timer display.
   - `installTrigger_`: Installs a timer refresh trigger.
   - `uninstallTrigger_`: Removes the timer trigger.
   - `startTimer_`: Starts a task timer.
   - `stopTimer_`: Stops the timer and logs the record.
   - `sendReport_`: Generates and sends a time tracking report.
   - `onOpen`: Adds custom menu options to the Spreadsheet UI.

- **email.html**
   - HTML template used for generating time tracking report emails.

## ⚙️ Setup Instructions

1. Open your Google Spreadsheet.
2. Navigate to **Extensions > Apps Script**.
3. Copy and paste the contents of `util.js`, `code.js`, and `email.html` into the Apps Script editor.
4. Create a sheet with the following tabs:
   - `Tasks`: List of tasks to be tracked.
   - `Records`: Logs of completed tasks with time records.
   - `Report`: Used for generating summary reports.
5. Add named ranges in Google Sheets:
   - `start`: Timer start cell.
   - `task`: Row number of the current active task.
   - `reportFrom`: Sender email address.
   - `reportTo`: Recipient email address.
   - `reportBy`: Sender name.
6. Save the script and run the `onOpen` function.

## 📝 Configuration Example
In your `Settings` or named ranges:
| Named Range  | Example Value        |
|--------------|-----------------------|
| start        | A1                   |
| task         | B1                   |
| reportFrom   | user@example.com     |
| reportTo     | client@example.com   |
| reportBy     | John Doe             |

## 🛠️ How It Works
1. Select a task row in the `Tasks` sheet.
2. Start the timer from the custom menu.
3. When finished, stop the timer.
4. Task details, including start and stop time, are recorded in the `Records` sheet.
5. Use the **Send Email** option from the menu to generate and send a PDF report.

## 📧 Permissions
The script requires the following permissions:
- Access Google Sheets data
- Send emails via Gmail
- Manage time-based triggers

## 📜 License
This project is licensed under the MIT License.

## 🤝 Contributions
Contributions are welcome! Feel free to open an issue or submit a pull request.

## ⭐ Acknowledgments
Thanks to the Google Apps Script community for continuous support and resources.

---
Happy tracking! 🕒
