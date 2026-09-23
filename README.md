Kharis Lost & Found

<p align="center">
  <strong>A modern digital lost & found platform for churches and multi-branch organisations.</strong>
</p>
<p align="center">
  <a href="https://ruthhilary.github.io/KharisLost-Found/">
    <img src="https://img.shields.io/badge/LIVE%20DEMO-6C4AB6?style=for-the-badge" alt="Live Demo">
  </a>
  <a href="https://github.com/Ruthhilary/KharisLost-Found">
    <img src="https://img.shields.io/badge/GITHUB-181717?style=for-the-badge&logo=github" alt="GitHub">
  </a>
  <img src="https://img.shields.io/badge/STATUS-ACTIVE%20DEVELOPMENT-2EA44F?style=for-the-badge" alt="Status">
</p>
<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#features">Features</a> •
  <a href="#technology">Technology</a> •
  <a href="#roadmap">Roadmap</a> •
  <a href="#getting-started">Getting Started</a>
</p>

⸻

#Overview

Kharis Lost & Found is a responsive web application designed to modernise the way churches and multi-branch organisations manage lost property.

Instead of relying on paper records, group chats or disconnected spreadsheets, Kharis provides a structured digital workflow for reporting, discovering, claiming and returning lost belongings.

The workflow

Report → Discover → Claim → Verify → Return

The platform is designed with two primary experiences:

* Members can report, search, question and claim items.
* Administrators can manage reports, claims, branches and member interactions.

⸻

Live Demo

<p align="center">

→ Launch Kharis Lost & Found

</p>

The application is deployed using GitHub Pages and can be accessed directly from a modern web browser.

⸻

Features

Member Experience

Report an Item

Members can submit lost or found items with:

* Item name
* Category
* Description
* Location
* Branch
* Photograph
* Additional notes

Search & Discovery

Members can:

* Search reported items
* Filter by category
* Browse item cards
* View item information
* Ask questions about items

Claims

Members can identify an item as theirs and submit a claim.

Claims can include additional notes to help administrators verify ownership.

⸻

Administration

Item Management

Administrators can:

* View reported items
* Search and filter items
* View uploaded photographs
* Review item information
* Assign items to members
* Mark items as donated
* Return incorrectly claimed items
* Manage branch-specific information

Questions & Replies

Members can ask questions about an item.

Administrators can view unanswered questions and respond directly from the item management interface.

Admin Notifications

When a member reports an item, administrators can receive:

* Notification badges
* Dashboard alerts
* Toast notifications
* Confirmation sounds

Optional email notifications are available through EmailJS.

⸻

Multi-Branch Support

Kharis Lost & Found is designed for organisations operating across multiple branches.

Users select their branch when using the platform, while administrators can manage information relevant to their branch.

The main administrator can oversee activity across the wider organisation.

                         KHARIS
                           │
              ┌────────────┴────────────┐
              │                         │
           BRANCH 1                  BRANCH 2
              │                         │
        ┌─────┴─────┐             ┌─────┴─────┐
        │           │             │           │
      Users       Admins        Users       Admins

⸻

Responsive Design

Kharis is designed to work across:

Platform	Support
📱 Mobile	✓
📲 iPhone	✓
📲 iPad	✓
💻 Laptop	✓
🖥️ Desktop	✓

Mobile

The interface includes:

* Touch-friendly controls
* Larger buttons
* Bottom-sheet modals
* Horizontal table scrolling
* Swipeable categories
* Two-column item cards
* iOS-safe input sizing
* Safe-area support

Tablet

The layout automatically adapts to tablet-sized screens.

Desktop

Administrators receive a larger workspace for managing reports, claims and branches.

⸻

Dark Mode

Kharis includes a dedicated dark interface designed for comfortable use in low-light environments.

The interface remembers the user’s selected appearance so it remains consistent after refreshing the page.

⸻

Smart Image Uploads

Large photographs from mobile devices can quickly consume browser storage.

Kharis automatically compresses uploaded images before saving them.

