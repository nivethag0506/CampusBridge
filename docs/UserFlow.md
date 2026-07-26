# 🔄 User Flow & Navigation Diagrams — CampusBridge

This document outlines the step-by-step navigation flows for the key user interactions across CampusBridge.

---

## 1. User Onboarding & Role Verification Flow

```mermaid
graph TD
    Start([User Visits CampusBridge]) --> SignUp[Click Sign Up]
    SignUp --> SelectRole{Select User Role}
    
    SelectRole -->|Student| StudentForm[Enter Roll No, Branch, Graduation Year]
    SelectRole -->|Alumni| AlumniForm[Enter Passout Year, Company, LinkedIn Profile]
    SelectRole -->|TPO / Faculty| FacultyForm[Enter Faculty ID & Department]
    
    StudentForm --> VerifyEmail[Verify College Email domain @univ.edu]
    FacultyForm --> VerifyEmail
    AlumniForm --> PendingAdmin[Sent to Admin Verification Queue]
    
    VerifyEmail --> ActiveStudent([Active Student Account])
    PendingAdmin --> AdminApprove{Admin Approves?}
    AdminApprove -->|Yes| ActiveAlumni([Active Alumni Account])
    AdminApprove -->|No| RejectNotice[Receive Rejection Email]
```

---

## 2. Student Mentorship Booking Flow

```mermaid
sequenceDiagram
    autonumber
    actor Student
    participant System as CampusBridge System
    actor Alumni

    Student->>System: Browse / Filter Alumni (by Domain, Company)
    System-->>Student: Display Alumni Profiles & Open Time Slots
    Student->>System: Select Time Slot & Submit Note/Resume
    System->>Alumni: Send Email Notification & Booking Request
    alt Alumni Accepts
        Alumni->>System: Accept Mentorship Booking
        System->>Student: Send Confirmation & Meeting Link (Google Meet / Zoom)
        System->>Alumni: Add to Calendar
    else Alumni Declines
        Alumni->>System: Reject Booking (Optionally select reason)
        System->>Student: Send Rejection Notification & Suggest Alternatives
    end
```

---

## 3. Placement Drive & Referral Application Flow

```mermaid
graph TD
    A[Alumni or TPO] -->|Create Listing| B(Post Job / Placement Drive)
    B --> C[Specify CGPA, Branch & Target Batch]
    C --> D[Job Appears on Student Dashboard]
    
    E[Student] --> F[View Job Details]
    F --> G{Meets Eligibility?}
    G -->|No| H[Show Ineligible Banner with Reasons]
    G -->|Yes| I[Upload/Select Resume]
    I --> J[Click Apply]
    J --> K[Application Status: Applied]
    
    K --> L[TPO Dashboard / Alumni Referral Portal]
    L --> M{Review Candidate}
    M -->|Shortlist| N[Status: Shortlisted / Interview Scheduled]
    M -->|Reject| O[Status: Rejected]
```

---

## 4. Discussion Forum & Community Post Flow

1. **Create Post**: User selects tag (`#InterviewExperience`, `#QnA`, `#CareerAdvice`), writes Markdown content, attaches optional images/PDFs.
2. **Moderation Check**: Automated filter scans for profanity or spam.
3. **Feed Publishing**: Published to public campus feed.
4. **Engagement**: 
   - Users upvote / downvote.
   - Alumni answers receive a highlighted **Verified Alumni** badge.
   - Author can mark an answer as **Accepted Solution**.
