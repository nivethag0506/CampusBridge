# User Flow

**Project:** CampusBridge

**Version:** 1.0

**Status:** Approved

---

# Overview

This document describes how each user interacts with CampusBridge from authentication to completing their primary tasks.

The objective is to define complete user journeys before UI design and backend implementation.

Each workflow represents the expected behavior of the application.

---

# Supported User Roles

- Student
- Alumni
- Faculty
- Placement Cell
- Recruiter
- Administrator

---

# Global Authentication Flow

```text
Open Application

↓

Login / Register

↓

Email Verification

↓

Authentication

↓

JWT Issued

↓

Load User Profile

↓

Redirect to Role Dashboard
```

---

# Student Journey

## Goal

A student joins the platform, builds a professional profile, connects with alumni, applies for opportunities, and participates in campus activities.

### Flow

```text
Landing Page

↓

Register

↓

Verify College Email

↓

Complete Profile

↓

Student Dashboard

↓

Explore Feed

↓

Connect with Alumni

↓

Join Clubs

↓

Apply for Jobs

↓

Book Mentorship Session

↓

Upload Projects

↓

Receive Notifications
```

### Student Dashboard

The student dashboard provides:

- Personalized announcements
- Upcoming events
- Recommended internships
- Placement drives
- Mentor suggestions
- Community updates
- AI career insights

---

# Alumni Journey

## Goal

Alumni contribute to the campus community through mentorship, referrals, and networking.

### Flow

```text
Register

↓

Admin Verification

↓

Alumni Dashboard

↓

Complete Professional Profile

↓

Accept Student Connections

↓

Post Referral

↓

Schedule Mentorship

↓

Participate in Discussions
```

### Alumni Features

- Mentorship
- Referral posting
- Company updates
- Alumni networking
- Success stories

---

# Faculty Journey

## Goal

Faculty manage academic communication and student engagement.

### Flow

```text
Login

↓

Faculty Dashboard

↓

Publish Announcements

↓

Create Events

↓

Review Student Projects

↓

Manage Department Activities
```

---

# Placement Cell Journey

## Goal

Manage placement activities from a centralized dashboard.

### Flow

```text
Login

↓

Placement Dashboard

↓

Create Company Drive

↓

Define Eligibility

↓

Publish Opportunity

↓

Monitor Applications

↓

Shortlist Students

↓

Update Results
```

---

# Recruiter Journey

## Goal

Recruiters discover and hire students.

### Flow

```text
Register

↓

Verification

↓

Recruiter Dashboard

↓

Publish Job

↓

Browse Students

↓

View Profiles

↓

Shortlist Candidates

↓

Contact Placement Cell
```

---

# Administrator Journey

## Goal

Maintain platform security and operations.

### Flow

```text
Login

↓

Admin Dashboard

↓

Approve Users

↓

Verify Alumni

↓

Verify Recruiters

↓

Moderate Content

↓

Monitor Reports

↓

View Analytics

↓

Manage Platform Settings
```

---

# Mentorship Workflow

```text
Student

↓

Browse Mentors

↓

View Mentor Profile

↓

Send Request

↓

Mentor Accepts

↓

Schedule Session

↓

Complete Session

↓

Submit Feedback
```

---

# Placement Workflow

```text
Placement Cell

↓

Create Placement Drive

↓

Publish Opportunity

↓

Student Applies

↓

Application Review

↓

Shortlisting

↓

Interview Process

↓

Offer Released

↓

Placement Recorded
```

---

# Internship Workflow

```text
Recruiter

↓

Publish Internship

↓

Student Applies

↓

Recruiter Reviews

↓

Shortlisting

↓

Interview

↓

Selection
```

---

# Community Workflow

```text
User

↓

Create Post

↓

Community Feed

↓

Like

↓

Comment

↓

Share

↓

Save Post

↓

Receive Notifications
```

---

# Event Workflow

```text
Faculty / Club

↓

Create Event

↓

Publish

↓

Student Registers

↓

Reminder Sent

↓

Attend Event

↓

Upload Photos

↓

Archive Event
```

---

# Club Workflow

```text
Create Club

↓

Approve Club

↓

Recruit Members

↓

Publish Activities

↓

Conduct Events

↓

Manage Discussions
```

---

# Project Showcase Workflow

```text
Student

↓

Create Project

↓

Upload Images

↓

Add GitHub Repository

↓

Add Live Demo

↓

Publish

↓

Visible on Profile
```

---

# AI Career Assistant Workflow

```text
Student

↓

Upload Resume

↓

Resume Parsed

↓

Gemini AI Analysis

↓

Skill Gap Detection

↓

Career Suggestions

↓

Learning Roadmap

↓

Recommended Jobs
```

---

# Notification Workflow

```text
System Event

↓

Notification Created

↓

Stored in Database

↓

Real-Time Delivery

↓

Notification Center

↓

User Reads Notification
```

---

# Search Workflow

```text
Search Query

↓

Global Search Service

↓

Users

↓

Posts

↓

Projects

↓

Events

↓

Jobs

↓

Results Displayed
```

---

# Error Flow

```text
Invalid Request

↓

Validation

↓

Error Handler

↓

Structured Response

↓

User Feedback
```

---

# Logout Flow

```text
User

↓

Logout

↓

JWT Removed

↓

Session Cleared

↓

Redirect to Login
```

---

# Future User Flows

The following workflows are planned for future releases.

- Mobile onboarding
- AI mock interview
- Referral tracking
- Multi-college collaboration
- Company hiring pipeline
- Campus marketplace
- Digital student ID

---

# Summary

These workflows define how users interact with CampusBridge.

All frontend pages, backend APIs, database models, and automated tests should align with these user journeys to ensure consistent application behavior.
