# ⚡ Database Indexing & Query Optimization — CampusBridge

This document defines the database indexing strategy to ensure fast queries (<50ms) across high-frequency user actions.

---

## 🔍 Recommended SQL Indexes

```sql
-- 1. Authentication & Email Lookups
CREATE UNIQUE INDEX idx_users_email ON users(email);

-- 2. Student Lookup by Roll Number & User ID
CREATE UNIQUE INDEX idx_students_roll_number ON student_profiles(roll_number);
CREATE INDEX idx_students_user_id ON student_profiles(user_id);

-- 3. Filtering Jobs by Type, CGPA, and Active Deadline
CREATE INDEX idx_jobs_filter ON job_listings(job_type, min_cgpa, deadline);

-- 4. Fast Application Lookup per Student
CREATE INDEX idx_applications_student_job ON job_applications(student_id, job_id);

-- 5. Mentorship Available Slot Lookups
CREATE INDEX idx_mentorship_slots_alumni_time ON mentorship_slots(alumni_id, start_time) 
WHERE is_booked = false;

-- 6. Full-Text Search Index on Discussion Posts
CREATE INDEX idx_posts_search ON community_posts USING gin(to_tsvector('english', title || ' ' || content));
```

---

## 📊 Query Optimization Rules

1. **Avoid `SELECT *`**: Always select explicit columns or use Prisma `select` fields.
2. **Paginate All Feed Queries**: Apply offset/cursor pagination (`LIMIT 20 OFFSET :offset`).
3. **Use Redis Caching**: Cache static dropdowns (e.g. branch names, companies list) in Redis with a 24-hour TTL.
