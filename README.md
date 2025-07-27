# 📋 FieldTrace – 100% Offline Audit & Field Logging App

> A modular, fully offline-first Flutter app designed for capturing, managing, and exporting field audit data with support for media, dynamic forms, location tagging, and more. Built with MVVM + BLoC, SQLite, and feature-first architecture.

---

![Flutter](https://img.shields.io/badge/flutter-100%25-blue?logo=flutter)
![License](https://img.shields.io/github/license/your-username/fieldtrace)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![Offline-First](https://img.shields.io/badge/offline-first-important)

---

## 🧠 Project Highlights

- ✅ 100% **offline** – no backend required
- 📄 Dynamic **form builder** (JSON-based)
- 🗺️ Auto **location capture**
- 📸 **Media support** (photos, video, audio)
- 📤 Export logs as **PDF / CSV / ZIP**
- 🧠 **BLoC** + **MVVM** architecture
- 🗃️ **SQLite** for local data storage
- 🎯 Feature-first folder structure
- 🔐 Optional offline PIN-based auth

---

## 🏗️ Use Cases

| Sector | Use |
|--------|-----|
| 🧑‍🌾 Agriculture | Crop monitoring, fertilizer inspection |
| 🏗️ Infrastructure | Road & bridge checks, utility audits |
| 🛡️ Security | Guard patrolling logs, incident capture |
| 🚚 Logistics | Delivery proofs, damage reports |
| 🏥 Healthcare | Field medical or survey reports |
| 🏫 Education | School audits, facility inspections |

---

## 📲 Screenshots

| Log Creation | Form Input | PDF Export |
|--------------|------------|-------------|
| _Coming Soon_ | _Coming Soon_ | _Coming Soon_ |

---

## 🗂️ Features

### 🔹 Form Builder (Local JSON)
- Define forms with fields: text, dropdown, checkbox, date, number
- Stored locally in assets or file system
- Rendered dynamically

### 🔹 Media Support
- Attach photos, videos, or audio
- Optional image annotation
- All stored locally

### 🔹 Geo & Time Logging
- GPS coordinates (optional)
- Timestamp for every log
- Future support for geo-fencing

### 🔹 Local Auth (Optional)
- PIN-based login (stored encrypted)
- Multi-profile support coming soon

### 🔹 Exports
- **PDF**: formatted reports
- **CSV**: spreadsheet-friendly data
- **ZIP**: full bundle with media
- Share via Bluetooth, USB, or local storage

---


> Built using **feature-first architecture** with separation of concerns:
- **Model → View → ViewModel (BLoC)** pattern
- Modular, scalable and testable

---

## 🧰 Tech Stack

| Layer | Tools |
|-------|-------|
| UI | Flutter 3.x |
| Architecture | MVVM + BLoC |
| Database | SQLite (via `sqflite`) |
| State Management | `flutter_bloc` |
| Offline Storage | `path_provider`, `file`, `shared_preferences` |
| Media | `image_picker`, `camera`, `audioplayers` |
| Export | `pdf`, `csv`, `archive` |
| Location | `geolocator`, `geocoding` |

---
## ✅ Project Task Checklist for FieldTrace

A structured list of development tasks for building the offline-first dynamic form builder app. Tasks are ordered logically from setup → base features → UI → exports → enhancements → final polish.

---

### 🧱 Project Setup & Theming

- [ ] App folder structure using feature-first architecture
- [ ] Theme setup (Material 3 - dark/light toggle)
- [ ] Theme switcher (UI + persistent setting using shared_preferences)
- [ ] Custom app icon and splash screen

---

### 🔐 Authentication & Security

- [ ] PIN-based authentication
- [ ] Biometric authentication (fingerprint/face)
- [ ] Combine biometric + PIN logic
- [ ] Auto-lock app after inactivity (optional setting)

---

### 📄 Form Management (Admin UI)

- [ ] Form List Page UI (name, last updated, count, buttons for "view form", "view data", "archive")
- [ ] Archive List Page (list of archived forms)
- [ ] Create New Form screen (custom + templates)
- [ ] Dialog box: form actions (edit, delete, duplicate, archive)
- [ ] Drag & Drop fields for custom form creation
- [ ] Design Appointment Form (template with editable fields)
- [ ] Design Registration Form (template with editable fields)
- [ ] Design Attendance Form (template with editable fields)
- [ ] Design Custom Blank Form screen (user adds fields from scratch)

---

### 🧾 Form Field Types Implementation (Dynamic Engine)

- [ ] Field: Text Input
- [ ] Field: Text Area
- [ ] Field: Dropdown
- [ ] Field: Radio Buttons
- [ ] Field: Checkbox
- [ ] Field: Number / Decimal
- [ ] Field: Date & Time Pickers
- [ ] Field: Image Capture
- [ ] Field: Audio Recorder
- [ ] Field: File Upload
- [ ] Field: Signature Pad
- [ ] Field: Location (GPS)
- [ ] Field: Boolean / Toggle
- [ ] Field: Repeating Group
- [ ] Field: Calculated (Total = qty × rate)

---

### 📥 Form Submission Handling

- [ ] Save submission to local SQLite
- [ ] Store form data as JSON in DB
- [ ] Auto-create `created_at`, `updated_at`, `deleted_at`
- [ ] Form’s data list page (list of all submissions)
- [ ] Form’s data detail view (view/edit/delete)
- [ ] Form data deletion dialog (soft delete with undo)
- [ ] Media attachment support per submission

---

### 📦 Data Export & Auto Cleanup

- [ ] Export data to Excel (CSV)
- [ ] Export single form to PDF (structured layout)
- [ ] Export all form data (with media) as ZIP
- [ ] Auto-delete data older than X days (customizable)
- [ ] Before delete: export to local phone storage automatically
- [ ] Show dialog to inform user data was auto-exported & deleted

---

### ⚙️ Settings & Configurations

- [ ] Settings page UI
- [ ] Theme toggle (light/dark)
- [ ] Set auto-delete duration (7, 30, 60 days)
- [ ] Toggle biometric / PIN login
- [ ] Toggle GPS capture per form

---

### 🔎 Search, Filter & Dashboard

- [ ] Search forms by name
- [ ] Search submissions by field value
- [ ] Filter submissions by date range
- [ ] Dashboard page with summary (total forms, entries today, etc.)

---

### 📲 Share & Import

- [ ] Share exported files (ZIP, PDF, CSV)
- [ ] Import form schema from JSON file
- [ ] Export form schema to share template

---

### 🧪 Testing & Stability

- [ ] Form rendering unit tests
- [ ] Submission saving unit tests
- [ ] Export logic test (CSV + PDF)
- [ ] SQLite database tests
- [ ] Media & file test (attach, save, delete)
- [ ] App stability test (offline + restart scenarios)

---

> You can assign priorities (`P0`, `P1`, `P2`) or labels like `easy`, `medium`, `hard`, `beginner-friendly`, etc., on GitHub to better manage contributions.



## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/fieldtrace.git
cd fieldtrace


