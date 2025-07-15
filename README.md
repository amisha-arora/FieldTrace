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

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/fieldtrace.git
cd fieldtrace


