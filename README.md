# CareFlow OPD — Hospital Outpatient Booking System

A responsive, clickable frontend prototype for a Hospital Outpatient Department (OPD) appointment booking system. It demonstrates the patient and administrator workflows designed for the CareFlow OPD software engineering project.

## Run the prototype

1. Download and extract the ZIP file.
2. Open the extracted `CareFlow_OPD_Website` folder.
3. Keep `index.html`, `styles.css`, and `script.js` together in the same folder.
4. Double-click `index.html` and choose Chrome, Edge, Firefox, or Safari.

No package installation, build command, database, or internet connection is required for the local demonstration.

If your browser blocks local-file behavior, open a terminal in this folder and run:

```bash
# Windows
py -m http.server 8000

# macOS / Linux
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Demo accounts

| Role | Email | Password |
|---|---|---|
| Patient | `patient@opd.demo` | `patient123` |
| Admin | `admin@opd.demo` | `admin123` |

Additional sample patient accounts are available in the Patient Accounts screen for testing account restrictions.

## Patient features

- Register, sign in, and manage a patient profile.
- Browse doctors, specialties, departments, and availability.
- Select an available date and appointment time.
- Optionally describe the reason for the visit / medical condition.
- Receive a system-generated token after a successful booking.
- View only the patient's own upcoming token number and appointment status.
- Cancel or reschedule an eligible Waiting appointment.
- Book a separate follow-up appointment after a Completed visit; the completed visit remains in history.
- View and manage in-app notifications from the bell beside the search bar.
- View the patient account status (Active or Banned).

## Admin features

- Dashboard with appointment, token-status, doctor, and patient-account statistics.
- Read-only appointment monitoring, filtering, and token-record viewing.
- Patient account search and account-status visibility.
- Ban a patient account with an optional reason and restore access.
- Add, edit, and deactivate doctor profiles.
- Manage doctor clinic days and available appointment times.
- View in-app notifications from the bell beside the search bar.

**Admin cannot manually update appointment/token statuses or call the next patient.** In the intended system architecture, the backend booking/queue workflow owns status transitions; the Admin interface is for monitoring and account/doctor administration.

## Prototype scope and limitations

This is a static frontend prototype. It does not connect to a real hospital backend, database, notification service, or authentication provider. Demo data are stored in the browser's `localStorage` and are not synchronized between devices or users. Demo passwords and patient visit descriptions are not securely protected. Do not enter real patient, medical, or personal information.

Appointment statuses shown in the prototype are sample data. The `notifyAppointmentStatusUpdate` function is an integration point illustrating where a future backend event could trigger notifications. Real status validation, account restrictions, role permissions, privacy controls, and audit logs must be enforced by a server in a production implementation.

## Project files

```text
CareFlow_OPD_Website/
├── index.html
├── styles.css
├── script.js
├── README.md
└── .gitignore
```

## Add this prototype to the GitHub repository

Repository: <https://github.com/jazzvarichsara-stack/The-hospital-booking-system>

1. Extract the ZIP file.
2. Open the extracted `CareFlow_OPD_Website` folder.
3. In the GitHub repository, open the `main` branch.
4. Choose **Add file → Upload files**.
5. Upload `index.html`, `styles.css`, `script.js`, and `.gitignore` to the repository root. Upload/replace `README.md` with this README if the team approves the updated description.
6. Do not delete the existing `docs/` folder; it can remain beside the website files.
7. Enter a commit message such as `Add CareFlow OPD frontend prototype` and select **Commit changes**.

After upload, the repository root should look like:

```text
The-hospital-booking-system/
├── docs/                 # Keep the team's existing documents
├── index.html
├── styles.css
├── script.js
├── README.md
└── .gitignore
```

### Optional: publish with GitHub Pages

After the files are in the repository root, open **Settings → Pages**. Under the build/deployment source, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, then save. GitHub Pages publishes static frontend files; it does not provide the backend services described above.

## License and project use

This prototype is provided for the CareFlow OPD academic project. Add a license only if the project team has agreed on one.
