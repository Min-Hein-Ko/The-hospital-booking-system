# CareFlow OPD — Hospital Outpatient Booking System

CareFlow OPD is a web-based prototype designed to improve the outpatient department (OPD) appointment experience for patients and support hospital staff with clearer appointment and account administration.

## Live Prototype

**[Open the CareFlow OPD Prototype](https://min-hein-ko.github.io/The-hospital-booking-system/)**

The prototype is published through GitHub Pages and can be opened from a web browser on desktop computers, tablets, and mobile devices.

## The Problem We Aim to Solve

Patients visiting an outpatient department may spend unnecessary time contacting or visiting the hospital to find an appropriate doctor, check consultation schedules, or arrange an appointment. Unclear appointment information and limited visibility of queue progress can also make hospital visits less predictable and contribute to avoidable waiting and crowding.

CareFlow OPD aims to reduce these difficulties by making doctor information, appointment availability, online booking, and personal token information easier to access. Patients can plan their visit with their appointment details and token status instead of relying only on in-person enquiries. The system is intended to reduce avoidable waiting and time spent arranging appointments; it does not guarantee that clinical consultation queues will be eliminated.

## Project Objectives

- Help patients find doctors by specialty and view available appointment schedules.
- Allow patients to book an available appointment online and receive a system-generated token.
- Prevent duplicate booking of an unavailable doctor, date, and time slot.
- Let patients review their own upcoming appointment, token number, and appointment status.
- Support appointment cancellation and rescheduling, including booking a separate follow-up after a completed visit.
- Give administrators tools to maintain doctor information and schedules, monitor appointment data, and manage patient account access.
- Keep appointment and token status changes under system/backend control rather than allowing administrators to manually edit status values.
- Provide in-app notifications for patients and administrators.

## Main Features

### Patient

- Register and sign in to a patient account.
- Browse doctors, specializations, departments, and available schedules.
- Book an appointment and receive an automatically generated token number.
- Add an optional reason for the visit or description of the patient's condition when booking.
- View personal appointment history, upcoming token number, and appointment status.
- Cancel or reschedule eligible appointments.
- Book a follow-up appointment without replacing the record of a completed appointment.
- View account status and receive notifications about relevant account and appointment events.

### Administrator

- View an operational dashboard with appointment, queue, doctor, and patient-account summaries.
- View and search appointment and token records without manually changing appointment or token statuses.
- Add, edit, and deactivate doctor information.
- Manage doctor schedules and appointment availability.
- View patient accounts and their account status.
- Ban or restore patient account access, with an optional reason for a restriction.
- Manage the administrator's own profile information.
- Receive and manage in-app notifications.

## Appointment and Token Status Control

Appointment and token statuses are intended to be controlled by the system/backend workflow. The administrator interface is for viewing operational data and managing hospital information and patient account access; it does not provide controls for manually selecting appointment statuses.

The prototype demonstrates these status labels:

- `Waiting`
- `Called`
- `In Operation`
- `Completed`
- `Cancelled`

The final backend implementation must validate permitted status transitions and record the event that causes each transition.

## Technology

- **HTML5** — page structure
- **CSS3** — layout, styling, and responsive presentation
- **JavaScript** — prototype interactions and demonstration logic
- **GitHub Pages** — static website hosting

## Team Members and Contributions

| No. | Name | Related Work / Contribution |
|---:|---|---|
| 1 | Aung Phone Thant | M1, M2, Functional Requirements (FR), Non-Functional Requirements (NFR), Use Cases |
| 2 | Yoon Yadanar MyintHtay | M1, M2, Specification, UI |
| 3 | Apichaya Somrit | M1, M2, Data Model, Screen List, Traceability Summary (Golden Thread) in the SRS |
| 4 | Min Hein Ko | M1, M2, Prototype, Diagrams, README |
| 5 | Varissara Kitiphatphiboon | M1, M2, UI, Process and Team Coordination |

## Project Scope

The prototype focuses on outpatient doctor discovery, appointment booking, token information, appointment management, doctor schedules, administrator monitoring, patient account access, and notifications.

The following capabilities are outside the current project scope: online payment or billing, online medical consultation or video calls, diagnosis or treatment recommendations, prescription management, electronic medical records management, emergency or ambulance services, insurance claims, online pharmacy or medicine ordering, and integration with external hospital systems.

## Prototype Limitations and Data Privacy

CareFlow OPD is an academic frontend prototype, not a production hospital service. Its demonstration data is stored locally in the browser and is not synchronized through a shared backend or database. Account login and role behavior are simulated for demonstration purposes. A public static website must not be used to store or process real patient data.

Use demonstration accounts and sample information only. Do not enter real names, contact details, passwords, medical conditions, or other confidential patient information. A production system would require a properly secured backend, database, authentication, authorization, audit logging, and privacy controls before clinical use.

---

**Project:** The Hospital Booking System — CareFlow OPD  
**Repository:** [The-hospital-booking-system](https://github.com/Min-Hein-Ko/The-hospital-booking-system)  
**Live prototype:** [CareFlow OPD on GitHub Pages](https://min-hein-ko.github.io/The-hospital-booking-system/)
