# 🎓 CampusBridge

> **Bridging the gap between Students, Alumni, Faculty, and Industry.**

CampusBridge is a unified web platform designed to streamline campus placement activities, alumni mentorship, community networking, event management, and AI-driven career guidance for college campuses.

---

## 📁 Project Directory Structure

```text
CampusBridge/
├── README.md                 # Project Overview & Quick Start
├── .gitignore                # Git Ignore Rules
│
├── docs/                     # Comprehensive Architecture & Project Docs
│   ├── PRD.md                # Product Requirements Document
│   ├── UserFlow.md           # User Journeys & Workflow Diagrams
│   ├── DatabaseDesign.md     # Relational Database Schema & Specification
│   ├── SystemArchitecture.md # System & Component Architecture
│   ├── API.md                # REST / GraphQL API Specifications
│   ├── Features.md           # Detailed Feature Matrix & User Stories
│   ├── Roadmap.md            # Release Phases & Milestones
│   ├── TechStack.md          # Technical Stack & Libraries Selection
│   └── MeetingNotes.md       # Team Alignment & Architectural Discussions
│
├── design/                   # UI/UX Resources & Assets
│   ├── figma-link.md         # Design System & Figma File Links
│   ├── wireframes/           # Low-fidelity Wireframe Mockups
│   ├── ui-images/            # High-fidelity UI Screenshots & Demos
│   └── assets/               # Logos, Icons, and Media Assets
│
├── database/                 # Database Models & Indexing Strategy
│   ├── ERD.md                # Entity Relationship Diagram & Relations
│   ├── Collections.md        # Table / Collection Schema Definitions
│   └── Indexing.md           # Indexing & Query Optimization Strategies
│
├── prompts/                  # AI System Prompts & Code Gen Templates
│   ├── ai_prompts.md         # Core AI Agent Features (Resume Reviewer, Matcher)
│   ├── frontend.md           # Client-side Component Generation Guidelines
│   ├── backend.md            # Server-side Controller & Service Guidelines
│   ├── database.md           # Migration & Schema Design Prompts
│   ├── ui.md                 # UI/UX Styling & Theme System Prompts
│   └── testing.md            # Unit, Integration & E2E Testing Prompts
│
├── frontend/                 # Client Application (React / Next.js)
├── backend/                  # Server Application (Node.js Express / Python FastAPI)
└── .github/
    └── workflows/            # CI/CD Pipelines & Automation Workflows
```

---

## ✨ Core Highlights

- 🤝 **Alumni Mentorship Matchmaker**: Direct 1-on-1 scheduling with industry alumni.
- 💼 **Placement & Referral Hub**: Official TPO placement drives + Alumni referral postings.
- 🗓️ **Events & Workshops**: University-wide tech sessions, webinars, and hackathon management.
- 🤖 **AI Career Suite**: AI Resume Optimizer, Mock Technical Interviewer, and Goal Assister.
- 💬 **Campus Discussions**: Q&A hub for campus queries, interview experiences, and academic support.

---

## 🛠️ Tech Stack Overview

- **Frontend**: Next.js (App Router), TypeScript, Tailwind CSS
- **Backend**: Node.js / TypeScript (Express / NestJS) or Python (FastAPI)
- **Database**: PostgreSQL with Prisma ORM / Redis for Caching
- **Authentication**: NextAuth.js / JWT with Role-Based Access Control (RBAC)
- **CI/CD**: GitHub Actions

---

## 🚀 Getting Started

1. **Clone Repository**:
   ```bash
   git clone https://github.com/your-org/CampusBridge.git
   cd CampusBridge
   ```

2. **Explore Documentation**:
   Check the [`docs/`](docs/) directory for detailed system design specs:
   - [Product Requirements Document (PRD)](docs/PRD.md)
   - [System Architecture](docs/SystemArchitecture.md)
   - [API Specification](docs/API.md)
   - [Database ERD](database/ERD.md)
