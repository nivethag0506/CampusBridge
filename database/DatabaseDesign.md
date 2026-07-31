# Database Design

**Project:** CampusBridge

**Version:** 1.0

**Database:** MongoDB Atlas

**ODM:** Mongoose

**Status:** Approved

---

# Overview

CampusBridge is designed using a document-oriented database architecture powered by MongoDB. The database is organized around business domains instead of application pages, making the system modular, scalable, and easier to maintain.

Each collection represents a business entity. Relationships between entities are maintained using ObjectId references where appropriate, while embedded documents are used only when they improve read performance without introducing excessive duplication.

---

# Database Goals

The database design aims to:

- Support multiple user roles with role-based access.
- Scale for thousands of students, alumni, recruiters, and faculty members.
- Minimize duplicate data.
- Support efficient search and filtering.
- Enable real-time communication.
- Provide a foundation for AI-powered features.
- Keep collections independent and maintainable.

---

# Technology Stack

| Component | Technology |
|-----------|------------|
| Database | MongoDB Atlas |
| ODM | Mongoose |
| Object Identifier | ObjectId |
| File Storage | Cloudinary |
| Cache (Future) | Redis |

---

# Business Domains

The database is divided into the following domains.

## 1. Identity

Responsible for user authentication and personal information.

Collections:

- Users
- Profiles
- Skills
- Education
- Experience
- Achievements
- Portfolios

---

## 2. Community

Responsible for social networking within the campus.

Collections:

- Posts
- Comments
- Likes
- Bookmarks
- Connections
- Clubs
- Announcements

---

## 3. Career

Responsible for placement and recruitment activities.

Collections:

- Companies
- Jobs
- Internships
- Applications
- Referrals

---

## 4. Alumni

Responsible for alumni networking and mentorship.

Collections:

- MentorshipRequests
- MentorshipSessions
- MentorAvailability

---

## 5. Campus

Responsible for events and student activities.

Collections:

- Events
- EventRegistrations
- Projects
- Teams
- Hackathons

---

## 6. Communication

Responsible for messaging and notifications.

Collections:

- Conversations
- Messages
- Notifications

---

## 7. Artificial Intelligence

Responsible for AI-generated insights.

Collections:

- ResumeAnalyses
- SkillGapReports
- CareerRecommendations
- ProjectRecommendations

---

## 8. Administration

Responsible for platform management.

Collections:

- Reports
- AuditLogs

---

# Collection Overview

| Collection | Purpose |
|------------|----------|
| Users | Authentication and authorization |
| Profiles | Public profile information |
| Skills | User technical skills |
| Education | Academic history |
| Experience | Internship and work experience |
| Achievements | Certifications and awards |
| Portfolios | Project showcase |
| Posts | Community feed |
| Comments | Post discussions |
| Likes | Post reactions |
| Bookmarks | Saved posts |
| Connections | Student–Alumni connections |
| Companies | Company information |
| Jobs | Placement opportunities |
| Internships | Internship listings |
| Applications | Job applications |
| Referrals | Alumni referrals |
| MentorshipRequests | Mentorship requests |
| MentorshipSessions | Scheduled mentoring sessions |
| MentorAvailability | Mentor availability schedule |
| Events | College events |
| EventRegistrations | Event registrations |
| Projects | Student projects |
| Teams | Project teams |
| Hackathons | Hackathon details |
| Conversations | Chat rooms |
| Messages | Chat messages |
| Notifications | System notifications |
| ResumeAnalyses | AI resume reviews |
| SkillGapReports | AI skill gap analysis |
| CareerRecommendations | AI career suggestions |
| ProjectRecommendations | AI project recommendations |
| Reports | User reports |
| AuditLogs | Administrative activity logs |

---

# Relationship Strategy

CampusBridge primarily uses referenced relationships.

Example:

```
User
 ├── Profile
 ├── Posts
 ├── Projects
 ├── Applications
 ├── Messages
 ├── Notifications
 └── Resume Analysis
```

References reduce duplication and simplify updates.

---

# Embedding Strategy

Embedded documents are used only for small datasets that always belong to a parent document.

Examples:

- Social links
- Contact information
- Notification preferences
- User settings

Large datasets remain separate collections.

---

# Soft Delete Strategy

Collections support soft deletion where applicable.

Example fields:

```json
{
  "isDeleted": false,
  "deletedAt": null
}
```

Soft deletion preserves historical data while hiding records from active queries.

---

# Audit Fields

Every collection includes standard audit fields.

```json
{
  "createdAt": "...",
  "updatedAt": "...",
  "createdBy": "...",
  "updatedBy": "..."
}
```

These fields simplify debugging and activity tracking.

---

# Naming Conventions

## Collections

Use plural names.

Examples:

- users
- profiles
- posts
- events

---

## Fields

Use camelCase.

Examples:

```
firstName
createdAt
profileImage
companyName
```

---

## References

Reference fields use the related entity name.

Examples:

```
userId
companyId
mentorId
eventId
projectId
```

---

# Common Document Pattern

Every collection follows a consistent structure.

```json
{
  "_id": "ObjectId",
  "createdAt": "Date",
  "updatedAt": "Date",
  "createdBy": "ObjectId",
  "updatedBy": "ObjectId",
  "isDeleted": false
}
```

---

# Security Considerations

Sensitive information is never stored in plain text.

Examples:

- Passwords are hashed using bcrypt.
- JWT tokens are not stored in the database.
- File URLs are stored instead of file contents.
- Access permissions are enforced at the application layer.

---

# Scalability Considerations

The schema is designed to support future expansion.

Planned enhancements include:

- Multi-college support
- Department-level administration
- Multi-language support
- Analytics warehouse
- Recommendation engine
- Mobile application
- Microservice migration

---

# Database Lifecycle

```
Client

↓

Express API

↓

Validation

↓

Business Logic

↓

Mongoose Models

↓

MongoDB Atlas

↓

Response
```

---

# Design Principles

The following principles guide database development:

- One collection represents one business entity.
- Avoid unnecessary data duplication.
- Use references for large relationships.
- Index frequently queried fields.
- Validate data before persistence.
- Keep collections loosely coupled.
- Design for future scalability.

---

# Summary

The CampusBridge database is organized around business domains instead of user interface pages. This approach produces a maintainable schema, simplifies API development, and provides a scalable foundation for future enhancements without requiring major structural changes.
