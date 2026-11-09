# Hospital OPD Booking System — Testing Results

## 1. Testing objective

This document records the functional checks carried out against the Hospital Outpatient Department (OPD) Booking System prototype. The tests focus on the patient and administrator workflows represented in the prototype, including doctor availability, appointment booking, token generation, appointment management, account controls, and notifications.

The results below are based on the team's recorded observations of the prototype. They are not a claim that the application has undergone independent penetration, performance, or production-environment testing.

## 2. Test results

| No. | Functional Requirement | Test scenario | Expected result | Actual result |
|---:|:---:|---|---|---|
| 1 | FR-1 | Open the doctor directory using the patient interface. | The directory presents doctors who are active and identifies each doctor's specialty. | **Pass.** Active doctors and their specialties can be viewed. |
| 2 | FR-1 | Open a doctor's booking options and inspect the available dates and times. | The patient can see the appointment dates and time slots offered for booking. | **Pass.** Available dates and times are displayed to the patient. |
| 3 | FR-1 | Attempt to choose a doctor or time slot that is already unavailable because it has been booked. | The unavailable doctor or time slot is disabled or otherwise prevented from being selected. | **Pass.** A time slot that has already been booked cannot be selected. |
| 4 | FR-2 | Complete the booking selection using an available doctor, date, and time. | The system accepts the selection when all chosen options are available. | **Pass.** A patient can select an available doctor, date, and time. |
| 5 | FR-2 | Submit an appointment booking and inspect the confirmation. | The system creates the appointment and assigns a token that begins in the Waiting state. It should also prevent duplicate bookings. | **Partially verified.** A token is generated after a successful booking. The recorded observation does not separately demonstrate the initial status or duplicate-booking prevention. |
| 6 | FR-3 | View the details shown after making an appointment. | The appointment view identifies the patient's token number, selected doctor, appointment date, and appointment time. | **Pass.** The token number and appointment date and time are shown after booking; the doctor is selected as part of the displayed appointment information. |
| 7 | FR-3 | Check the appointment after its status has been changed by the system. | The patient-facing view reflects the appointment status supplied by the system. | **Pass.** The prototype displays statuses such as Waiting and Cancelled in the observed situations. |
| 8 | FR-3 | Sign in as a patient and inspect the token information available in the account. | The patient can access their own appointment and token information, but not another patient's private token details. | **Pass.** The tested patient account did not provide access to other patients' token information. |
| 9 | FR-4 | Cancel an appointment that is still upcoming. | The appointment is cancelled and its status changes to Cancelled. | **Pass.** The appointment status changes to Cancelled after cancellation. |
| 10 | FR-4 | Reschedule an existing appointment by choosing another available date and time. | The system saves the new appointment time and issues a new token for the rescheduled booking. | **Pass.** A new available date and time can be selected, and a new token number is generated. |
| 11 | FR-4 | Create a follow-up appointment after an earlier appointment has been completed. | The new booking is stored as a separate appointment, while the completed appointment remains in the patient's history. | **Not tested.** The team did not perform this scenario because the observed appointment flow ended with a Completed status and no follow-up booking was required. |
| 12 | FR-5 | Use the administrator interface to edit a doctor's details and schedule. | An administrator can update the doctor's information and availability. | **Pass.** Doctor information and schedules can be edited from the administrator interface. |
| 13 | FR-5 | After an administrator saves a doctor or schedule change, view the same information as a patient. | The patient interface displays the updated doctor information and availability. | **Pass.** The changes saved by the administrator are visible from the patient interface. |
| 14 | FR-5 | Attempt to remove a doctor who has an existing active appointment. | The system blocks deletion when removing the doctor would affect an existing appointment record. | **Pass.** A doctor with an existing active appointment cannot be removed. |
| 15 | FR-6 | Open the administrator dashboard and review its summary information. | The dashboard provides an overview of appointment activity, active doctors, and patient accounts. | **Pass.** The administrator dashboard can be used to monitor the system overview. |
| 16 | FR-6 | Open the appointment and token information from the administrator interface. | The administrator can inspect appointment and token information, including locating relevant records where the interface provides search or filtering. | **Partially verified.** The team confirmed that the administrator can check the records. The recorded observation does not separately confirm every search and filter operation. |
| 17 | FR-6 | Inspect appointment status and token information from the administrator dashboard. | The administrator can view this information but cannot manually change appointment statuses or control the token queue through the dashboard. | **Pass.** Appointment and token information are view-only in the administrator dashboard. |
| 18 | FR-7 | Open a patient's account details from the administrator interface. | The administrator can view patient information and identify whether the account is Active or Banned. | **Pass.** The administrator can check an individual patient's account status. |
| 19 | FR-7 | Ban a patient account and then use the restore option. | The administrator can restrict the account and later restore its access. | **Partially verified.** The ban and Restore Access actions were successfully observed. The recording does not separately confirm an audit log of these actions. |
| 20 | FR-7 | Try to use appointment services while signed in to a banned patient account. | The system blocks the account from booking or rescheduling and displays an access-restriction message. | **Pass.** The banned account displayed an account-access restriction message. |
| 21 | FR-8 | Check the entry points for a new and an existing patient. | A new patient can start registration, while a registered patient can access the sign-in option. | **Pass.** The interface provides Create an Account and Sign In options. |
| 22 | FR-8 | Open the patient profile and edit personal details. | The patient can update their own profile information, including name, email address, and phone number. | **Pass.** The tested profile allowed these personal details to be edited. |
| 23 | FR-8 | Attempt to access booking or rescheduling while the patient account is banned. | Restricted accounts cannot use appointment booking or rescheduling until access is restored. | **Pass.** The banned account was prevented from using the system and showed an access-restriction message. |
| 24 | FR-9 | Open the notification area and inspect the unread notification indicator. | The interface displays notifications and indicates how many are unread. | **Pass.** Notifications can be opened, and an unread count is displayed. |
| 25 | FR-9 | Open a notification and use the control to mark notifications as read. | The user can read notifications and mark an individual notification or all notifications as read. | **Pass.** The team confirmed that the Mark All as Read control can be used to clear the unread state. |
| 26 | FR-9 | Reschedule an appointment and inspect the notification received by the patient. | The system sends a relevant notification after the change and does not expose the patient's visit-reason description in the notification. | **Partially verified.** A notification related to a successful reschedule was observed. Notifications for every listed event type and the exclusion of visit-reason information were not separately documented as tested. |

