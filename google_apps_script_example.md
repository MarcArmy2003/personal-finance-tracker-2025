# 📑 Google Apps Script: Export Monthly Finance Data

This script pulls data from a Google Sheet and sends a monthly summary to your email.

```javascript
function sendMonthlySummary() {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Summary");
  const range = sheet.getRange("A1:B10");
  const data = range.getDisplayValues();
  let message = "";
  data.forEach(row => { message += row.join(": ") + "\n"; });

  MailApp.sendEmail({
    to: "your.email@example.com",
    subject: "Monthly Finance Summary",
    body: message
  });
}
```

To use: Open your Sheet → Extensions → Apps Script → Paste and run.
