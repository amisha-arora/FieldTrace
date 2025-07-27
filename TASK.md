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

## ✅ Task Categorization Criteria

| Criteria                         | Small Task 🟢          | Medium Task 🟡               | Hard Task 🔴                         |
|----------------------------------|-------------------------|------------------------------|--------------------------------------|
| 💻 Code Complexity               | 1–3                     | 4–6                          | 7–10                                 |
| ⏱ Estimated Time to Complete    | < 2 hours               | 2–5 hours                    | > 5–10+ hours                        |
| 🧠 Required Knowledge Depth      | Beginner                | Intermediate                 | Advanced                             |
| 🔁 Feature Integration           | Minimal                 | One feature module           | Multiple modules                     |
| 📚 Documentation Needed          | No or minimal           | Yes                          | Yes + architecture notes             |



