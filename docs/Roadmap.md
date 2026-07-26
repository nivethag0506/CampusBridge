# 🗺️ Project Roadmap & Release Plan — CampusBridge

This document defines the development phases, milestones, and release schedule for CampusBridge.

---

## 📌 Release Milestones Overview

```mermaid
gantt
    title CampusBridge Project Schedule
    dateFormat  YYYY-MM-DD
    section Phase 1: Foundation
    Requirements & Architecture Docs :done, p1, 2026-07-01, 2026-07-15
    DB Schema & API Design          :active, p2, 2026-07-15, 2026-07-31
    section Phase 2: Core Platform
    Auth & User Management          :p3, 2026-08-01, 2026-08-15
    Mentorship Module               :p4, 2026-08-15, 2026-08-31
    Placement & Job Portal          :p5, 2026-09-01, 2026-09-20
    section Phase 3: AI & Analytics
    AI Resume & Interview Suite     :p6, 2026-09-20, 2026-10-10
    TPO Analytics Dashboard         :p7, 2026-10-10, 2026-10-25
    section Phase 4: Launch & Scale
    UAT & Beta Testing              :p8, 2026-10-25, 2026-11-10
    Production Deployment           :p9, 2026-11-15, 2026-11-20
```

---

## 🚀 Detailed Phase Breakdown

### Phase 1: Planning & Foundation (Current)
- Complete directory setup, architecture specs, ERD schema, and API contracts.
- Initialize Next.js frontend repository and Node.js/FastAPI backend framework.

### Phase 2: Core Platform & RBAC
- Implement JWT / OAuth authentication with domain-specific verification (`@univ.edu`).
- Build Student and Alumni profile dashboards.
- Launch 1-on-1 Mentorship booking flow with email notifications.
- Launch Job & Referral Board for TPO drives and alumni job posts.

### Phase 3: AI Engine & Advanced Features
- Integrate AI Resume Reviewer API (PDF parsing + LLM analysis).
- Launch AI Mock Technical Interviewer simulator.
- Build TPO Placement Analytics dashboard with CSV export capabilities.

### Phase 4: Security Audit, Testing & Deployment
- Execute end-to-end load testing (k6) and vulnerability scanning.
- Deploy staging environment on AWS / Vercel + Railway.
- Conduct User Acceptance Testing (UAT) with pilot student & alumni group.
