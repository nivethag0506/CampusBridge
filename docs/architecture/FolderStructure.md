# Folder Structure

**Project:** CampusBridge

**Version:** 1.0

**Status:** Approved

---

# Overview

This document defines the directory structure for CampusBridge.

The objective is to maintain a consistent, modular, and scalable codebase throughout development.

Every contributor should follow this structure when creating new files.

---

# Repository Structure

```text
CampusBridge/
│
├── backend/
├── frontend/
├── docs/
├── design/
├── database/
├── prompts/
├── scripts/
├── assets/
│
├── README.md
├── LICENSE
├── .gitignore
└── package.json
```

---

# Frontend Structure

```text
frontend/
│
├── public/
│
├── src/
│   ├── assets/
│   ├── components/
│   │
│   ├── layouts/
│   │
│   ├── pages/
│   │
│   ├── modules/
│   │
│   ├── services/
│   │
│   ├── hooks/
│   │
│   ├── context/
│   │
│   ├── routes/
│   │
│   ├── utils/
│   │
│   ├── constants/
│   │
│   ├── types/
│   │
│   ├── styles/
│   │
│   ├── lib/
│   │
│   ├── App.tsx
│   └── main.tsx
│
├── package.json
└── vite.config.ts
```

---

# Frontend Folder Responsibilities

## assets/

Contains:

- Images
- Logos
- Icons
- Fonts

---

## components/

Reusable UI components.

Examples:

```text
Button
Navbar
Sidebar
Card
Modal
Input
Avatar
Badge
```

---

## layouts/

Application layouts.

Examples:

```text
DashboardLayout

AuthLayout

LandingLayout
```

---

## pages/

Application pages.

Examples:

```text
Home

Login

Register

Feed

Jobs

Projects

Events

Profile
```

---

## modules/

Feature-specific components.

Example:

```text
modules/

authentication/

feed/

mentorship/

jobs/

projects/

notifications/
```

Each module contains:

```text
components/

hooks/

services/

types/
```

---

## services/

API communication.

Example:

```text
auth.service.ts

user.service.ts

job.service.ts

event.service.ts
```

---

## hooks/

Reusable React hooks.

Examples:

```text
useAuth

useFetch

useSocket

usePagination
```

---

## context/

Global application state.

Examples:

```text
AuthContext

ThemeContext

NotificationContext
```

---

## routes/

Application routing.

Example:

```text
PublicRoutes

PrivateRoutes

AdminRoutes
```

---

## utils/

Shared helper functions.

Examples:

```text
formatDate

generateAvatar

calculateProgress

validators
```

---

## constants/

Application constants.

Examples:

```text
API_URL

Roles

Permissions

Status
```

---

## types/

TypeScript interfaces.

Example:

```text
User

Job

Event

Notification

Project
```

---

# Backend Structure

```text
backend/
│
├── src/
│   ├── config/
│   ├── routes/
│   ├── controllers/
│   ├── services/
│   ├── models/
│   ├── middleware/
│   ├── validators/
│   ├── utils/
│   ├── sockets/
│   ├── jobs/
│   ├── uploads/
│   ├── ai/
│   ├── modules/
│   ├── database/
│   ├── logs/
│   ├── app.ts
│   └── server.ts
│
├── package.json
└── tsconfig.json
```

---

# Backend Folder Responsibilities

## config/

Application configuration.

Examples:

```text
database.ts

cloudinary.ts

jwt.ts

mail.ts
```

---

## routes/

API endpoints.

Example:

```text
auth.routes.ts

user.routes.ts

job.routes.ts
```

---

## controllers/

Handle HTTP requests.

Responsibilities:

- Receive requests
- Validate input
- Call services
- Return responses

Business logic should not be implemented here.

---

## services/

Contains business logic.

Examples:

```text
AuthService

UserService

MentorshipService

AIService
```

---

## models/

Mongoose schemas.

Examples:

```text
User

Post

Job

Project

Event
```

---

## middleware/

Reusable middleware.

Examples:

```text
Authentication

Authorization

Error Handler

Rate Limiter
```

---

## validators/

Request validation.

Examples:

```text
LoginSchema

RegisterSchema

JobSchema
```

---

## utils/

Shared backend helpers.

---

## sockets/

Socket.IO implementation.

---

## uploads/

Temporary uploaded files before Cloudinary.

---

## ai/

Gemini integration.

Examples:

```text
Resume Analyzer

Career Advisor

Prompt Builder
```

---

## jobs/

Background tasks.

Examples:

```text
Email Queue

Notification Queue
```

---

## database/

Database connection.

Migration scripts.

Seed data.

---

# Naming Convention

## Files

Use lowercase with dots.

Example:

```text
auth.controller.ts

user.service.ts

job.routes.ts
```

---

## Components

Use PascalCase.

Example:

```text
DashboardCard.tsx

Navbar.tsx

JobCard.tsx
```

---

## Variables

camelCase

Example

```ts
userProfile

mentorList

projectData
```

---

## Constants

UPPER_SNAKE_CASE

Example

```ts
JWT_SECRET

API_BASE_URL
```

---

# Import Order

```text
External Libraries

↓

Internal Modules

↓

Components

↓

Utilities

↓

Styles
```

---

# Development Rules

- Keep controllers lightweight.
- Place business logic in services.
- Reuse utility functions.
- Avoid duplicate code.
- Validate every request.
- Never expose secrets in source code.
- Use environment variables for configuration.

---

# Summary

This folder structure provides a scalable foundation for CampusBridge.

Following these conventions ensures that the project remains organized, maintainable, and easy to extend as new features are added.
