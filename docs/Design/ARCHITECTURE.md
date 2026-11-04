# CareFlow OPD — Current Prototype Architecture

This diagram describes the **current repository implementation** documented in the project README. It is a frontend-only web prototype built with HTML, CSS and JavaScript.

```mermaid
flowchart TB
    subgraph USERS["USERS"]
        PATIENT["Patient"]
        ADMIN["Admin"]
    end

    subgraph BROWSER["WEB BROWSER"]
        subgraph UI["PRESENTATION LAYER"]
            LOGIN["Sign-in / Registration UI"]
            PATIENT_UI["Patient Portal"]
            ADMIN_UI["Admin Workspace"]
            CSS["styles.css<br/>Layout and responsive styling"]
        end

        subgraph LOGIC["FRONTEND LOGIC"]
            JS["script.js<br/>Demo data and interactive behavior"]
            AUTH["Demo sign-in and role selection"]
            PATIENT_FEATURES["Patient features<br/>Doctor browsing, booking, tokens,<br/>queue view, cancel/reschedule"]
            ADMIN_FEATURES["Admin features<br/>Dashboard, patient accounts,<br/>doctor and schedule management"]
            NOTIFICATIONS["Notification UI"]
        end

        STORAGE[("Browser Local Storage<br/>Demo data saved in this browser")]
    end

    STANDALONE["CareFlow_OPD_Standalone.html<br/>Alternative single-file prototype"]

    PATIENT --> LOGIN
    ADMIN --> LOGIN
    LOGIN --> AUTH
    AUTH --> PATIENT_UI
    AUTH --> ADMIN_UI

    PATIENT_UI --> PATIENT_FEATURES
    ADMIN_UI --> ADMIN_FEATURES
    PATIENT_UI --> NOTIFICATIONS
    ADMIN_UI --> NOTIFICATIONS

    PATIENT_FEATURES --> JS
    ADMIN_FEATURES --> JS
    NOTIFICATIONS --> JS
    CSS -. styles .-> UI
    JS <--> STORAGE

    STANDALONE -. "Alternative: contains HTML, CSS and JavaScript together" .-> BROWSER
```

## Main components

| Component | Responsibility |
|---|---|
| `index.html` | Main web page and application structure |
| `styles.css` | Layout, visual styling and responsive design |
| `script.js` | Demo data and interactive frontend behavior |
| Browser Local Storage | Saves demo changes in the current browser |
| `CareFlow_OPD_Standalone.html` | Alternative single-file version containing its own HTML, CSS and JavaScript |

## User roles

- **Patient:** Register/sign in, browse doctors and schedules, book appointments, view tokens and appointment status, and cancel or reschedule eligible appointments.
- **Admin:** View dashboard information, manage patient account access, and add, edit or deactivate doctor profiles and schedules. The current README states that appointment and token statuses are read-only for Admin.

## Current implementation limitations

- No real backend server or production database is connected.
- Authentication is demonstrated in the frontend; it is not a production authentication service.
- Local Storage is browser-specific and does not synchronize data between users, browsers or computers.
- Appointment and token status behavior is simulated; the prototype does not provide real-time queue operations or notifications.
- Do not enter real patient, medical or personal information.

## Intended production direction

A production version would need a server-side application/API, secure authentication and authorization, a shared persistent database, and server-controlled appointment and token workflows. Those components are **future architecture**, not part of the current repository prototype.
