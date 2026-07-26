# API Design Specification

**Project:** CampusBridge

**Version:** 1.0

**Status:** Draft

---

# Overview

This document defines the REST API design standards used throughout CampusBridge.

Every API module in the project follows the conventions described here to ensure consistency, maintainability, and predictable behavior.

Individual endpoint documentation is maintained in dedicated module documents.

---

# Base URL

Development

```
http://localhost:5000/api/v1
```

Production

```
https://api.campusbridge.app/api/v1
```

---

# API Principles

The API follows RESTful design principles.

- Resource-oriented endpoints
- Stateless requests
- JWT-based authentication
- JSON request and response bodies
- Consistent error handling
- Versioned APIs

---

# Content Type

All requests and responses use JSON unless otherwise specified.

```
Content-Type: application/json
```

Multipart requests are used only for file uploads.

---

# Authentication

Protected endpoints require a JWT access token.

Example header

```http
Authorization: Bearer <access_token>
```

---

# API Versioning

The current API version is:

```
v1
```

Future breaking changes will be introduced under new versions.

Example

```
/api/v2/users
```

---

# Standard Response Format

Successful response

```json
{
  "success": true,
  "message": "Operation completed successfully.",
  "data": {}
}
```

Error response

```json
{
  "success": false,
  "message": "Validation failed.",
  "errors": []
}
```

---

# HTTP Status Codes

| Status | Meaning |
|---------|---------|
| 200 | Success |
| 201 | Resource Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 429 | Too Many Requests |
| 500 | Internal Server Error |

---

# Authentication APIs

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | /auth/register | Register a new user |
| POST | /auth/verify-email | Verify email address |
| POST | /auth/login | User login |
| POST | /auth/google | Google OAuth login |
| POST | /auth/forgot-password | Request password reset |
| POST | /auth/reset-password | Reset password |
| GET | /auth/me | Get current user |
| POST | /auth/logout | Logout |

---

# User APIs

| Method | Endpoint |
|---------|----------|
| GET | /users/profile |
| PUT | /users/profile |
| GET | /users/:id |
| GET | /users/search |

---

# Feed APIs

| Method | Endpoint |
|---------|----------|
| GET | /posts |
| POST | /posts |
| GET | /posts/:id |
| PUT | /posts/:id |
| DELETE | /posts/:id |
| POST | /posts/:id/like |
| POST | /posts/:id/comment |

---

# Alumni APIs

| Method | Endpoint |
|---------|----------|
| GET | /alumni |
| GET | /alumni/:id |
| GET | /alumni/search |
| POST | /alumni/connect |

---

# Mentorship APIs

| Method | Endpoint |
|---------|----------|
| POST | /mentorship/request |
| GET | /mentorship/requests |
| PUT | /mentorship/:id/accept |
| PUT | /mentorship/:id/reject |
| POST | /mentorship/session |

---

# Placement APIs

| Method | Endpoint |
|---------|----------|
| GET | /placements |
| POST | /placements |
| GET | /placements/:id |
| POST | /placements/:id/apply |

---

# Internship APIs

| Method | Endpoint |
|---------|----------|
| GET | /internships |
| POST | /internships |
| POST | /internships/:id/apply |

---

# Project APIs

| Method | Endpoint |
|---------|----------|
| GET | /projects |
| POST | /projects |
| PUT | /projects/:id |
| DELETE | /projects/:id |

---

# Event APIs

| Method | Endpoint |
|---------|----------|
| GET | /events |
| POST | /events |
| POST | /events/:id/register |
| PUT | /events/:id |

---

# Club APIs

| Method | Endpoint |
|---------|----------|
| GET | /clubs |
| POST | /clubs |
| POST | /clubs/:id/join |

---

# Notification APIs

| Method | Endpoint |
|---------|----------|
| GET | /notifications |
| PUT | /notifications/:id/read |

---

# Chat APIs

| Method | Endpoint |
|---------|----------|
| GET | /conversations |
| POST | /messages |
| GET | /messages/:conversationId |

---

# AI APIs

| Method | Endpoint |
|---------|----------|
| POST | /ai/resume-review |
| POST | /ai/career-roadmap |
| POST | /ai/skill-gap |
| POST | /ai/project-suggestions |

---

# Admin APIs

| Method | Endpoint |
|---------|----------|
| GET | /admin/users |
| PUT | /admin/users/:id |
| DELETE | /admin/users/:id |
| GET | /admin/reports |
| GET | /admin/dashboard |

---

# Pagination

Collection endpoints support pagination.

Example

```
GET /posts?page=1&limit=10
```

Response

```json
{
  "page": 1,
  "limit": 10,
  "totalPages": 5,
  "totalItems": 48,
  "data": []
}
```

---

# Filtering

Example

```
GET /jobs?company=Google
```

```
GET /events?department=CSE
```

```
GET /alumni?batch=2024
```

---

# Sorting

Example

```
GET /posts?sort=createdAt
```

```
GET /projects?sort=likes
```

---

# Search

Example

```
GET /users/search?q=Rahul
```

---

# Rate Limiting

Authentication endpoints are rate-limited.

Example policy

- 5 login attempts per minute per IP
- 10 password reset requests per hour

---

# File Uploads

Supported file types

- JPG
- PNG
- PDF

Maximum upload size

- Profile Image: 5 MB
- Resume: 10 MB
- Project Media: 15 MB

---

# API Documentation Strategy

Each functional module has its own API specification.

```
docs/api/

API.md

AuthenticationAPI.md

UserAPI.md

FeedAPI.md

MentorshipAPI.md

PlacementAPI.md

EventAPI.md

AIAPI.md

AdminAPI.md
```

---

# Change Management

Breaking API changes require a new version.

Non-breaking enhancements may be added to the existing version after review.
