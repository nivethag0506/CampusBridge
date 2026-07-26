# 📋 Product Requirements Document (PRD) — CampusBridge

- **Project Name**: CampusBridge
- **Document Version**: 1.0.0
- **Status**: Draft / Under Review
- **Author**: Technical Architecture Team

---

## 🎯 1. Executive Summary

CampusBridge is a centralized platform designed to solve the fragmentation in college campus ecosystems. It bridges the gap between four core user groups: **Students**, **Alumni**, **Faculty/TPO (Training & Placement Office)**, and **Admins**. 

By unifying mentorship requests, job referral boards, placement drives, event scheduling, and AI-powered resume review into a single intuitive interface, CampusBridge enhances student employability and alumni engagement.

---

## 👥 2. Target User Personas & Roles

| Role | Key Goal | Primary Actions |
| :--- | :--- | :--- |
| **Student** | Find mentors, prepare for interviews, apply to jobs/referrals, attend events. | Request 1-on-1 mentorship, submit resumes, join events, post queries. |
| **Alumni** | Give back to college, mentor junior students, share job referrals. | Accept mentorship slots, post referral listings, share interview experiences. |
| **TPO / Faculty** | Manage campus recruitment drives, track student applications. | Post official job drives, approve student profiles, monitor placement stats. |
| **System Admin** | Maintain platform security, user verification, system audit logs. | Approve alumni credentials, moderate content, manage system settings. |

---

## 🛠️ 3. Core Modules & Functional Requirements

### 3.1 Mentorship & Networking Module
- **M-1.1**: Alumni can define their availability (e.g., 30-min weekly slots) and areas of expertise (Software, Data, Product, Hardware, Higher Ed).
- **M-1.2**: Students can search alumni by company, role, skills, or graduation year and request 1-on-1 sessions.
- **M-1.3**: Automated calendar integration and notification system for confirmed sessions.

### 3.2 Job & Placement Drive Portal
- **J-2.1**: TPO can post official campus placement drives with eligibility criteria (CGPA, branch, passout year).
- **J-2.2**: Alumni can post internal job referrals for their current companies.
- **J-2.3**: Students can apply with 1-click using their verified platform resume profile.
- **J-2.4**: TPO export dashboard to download candidate lists in CSV/Excel formats.

### 3.3 Community & Knowledge Sharing Hub
- **C-3.1**: Discussion forum tagged by topics (e.g., `#InterviewExperience`, `#GATEPrep`, `#ProjectHelp`).
- **C-3.2**: Upvote, comment, and bookmark functionality.
- **C-3.3**: Verified badges for Alumni and Faculty answers.

### 3.4 Campus Events & Workshops
- **E-4.1**: Calendar view of upcoming webinars, guest lectures, and campus events.
- **E-4.2**: RSVP tracking with QR code generation for event check-in.

### 3.5 AI Career Assistant
- **A-5.1**: **AI Resume Reviewer**: Analyzes uploaded resume PDF against target job descriptions and highlights missing keywords/improvements.
- **A-5.2**: **Mock Technical Interviewer**: Interactive prompt-driven interview simulator based on specific domain roles.

---

## 🔒 4. Non-Functional Requirements

- **Security**: OAuth 2.0 / JWT authorization with encrypted passwords (bcrypt/Argon2). Role-Based Access Control (RBAC) enforced on API endpoints.
- **Verification**: Student roll number validation; Alumni LinkedIn URL + verification approval workflow.
- **Performance**: Page load time < 2.0s; API response time < 200ms (P95).
- **Scalability**: Support for up to 50,000 active users per university campus.
- **Compliance**: GDPR / Data Privacy compliance regarding student email and contact information sharing.

---

## 📈 5. Success Metrics

1. **Mentorship Sessions**: >500 successful student-alumni sessions conducted per semester.
2. **Placement Conversion**: 25% increase in alumni-driven referral applications.
3. **Daily Active Users (DAU)**: >60% student engagement during peak recruitment season.