┌───────────────────┐
│   Select Image    │
└─────────┬─────────┘
          ↓
┌───────────────────┐
│ Compress Image    │
└─────────┬─────────┘
          ↓
┌───────────────────┐
│ Attempt Save      │
└─────────┬─────────┘
          ↓
     ┌────┴────┐
     │         │
   Success   Storage Full
     │         │
     ↓         ↓
   Saved    Compress Again
               │
               ↓
          Save / Alert

This prevents large phone photographs from silently causing submissions to fail.

⸻

Notifications

Kharis supports both in-app and optional email notifications.

In-App Notifications

When a new item is reported:

New Report
    ↓
Notification Badge
    ↓
Dashboard Alert
    ↓
Toast
    ↓
Confirmation Sound

Email Notifications

Administrators can configure EmailJS to receive report notifications.

Available information includes:

Field	Description
to_email	Administrator email
item_name	Reported item
location	Where it was found
branch	Relevant branch
reported_by	Reporting member
day	Report date

⸻

Internationalisation

Kharis supports multiple languages.

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

Note: Twi, Krio and Patois translations should be reviewed by native speakers before production deployment.

⸻

Technology

Frontend

Services

Core Technologies

* HTML5 — Application structure
* CSS3 — Responsive interface and visual design
* JavaScript — Application logic and interactions
* Browser Storage — Local persistence
* EmailJS — Optional administrator email notifications
* GitHub Pages — Static deployment

⸻

Architecture

The current version is intentionally lightweight and primarily browser-based.

                    ┌─────────────────────┐
                    │  KHARIS LOST & FOUND │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
          ┌──────▼──────┐             ┌──────▼──────┐
          │   MEMBERS   │             │    ADMINS   │
          └──────┬──────┘             └──────┬──────┘
                 │                           │
                 └─────────────┬─────────────┘
                               │
                       ┌───────▼───────┐
                       │ WEB APP       │
                       └───────┬───────┘
                               │
                    ┌──────────┴──────────┐
                    │                     │
             ┌──────▼──────┐       ┌──────▼──────┐
             │   Browser   │       │   EmailJS   │
             │   Storage   │       │   Alerts    │
             └─────────────┘       └─────────────┘

⸻

Data & Storage

The current version stores application data locally within the browser.

This makes the application lightweight and allows it to operate without a dedicated backend.

However, local browser storage means that information created on one device is not automatically synchronised with another device.

For example:

Member Phone
     │
     ▼
Report Item
     │
     ▼
Browser Storage
     │
     X
     │
Admin Laptop

Email notifications can alert an administrator that a report was created, but shared data synchronisation will require a central backend.

⸻

Roadmap

Completed

* [x]	Lost & found reporting
* [x]	Item search
* [x]	Item filtering
* [x]	Claims
* [x]	Questions and replies
* [x]	Administrative management
* [x]	Multi-branch structure
* [x]	Responsive design
* [x]	iPhone support
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

Clone the Repository

git clone https://github.com/Ruthhilary/KharisLost-Found.git

Navigate to the Project

cd KharisLost-Found

Run Locally

python3 -m http.server 8000

Then open:

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

The main architectural limitation is that application data is stored locally in the browser.

A future backend will provide:

* Centralised data
* Cross-device synchronisation
* Secure authentication
* Cloud image storage
* Data backups
* Real-time updates
* Improved scalability

⸻

Vision

Kharis Lost & Found was created around a simple question:

What happens when someone loses something at church?

The answer should not have to be:

“Ask around and hope someone knows.”

Kharis turns that process into a structured digital workflow.

       REPORT
          ↓
       DISCOVER
          ↓
        CLAIM
          ↓
        VERIFY
          ↓
        RETURN

The long-term vision is to create a reliable digital infrastructure for lost property management across churches and multi-branch 


⸻

License

This project is currently maintained as a private development project.

© 2026 Kharis Church. All rights reserved.

⸻

<p align="center">
  <strong>Kharis Lost & Found</strong><br>
  <sub>Turning lost property into a structured digital experience.</sub>
</p>
