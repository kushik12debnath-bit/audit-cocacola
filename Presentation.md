# Coca-Cola Tansi Beverage — Audit Management Platform

### Full Presentation for Client Demonstration

---

## Slide 1 — Title

**GO AUDIT — Internal Audit & Quality Management Platform**
Coca-Cola Tansi Beverage • Official Audit Hub

* Secure • Multi-role • Real-time • Enterprise-grade
* Live demo: https://audit-cocacola.vercel.app/login

---

## Slide 2 — The Problem

**Challenges in manual audit management**

* Paper-based checklists — slow, error-prone, hard to track
* No real-time visibility of audit progress across teams
* Evidence (photos, documents, audio) scattered across devices
* Role confusion — who can approve, who can edit, who can report
* Reports generated late, inconsistent format, hard to audit later
* No analytics to spot recurring non-conformances

**Goal:** One platform for the whole audit lifecycle — from planning to sign-off.

---

## Slide 3 — The Solution

**GO AUDIT — a single, branded, secure audit hub**

* Coca-Cola Tansi Beverage branded experience
* Multi-role access: Admin, Manager, Supervisor, Auditor
* Real-time progress tracking with collaborator allocation
* Evidence capture (photo, document, audio, video)
* Executive-grade reports (on-screen + PDF + CSV)
* Analytics dashboard with KPIs, charts, filters

---

## Slide 4 — Brand Identity

**Coca-Cola Tansi Beverage — Official Audit Hub**

* Signature Coca-Cola Red `#F40009` + deep charcoal `#0F172A`
* Official Coca-Cola script logo in navbar, login, and report header
* Crisp white cards, soft shadows, glassmorphic accents
* Consistent footer: copyright, version v2.1.0, sync status
* "CONFIDENTIAL" watermark on generated reports

---

## Slide 5 — Security & Role-Based Access

**Who can do what**

| Role | Audits | Approvals | Admin | Library | Reports |
|------|--------|-----------|-------|---------|---------|
| Admin | ✓ | ✓ | ✓ | ✓ | ✓ |
| Manager | ✓ | ✓ | — | — | ✓ |
| Supervisor | ✓ | ✓ | — | — | ✓ |
| Auditor | ✓ (own/assigned) | — | — | — | ✓ |

* JWT authentication, 7-day expiring tokens
* Passwords hashed with bcrypt (72-byte guard)
* Invalid IDs rejected with 400 (no 500 crashes)
* Disabled/rejected accounts cannot log in

---

## Slide 6 — Secure Auditor Signup (Invite-Code Flow)

**Three mandatory credentials**

1. Pre-allocated Official Email ID
2. Password (with strength meter + confirmation match)
3. Special Registration / Invite Code

**Account state machine**

* On signup → `PENDING_APPROVAL` (holding screen, no dashboard access)
* Admin / Manager / Supervisor see a **Pending Approvals** queue
* Verify email + invite code → **Approve** or **Reject**
* On approval → immediate login + dashboard access

**Invite codes** are generated/allocated by approvers and bindable to a specific email.

---

## Slide 7 — Real-Time Audit Progress & Collaboration

**Live progress on every audit**

* Prominent progress bar at the top of the Audit Workspace
* Exact completion % (0–100), completed vs. total checklist items
* Stage badge: **Initialized → In Progress → Under Review → Completed**
* Last-updated timestamp
* Collaborator allocation: multiple profiles can view and contribute
* Each contribution recalculates the shared progress bar

---

## Slide 8 — Audit Workflow (Step by Step)

1. **New Audit** — pick standard (ISO 45001 / 9001 / 14001 / FSSC 22000), fill plant, auditor, auditee, scope
2. **Workspace** — answer clause-by-clause questions
3. **Evidence** — attach photos, documents, audio, video
4. **Save / Complete** — 100% completion required to complete
5. **Report** — View Report, CAPA Report
6. **Export** — Full PDF, Findings-only PDF, Text report, CAPA CSV

---

## Slide 9 — Evidence & CAPA Management

**Evidence capture**

* Camera photo, gallery photo, document picker, audio recording, video
* Base64 storage with metadata (filename, type, timestamp)
* Openable attachments in the report view (fullscreen photo viewer)

**CAPA (Corrective Action Plan)**

* Online CAPA preparation by auditee/auditor
* Correction, root cause, corrective action, responsible person, target date, status
* Closure evidence photos
* Presentable CAPA report view + PDF download

---

## Slide 10 — Executive-Grade Reports

**On-screen + exported (PDF / CSV / Print)**

* Header: Coca-Cola logo + "Coca-Cola Tansi Beverage — Official Audit Report"
* Audit metadata card: Audit ID, timestamp, allocated profiles, approving supervisor/manager, overall compliance score
* Visual score gauge (green/amber/red by compliance)
* Section-wise compliance tables (Compliant / Minor NC / Major NC)
* Contributor log + digital sign-off blocks
* CONFIDENTIAL watermark

---

## Slide 11 — Analytics Dashboard

**KPI summary cards**

* Total Audits Conducted
* Completed Audits
* Active / In-Progress Audits
* Pending Approvals
* Average Compliance Rate

**Visualizations**

* Bar graph: 8-week audit volume trend
* Donut chart: audits by status (completed / in-progress / draft / flagged)
* Category distribution by standard
* Filters: date range, auditor, status → live chart update
* One-click export: CSV summary

---

## Slide 12 — Technical Architecture

| Layer | Technology |
|-------|-----------|
| Frontend | Expo Router + React Native (Web) |
| Backend | FastAPI (Python) |
| Database | MongoDB (mongomock fallback for preview) |
| Auth | JWT + bcrypt |
| Reports | expo-print + browser print (multi-page) |
| Hosting | Vercel (frontend + serverless API) |

**Endpoints**: 40+ REST endpoints covering auth, users, questionnaires, audits, CAPA, analytics, reports.

---

## Slide 13 — Live Demo

**Try it yourself**

* URL: https://audit-cocacola.vercel.app/login
* Admin login: `SRD` / `7550`
* Register a new auditor → approve → create audit → answer → report → analytics

**Demo walkthrough (5 minutes)**

1. Login as Admin (SRD)
2. Dashboard → Audits → New Audit
3. Answer 2–3 questions, attach a photo
4. Save → View Report → download PDF
5. Analytics → filter → export CSV
6. Approvals tab → generate invite code → register new auditor → approve

---

## Slide 14 — Roadmap & Next Steps

**Delivered in this release (v2.1.0)**

* Multi-role RBAC with invite-code signup + approval
* Real-time progress + collaboration
* Executive reports + CAPA
* Analytics dashboard

**Next**

* Persistent MongoDB (Atlas) for production data
* Mobile builds (iOS/Android via Expo)
* CAPA status dashboard on audit cards
* Audit plan module & startup performance
* Migrate deprecated expo-av → expo-audio

---

## Slide 15 — Thank You

**Coca-Cola Tansi Beverage — Official Audit Hub**

Contact: Saila Ruidas • Emergent Lab

Questions?
