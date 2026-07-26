# System Architecture

**Project:** CampusBridge

**Version:** 1.0

**Status:** Approved

---

# 1. Overview

CampusBridge follows a modular three-tier architecture consisting of a client application, backend services, and cloud-managed infrastructure.

The architecture is designed to support secure authentication, role-based access control, real-time communication, AI-powered services, and future expansion without requiring significant structural changes.

---

# 2. Architecture Goals

The architecture is designed to achieve the following goals:

- Modular development
- Clear separation of responsibilities
- Scalability
- Maintainability
- Security
- Reusability
- Production readiness

---

# 3. High-Level Architecture

```text
                    +----------------------+
                    |      Web Browser     |
                    +----------+-----------+
                               |
                               |
                        HTTPS Requests
                               |
                               ▼
                +-----------------------------+
                | React.js Frontend (Vite)    |
                +-------------+---------------+
                              |
             REST API         |      Socket.IO
                              |
                              ▼
                +-----------------------------+
                | Node.js + Express Backend   |
                +-------------+---------------+
                              |
      +-----------------------+-----------------------+
      |           |            |          |           |
      ▼           ▼            ▼          ▼           ▼
 Authentication  Community   Career   AI Service  Notification
      |           |            |          |           |
      +-----------------------+-----------------------+
                              |
                              ▼
                     MongoDB Atlas Database
                              |
              +---------------+----------------+
              |                                |
              ▼                                ▼
       Cloudinary                      Gemini API
     (Media Storage)               (AI Functionality)
```

---

# 4. System Layers

## Presentation Layer

The presentation layer provides the user interface.

Technology:

- React.js
- TypeScript
- Tailwind CSS
- shadcn/ui

Responsibilities:

- Render UI
- Handle navigation
- Manage forms
- Communicate with backend APIs
- Display real-time updates

---

## Application Layer

Implemented using Node.js and Express.js.

Responsibilities:

- Business logic
- Authentication
- Authorization
- Validation
- File processing
- AI integration
- Notification management

---

## Data Layer

MongoDB Atlas stores application data.

Responsibilities:

- User data
- Posts
- Events
- Jobs
- Projects
- Mentorship
- Notifications
- Chat

Mongoose manages schema validation and data access.

---

# 5. Backend Module Architecture

The backend is organized into independent modules.

```text
Backend

├── Authentication
├── User Management
├── Community
├── Alumni
├── Mentorship
├── Career
├── Projects
├── Events
├── Notifications
├── AI
└── Administration
```

Each module contains:

- Routes
- Controllers
- Services
- Models
- Validation
- Middleware

This structure minimizes coupling between features.

---

# 6. Frontend Architecture

The frontend follows a component-based architecture.

```text
src/

components/

pages/

layouts/

hooks/

services/

context/

utils/

assets/

types/
```

### Responsibilities

Components

Reusable UI elements.

Pages

Application screens.

Services

API communication.

Context

Global state.

Hooks

Reusable business logic.

Utils

Shared helper functions.

Types

Application-wide TypeScript types.

---

# 7. Authentication Flow

```text
User

↓

Login Request

↓

Authentication Controller

↓

Credential Validation

↓

Password Verification

↓

JWT Generation

↓

Access Token Returned

↓

Frontend Stores Token

↓

Authenticated API Requests
```

Only authenticated users may access protected resources.

Role-based authorization determines resource access.

---

# 8. Request Lifecycle

```text
Browser

↓

React Component

↓

Axios Request

↓

Express Route

↓

Middleware

↓

Controller

↓

Service

↓

Database

↓

Response

↓

React UI Update
```

Business logic remains inside service classes.

Controllers coordinate requests and responses only.

---

# 9. File Upload Flow

```text
User Upload

↓

Multer

↓

Validation

↓

Cloudinary

↓

Media URL Generated

↓

MongoDB Updated

↓

Response Returned
```

Supported uploads include:

- Profile images
- Resume PDFs
- Project screenshots
- Event banners

---

# 10. AI Service Flow

```text
User Action

↓

Backend AI Service

↓

Prompt Construction

↓

Gemini API

↓

AI Response

↓

Validation

↓

Client Response
```

The AI layer remains isolated from other modules, allowing future provider changes with minimal code modifications.

---

# 11. Notification Flow

```text
Application Event

↓

Notification Service

↓

Database

↓

Socket.IO

↓

Connected User

↓

UI Notification
```

Notifications are both stored and delivered in real time.

---

# 12. Security Architecture

Security is enforced across every layer.

Authentication

- JWT
- Google OAuth

Authorization

- Role-Based Access Control (RBAC)

Password Protection

- bcrypt

API Protection

- Helmet
- CORS
- Rate Limiting

Validation

- Zod
- Mongoose validation

Uploads

- MIME type validation
- File size limits

Secrets

- Environment variables

---

# 13. External Services

| Service | Purpose |
|----------|---------|
| MongoDB Atlas | Database |
| Cloudinary | Media storage |
| Gemini API | AI features |
| Gmail SMTP | Transactional email |

---

# 14. Error Handling

Errors follow a consistent structure.

```json
{
  "success": false,
  "message": "Validation failed.",
  "errors": []
}
```

Unexpected exceptions are logged before returning a generic response.

---

# 15. Logging Strategy

Application logs include:

- Authentication events
- API errors
- File uploads
- AI requests
- System warnings

Sensitive information such as passwords and tokens must never be logged.

---

# 16. Scalability

The architecture supports future growth by:

- Modular backend design
- Independent service layers
- Cloud-managed infrastructure
- Stateless authentication
- External media storage
- Horizontal backend scaling

---

# 17. Future Architecture

The current architecture is intended for a single institution.

Future enhancements may include:

- Multi-college support
- Microservices
- Redis caching
- Search indexing
- Analytics pipeline
- Mobile applications

These enhancements should be evaluated through Architecture Decision Records before implementation.

---

# 18. Summary

CampusBridge follows a modular MERN architecture designed for long-term maintainability and production deployment.

The architecture separates presentation, business logic, and data management while integrating cloud services for authentication, media storage, AI functionality, and real-time communication.
