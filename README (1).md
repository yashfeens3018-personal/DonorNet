# DonorNet 🩸

> A blood donation platform that connects **patients**, **donors** and **blood banks**, with **admin** oversight.
> **This repository contains the UI/UX prototype (Figma wireframes) and the QA test cases. It is not a working app yet.**

---

## 📖 Overview

In an emergency, finding the right blood type quickly is hard. Patients don't know which blood banks have stock, and blood banks have no fast way to reach donors when supplies run low.

**DonorNet** is a mobile app concept that solves this by bringing four kinds of users onto one platform. Every patient and donor account is **verified before approval**: users upload a proof document (e.g. CNIC) and a recent CBC (Complete Blood Count) report at sign-up, and an admin reviews the account.

## 👥 User Roles

| Role | What they do |
|------|--------------|
| 🧑‍⚕️ **Patient** | Signs up with proof and CBC report, waits for admin approval, then searches for donors and blood banks and sends blood requests. |
| 🩸 **Donor** | Signs up with blood type and CBC report, waits for admin approval, browses blood banks, and receives notifications when blood is urgently needed. |
| 🏥 **Blood Bank** | Manages its blood stock, accepts or rejects patient requests, and sends blood requests out to donors when stock runs low. Accounts are created by the admin. |
| 🛡️ **Admin** | Approves or declines patient and donor sign-ups, adds new blood banks, and monitors the platform through a dashboard. |

## ✨ Features (Designed)

### Authentication (all roles)
- Splash screen and login with email or username
- Forgot password flow using an **OTP sent by email**, followed by setting a new password
- Strong password rules: 8+ characters, at least 1 number and 1 special character
- Clear validation messages for weak passwords, missing fields, invalid email format, and duplicate email or username

### Patient
- Sign-up with username, email, password, address, phone, city, blood type, proof document and latest CBC
- "Waiting for approval" status after sign-up
- **Browse Donors:** search by username, filter by availability, blood type, distance and location
- **Browse Blood Banks:** search by name, filter by availability, blood type, distance and location
- Profile, addresses, past requests and settings

### Donor
- Sign-up with the same verification documents as patients
- Browse blood banks with search and filters
- Receives notifications when a blood bank sends an urgent request
- Profile, addresses and settings

### Blood Bank
- **Patient Requests:** view requests (requester, date, urgency, blood type) and **Accept / Reject** them, with confirmation pop-ups. Accepting deducts units from inventory and rejecting notifies the requester
- **My Stocks:** view and edit blood stock levels, with low-stock warnings
- **Request for Blood:** choose blood types, urgency, time frame and venue, then notify donors
- **Request History** of all past requests

### Admin
- **Approve Patient Signups** and **Approve Donor Signups:** review details and approve or decline
- **Add a Blood Bank:** name, email, phone, address, city, operating hours, admin in-charge and password
- **Admin Dashboard** with charts and tables
- Search across sign-up requests

## 🎨 Wireframes

The entire front end was designed as a wireframe/prototype in Figma, with separate flows for each role.

🔗 **[Open the Figma prototype](https://www.figma.com/design/1xQh4ZnslJlfxPQaSRUvbk/wireframes?node-id=0-1&t=rfybNPnImBz7yMC7-0)** (also saved in [`docs/wireframes.md`](docs/wireframes.md))

## ✅ Test Cases

Manual test cases were written for the main flows of all four roles. Each case includes an ID, scenario, steps, test data, expected result and pre-requisites, with blank "Actual Result" and "Pass/Fail" columns to fill in during testing.

| Area | Roles Covered |
|------|---------------|
| Patient and donor sign-up | Patient, Donor |
| Login (valid, invalid, empty fields) | All |
| Forgot password with OTP | All |
| Search and filter donors | Patient |
| Search and filter blood banks | Patient, Donor |
| Accept / reject patient requests | Blood Bank |
| Making blood requests | Blood Bank |
| Admin login, sign-up approvals, add blood bank, dashboard, search | Admin |

📄 **Files:**
- [`docs/test-cases/test_cases.pdf`](docs/test-cases/test_cases.pdf): ready to read
- [`docs/test-cases/test_cases.tex`](docs/test-cases/test_cases.tex): LaTeX source

To compile the PDF yourself:

```bash
cd docs/test-cases
pdflatex test_cases.tex
```

## 🗂️ Repository Structure

```
DonorNet/
├── README.md
├── LICENSE
└── docs/
    ├── wireframes.md          # Link to the Figma prototype
    └── test-cases/
        ├── test_cases.tex     # LaTeX source
        └── test_cases.pdf     # Compiled PDF
```

## 🛠️ Tools Used

- **Figma:** wireframing and prototyping
- **LaTeX:** test case documentation

## 🚧 Project Status & Roadmap

- [x] UI wireframes / prototype in Figma for all four roles
- [x] Test cases for the main flows
- [ ] Frontend implementation
- [ ] Backend and database (users, approvals, stock, requests)
- [ ] OTP email service and push notifications
- [ ] Location services for distance-based search
- [ ] Testing and deployment

## 👥 Team

<!-- TODO: replace with your names -->
| Name | Role |
|------|------|
| Your Name | UI/UX Design |
| Teammate | Test Cases / Documentation |

## 📄 License

MIT License. See [LICENSE](LICENSE). Change this if your course or team requires something else.
