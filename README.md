# CareFlow OPD — How to Open and View the Prototype

CareFlow OPD is a static website prototype for a Hospital Outpatient Department (OPD) booking system. It is built with **HTML, CSS, and JavaScript** and is intended to be opened and viewed in a web browser. You can use **Visual Studio Code (VS Code)** to open the project and edit its files.

> This README explains how to extract, open, run, and explore the prototype. It does not require Python, Node.js, npm, or a build process.

## 1. Extract the ZIP file

1. Download the CareFlow OPD project ZIP.
2. In Windows File Explorer, right-click the ZIP file.
3. Select **Extract All...** and choose a folder.
4. Open the extracted `CareFlow_OPD_VSCode_Project` folder.

**Important:** Do not open `index.html` from inside the ZIP preview. Extract the whole folder first so the HTML, CSS, and JavaScript files stay together.

## 2. Open the project in Visual Studio Code

1. Open **Visual Studio Code**.
2. Select **File → Open Folder...**.
3. Choose the extracted `CareFlow_OPD_VSCode_Project` folder.
4. In the Explorer panel, confirm that you can see `index.html`, `styles.css`, and `script.js`.

## 3. Run the prototype with Live Server (recommended)

1. In VS Code, open the **Extensions** panel (`Ctrl + Shift + X`).
2. Search for **Live Server** by Ritwick Dey and install it.
3. Open `index.html` in the editor.
4. Right-click inside the editor and choose **Open with Live Server**. You can also click **Go Live** in the VS Code status bar.
5. Your default browser should open the CareFlow OPD website.

When you edit and save the HTML, CSS, or JavaScript files, Live Server refreshes the browser page.

## 4. Open the prototype without Live Server

After extracting the ZIP, you can double-click `index.html` to open the website in your browser. Keep these three files in the same folder:

- `index.html`
- `styles.css`
- `script.js`

There is also a one-file fallback named `CareFlow_OPD_Standalone.html`. Double-click that file to open the standalone version; it contains its own CSS and JavaScript and does not need the separate files.

## 5. Demo login accounts

Use either the demo buttons on the sign-in screen or enter these credentials:

| Role | Email | Password |
|---|---|---|
| Patient | `patient@opd.demo` | `patient123` |
| Admin | `admin@opd.demo` | `admin123` |

The prototype also includes sample patient accounts that can be viewed from the Admin **Patient Accounts** page.

## 6. What to explore

### Patient portal

- Create a patient account or sign in with the demo patient account.
- Browse doctors, specialties, departments, and available schedules.
- Select a doctor, appointment date, and available time.
- Optionally enter a reason for the visit or describe a medical condition when booking.
- Confirm the booking and view the generated token number.
- View your own upcoming token and appointment status.
- Cancel or reschedule eligible appointments.
- Book a separate follow-up appointment after a completed visit; the previous completed visit remains in the history.
- Open the notification bell beside the search bar to view and manage notifications.
- View your account status on the patient side.

### Admin workspace

- View dashboard statistics for appointments, token statuses, doctors, and patient accounts.
- Search and view appointment and token records. Appointment and token statuses are read-only for Admin.
- Open **Patient Accounts** to view account statuses, ban an account, or restore access.
- Add, edit, or deactivate doctor profiles.
- Manage doctor clinic days and available time slots.
- Open the notification bell beside the search bar to view and manage notifications.

The **Resources** section and M2 requirement-map link have been removed from both Patient and Admin navigation.

## 7. How the demo data works

The prototype saves sample changes in the browser's local storage when it is available. This means changes such as bookings, account restrictions, and notifications usually remain in the same browser after refreshing the page. They are not shared with another browser, computer, or user session.

To start again with the original sample data, clear the site's local storage for the local CareFlow address in your browser's Developer Tools, then reload the page. This will reset demo bookings, account changes, and notifications saved in that browser.

## 8. Troubleshooting

**The browser shows a blank page or says `styles.css` or `script.js` is missing**

- Make sure you extracted the complete ZIP.
- Make sure `index.html`, `styles.css`, and `script.js` are in the same folder.
- Open `index.html` from the extracted folder, not from the ZIP preview.
- In VS Code, try **Open with Live Server**.
- Refresh the browser with `Ctrl + Shift + R`.

**The page says JavaScript is required**

Enable JavaScript in your browser and reload the page.

**The standalone version works but `index.html` does not**

Check that `styles.css` and `script.js` have not been moved or renamed. The standalone file is provided as a backup viewing option.

**The demo data looks different from the original sample**

The browser may have saved earlier test changes. Clear the local CareFlow site's local storage and reload to restore the original demo data.

## 9. Project files

```text
CareFlow_OPD_VSCode_Project/
├── index.html                    # Main website page
├── styles.css                    # Website layout, colors, and responsive design
├── script.js                     # Demo data and interactive behavior
├── CareFlow_OPD_Standalone.html  # One-file fallback version
├── README.md                     # Instructions for opening and viewing the prototype
├── OPEN_ME_FIRST.txt             # Short quick-start instructions
└── .gitignore                    # Ignore rules for development files
```

## 10. Prototype limitations and privacy

This is a **frontend demonstration only**. It does not connect to a real hospital backend, production database, real authentication service, or real-time notification service. Appointment and token status behavior is simulated for demonstration; the intended design is that a real backend controls status transitions while Admin views operational records without manually editing those statuses.

Do not enter real patient, medical, or personal information. Demo credentials and browser storage are not secure. A production system requires server-side authentication, authorization, secure data storage, audit logs, and approved clinical workflows.
