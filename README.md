
# Kharis Lost & Found
<p align="center">
  <strong>A digital lost & found platform for churches and multi-branch organisations.</strong>
</p>
<p align="center">
  Report, discover, claim and return lost property through one simple platform.
</p>
<p align="center">
  <a href="https://ruthhilary.github.io/KharisLost-Found/">
    <img src="https://img.shields.io/badge/Live%20Demo-6C4AB6?style=for-the-badge" alt="Live Demo">
  </a>
  <a href="https://github.com/Ruthhilary/KharisLost-Found">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github" alt="GitHub">
  </a>
  <img src="https://img.shields.io/badge/Status-Active%20Development-2EA44F?style=for-the-badge" alt="Active Development">
</p>
<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#features">Features</a> •
  <a href="#technology">Technology</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#roadmap">Roadmap</a>
</p>
---
# Overview
**Kharis Lost & Found** is a responsive web application designed to modernise how churches and multi-branch organisations manage lost property.
Instead of relying on paper records, group messages or disconnected spreadsheets, Kharis provides a structured workflow for reporting, discovering, claiming and returning belongings.
### Core workflow
```text
Report → Discover → Claim → Verify → Return

The platform provides separate experiences for members and administrators, while supporting multiple branches within the organisation.

⸻

Live Application

Launch Kharis Lost & Found →⁠￼

The current application is deployed using GitHub Pages and is accessible directly from a modern web browser.

⸻

Features

Member Experience

Members can:

* Report lost or found items
* Upload photographs
* Add item descriptions and locations
* Select a branch
* Browse reported items
* Search and filter items
* Submit claims
* Add claim notes
* Ask questions about items
* Request a branch change
* Change language preferences
* Use light or dark mode

⸻

Administration

Administrators can:

* View reported items
* Search and filter missing items
* Review item details
* View uploaded photographs
* Review member claims
* Assign items to members
* Mark items as donated
* Return incorrectly claimed items to Missing Items
* View unanswered questions
* Respond to member questions
* Manage branch-specific information
* Receive new-item notifications
* Configure email notifications
* Manage application settings

⸻

Multi-Branch Support

Kharis is designed around a multi-branch organisation structure.

Users select the branch they belong to, while administrators can manage information relevant to their branch.

The main administrator can oversee activity across the wider organisation.

Organisation
│
├── Branch 01
│   ├── Members
│   └── Administrators
│
├── Branch 02
│   ├── Members
│   └── Administrators
│
└── Branch 03
    ├── Members
    └── Administrators

⸻

Responsive Design

Kharis is designed to work across different screen sizes.

Platform	Support
Mobile	✓
iPhone	✓
iPad	✓
Tablet	✓
Laptop	✓
Desktop	✓

The mobile interface includes:

* Touch-friendly controls
* Larger buttons
* Bottom-sheet modals
* Horizontal table scrolling
* Swipeable categories
* Responsive item cards
* iOS-friendly input sizing
* Safe-area support

⸻

Image Uploads

Phone photographs can be several megabytes in size and can quickly consume browser storage.

Kharis automatically compresses uploaded images before saving them.

Select Image
     │
     ▼
Compress Image
     │
     ▼
Attempt Save
     │
     ├── Success ──→ Save Item
     │
     └── Failure
            │
            ▼
      Compress Again
            │
            ▼
        Save / Alert

If storage remains unavailable, the application informs the user instead of silently adding an item that will disappear after refresh.

⸻

Notifications

Administrators can receive in-app alerts when members report items.

The notification flow includes:

New Report
    │
    ▼
Notification Badge
    │
    ▼
Dashboard Alert
    │
    ▼
Toast Notification
    │
    ▼
Confirmation Sound

Optional email notifications can be configured using EmailJS⁠￼.

Email notifications can include:

Field	Description
to_email	Administrator email
item_name	Reported item
location	Item location
branch	Relevant branch
reported_by	Reporting member
day	Report date

⸻

Internationalisation

Kharis currently supports nine languages:

Language	Status
English	✓
French	✓
Spanish	✓
German	✓
Swedish	✓
Scottish Gaelic	✓
Krio	✓
Twi	✓
Patois	✓

Translation note: Twi, Krio and Patois translations should be reviewed by native speakers before production deployment.

⸻

User Interface

The interface includes:

* Light and dark themes
* Responsive navigation
* Search and filtering
* Interactive item cards
* Toast notifications
* Confirmation sounds
* Mobile-friendly dialogs
* Persistent settings
* Scrollable navigation
* Responsive layouts

User preferences such as language, theme, active tab and relevant filters can persist between sessions.

⸻

Technology

Frontend

Services

Core technologies

* HTML5 — Application structure
* CSS3 — Layout and responsive design
* JavaScript — Application logic and interactions
* Browser Storage — Local persistence
* Client-side image compression — Optimised uploads
* EmailJS — Optional email notifications
* GitHub Pages — Static deployment

⸻

Architecture

The current release is intentionally lightweight and primarily browser-based.

                    Kharis Lost & Found
                            │
              ┌─────────────┴─────────────┐
              │                           │
          Members                   Administrators
              │                           │
              └─────────────┬─────────────┘
                            │
                     Web Application
                            │
                ┌───────────┴───────────┐
                │                       │
         Browser Storage             EmailJS
                │                       │
           Local Data              Email Alerts

⸻

Data Storage

The current version stores application data locally within the user’s browser.

This keeps the application lightweight and allows it to run without a dedicated backend.

However, local browser storage means that data created on one device is not automatically synchronised with another device.

For example:

Member's Phone
      │
      ▼
Report Item
      │
      ▼
Browser Storage
      │
      X
      │
      ▼
Admin Laptop

The administrator can receive an email notification about a report through EmailJS, but the actual application data remains local to the browser.

A shared backend will be required for true cross-device synchronisation.

⸻

Roadmap

Completed

* [x]	Lost and found reporting
* [x]	Item search
* [x]	Item filtering
* [x]	Claims
* [x]	Questions and replies
* [x]	Administrative management
* [x]	Multi-branch structure
* [x]	Responsive design
* [x]	Mobile support
* [x]	iPad support
* [x]	Dark mode
* [x]	Image compression
* [x]	Multilingual interface
* [x]	Admin notifications
* [x]	EmailJS integration
* [x]	Persistent settings

Planned

* [ ]	Shared backend
* [ ]	Central database
* [ ]	Cross-device synchronisation
* [ ]	Cloud image storage
* [ ]	Secure authentication
* [ ]	Real-time updates
* [ ]	Push notifications
* [ ]	Advanced analytics
* [ ]	Automated item matching
* [ ]	AI-powered image recognition

⸻

Getting Started

Clone the repository

git clone https://github.com/Ruthhilary/KharisLost-Found.git

Navigate to the project

cd KharisLost-Found

Run locally

python3 -m http.server 8000

Open the application at:

http://localhost:8000

⸻

Project Structure

KharisLost-Found/
│
├── index.html
├── README.md
└── ...

⸻

Current Limitations

Kharis Lost & Found is currently an active development project.

The main architectural limitation is the current browser-based storage model.

Because application data is stored locally:

* Data is not automatically shared between devices.
* Reports submitted on a member’s phone are not automatically visible on an administrator’s laptop.
* EmailJS can notify administrators of new reports.
* A central backend is required for multi-device synchronisation.

The application is being progressively tested across mobile, tablet and desktop environments.

⸻

Future Direction

The long-term goal is to evolve Kharis from a lightweight browser application into a fully synchronised platform.

Future infrastructure could provide:

                  Central Backend
                       │
        ┌──────────────┼──────────────┐
        │              │              │
     Members        Admins         Branches
        │              │              │
        └──────────────┼──────────────┘
                       │
                Shared Database
                       │
             ┌─────────┴─────────┐
             │                   │
        Cloud Storage       Notifications

This would enable shared data, secure authentication, cloud image storage, real-time updates and reliable cross-device access.

⸻

Vision

Kharis Lost & Found was built around a simple problem:

What happens when someone loses something at church?

The goal is to replace scattered messages, paper records and manual tracking with one structured digital experience.

REPORT
   ↓
DISCOVER
   ↓
CLAIM
   ↓
VERIFY
   ↓
RETURN

Kharis aims to make lost property management simple for members and manageable for administrators.


⸻

Project Status

Active Development

Kharis Lost & Found is an evolving project currently being developed and tested across modern browsers and devices.

⸻

<p align="center">
  <strong>Kharis Lost & Found</strong>
  <br>
  <sub>Turning lost property into a structured digital experience.</sub>
</p>
<p align="center">
  <a href="https://ruthhilary.github.io/KharisLost-Found/">
    View the live application →
  </a>
</p>
```
