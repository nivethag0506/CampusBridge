# 📝 Meeting Notes & Architecture Alignment — CampusBridge

This document logs key architectural discussions, alignment meetings, and decision records for CampusBridge.

---

## 📅 Meeting #1: Initial Architecture & Directory Layout
- **Date**: July 25, 2026
- **Attendees**: Lead Architect, Frontend Team, Backend Team, Database Architect

### Key Decisions Made:
1. **Directory Structure Standardization**:
   - Agreed to organize the codebase into modular root directories (`docs/`, `design/`, `database/`, `prompts/`, `frontend/`, `backend/`, `.github/`).
2. **Database Engine**:
   - Confirmed **PostgreSQL** as the primary relational database with **Prisma ORM** for schema migrations.
3. **Role-Based Access Control (RBAC)**:
   - User roles defined as `STUDENT`, `ALUMNI`, `FACULTY`, `TPO`, and `ADMIN`.
4. **AI Features**:
   - Prompts isolated in `prompts/` directory to manage system instructions for Resume ATS Review, Mentorship Matcher, and Technical Mock Interviews.

---

## 📋 Action Items
- [x] Set up foundational directory tree & markdown documentation files.
- [ ] Initialize Next.js project inside `frontend/`.
- [ ] Initialize Express/FastAPI server inside `backend/`.
- [ ] Draft initial database migration scripts inside `database/`.
