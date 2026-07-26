# ✨ Feature Matrix & Module Breakdown — CampusBridge

This document outlines the detailed feature capabilities offered across the CampusBridge ecosystem.

---

## 🎯 Feature Matrix by User Role

| Feature Module | Student | Alumni | Faculty / TPO | System Admin |
| :--- | :---: | :---: | :---: | :---: |
| **Profile & Portfolio** | ✅ | ✅ | ✅ | ✅ |
| **Mentorship Request & Calendar** | ✅ (Book) | ✅ (Host) | 👁️ (View) | ⚙️ (Manage) |
| **Job Referral Board** | ✅ (Apply) | ✅ (Post) | ✅ (Post/Track) | ⚙️ (Moderate) |
| **AI Resume ATS Reviewer** | ✅ | ❌ | ❌ | ⚙️ (Configure) |
| **AI Mock Interviewer** | ✅ | ❌ | ❌ | ⚙️ (Configure) |
| **Campus Events & RSVP** | ✅ (Join) | ✅ (Host/Join)| ✅ (Create) | ⚙️ (Moderate) |
| **Community Q&A Forum** | ✅ | ✅ (Verified) | ✅ (Verified) | ⚙️ (Moderate) |
| **Placement Analytics** | ❌ | ❌ | ✅ (Export) | ✅ |

---

## 💡 Feature Module Summaries

### 1. Mentorship Engine
- **Availability Scheduler**: Alumni select recurring availability or custom calendar dates.
- **Automated Video Conferencing**: Integration with Google Meet / Zoom API to generate meeting links automatically upon request approval.
- **Feedback & Rating**: Post-session feedback rating (1-5 stars) and session summary notes.

### 2. TPO Placement & Alumni Referral Portal
- **Eligibility Engine**: Automatic filter preventing students who do not meet CGPA or branch criteria from submitting applications.
- **Bulk Resume Downloader**: TPO can zip and download all shortlisted student resumes in one click.
- **Referral Status Tracker**: Students get real-time status updates (Applied, Referred, Interview Scheduled, Offer Extended).

### 3. AI Assistant Tools
- **Resume ATS Analyzer**: Instant feedback on keywords, format, and bullet point impact.
- **Matchmaker AI**: Vector search / LLM scoring matching students to relevant alumni based on career trajectory.