## 3. Test outcome summary

| Outcome | Number of tests | Meaning |
|---|---:|---|
| Pass | 21 | The recorded observation supports the expected behavior for the tested scenario. |
| Partially verified | 4 | Some behavior was observed, but one or more parts of the combined expected result were not separately confirmed in the test record. |
| Not tested | 1 | The team did not execute the scenario. |
| **Total** | **26** | **All test scenarios listed in this document.** |

## 4. Testing notes and limitations

- The results describe the team's observations of the current prototype; they should not be interpreted as independent verification of the deployed or production system.
- A **Partially verified** result is used when the observation supports only part of a test's expected behavior. Additional testing is needed before treating the full criterion as confirmed.
- The follow-up booking scenario was not executed. It should be tested in a later test cycle to confirm that a new appointment does not overwrite a completed appointment.
- The test record does not establish performance under heavy traffic, security against external attacks, or reliability in a live hospital environment. Those areas require separate testing.

## 5. Conclusion

The prototype demonstrates the main patient and administrator workflows recorded in the functional requirements, including doctor availability, appointment booking, token generation, cancellation and rescheduling, doctor management, account restrictions, and notifications. Most recorded scenarios were successful. A small number require additional evidence, and the follow-up booking scenario remains untested. These items should be addressed in a future testing cycle before the system is considered ready for real-world deployment.
