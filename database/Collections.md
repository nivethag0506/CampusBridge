# 🗄️ Collections & Table Schemas — CampusBridge

This document documents the specific column attributes, types, nullability, and default values for each table/collection in CampusBridge.

---

## 📋 Table Specifications

### 1. `users`
- Primary user table handling authentication and global identity.

| Column | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | `UUID` | `PK, DEFAULT gen_random_uuid()` | Unique ID |
| `email` | `VARCHAR(255)` | `UNIQUE, NOT NULL` | Login email address |
| `password_hash` | `VARCHAR(255)` | `NOT NULL` | Encrypted bcrypt hash |
| `role` | `VARCHAR(50)` | `NOT NULL` | `'STUDENT'`, `'ALUMNI'`, `'FACULTY'`, `'TPO'`, `'ADMIN'` |
| `is_verified` | `BOOLEAN` | `DEFAULT false` | Verified status |
| `created_at` | `TIMESTAMPTZ` | `DEFAULT now()` | Creation timestamp |

---

### 2. `student_profiles`
- Extended profile details for students.

| Column | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | `UUID` | `PK` | Profile ID |
| `user_id` | `UUID` | `FK(users.id), NOT NULL` | Parent user reference |
| `roll_number` | `VARCHAR(50)` | `UNIQUE, NOT NULL` | Institutional Roll Number |
| `branch` | `VARCHAR(100)` | `NOT NULL` | Academic major |
| `cgpa` | `DECIMAL(3,2)` | `NOT NULL` | CGPA out of 10.0 |
| `passout_year` | `INT` | `NOT NULL` | Graduation year |
| `resume_url` | `TEXT` | `NULLABLE` | AWS S3 link to resume PDF |

---

### 3. `job_listings`
- Job referral and campus drive postings.

| Column | Type | Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | `UUID` | `PK` | Job listing ID |
| `posted_by` | `UUID` | `FK(users.id), NOT NULL` | User who posted the job |
| `title` | `VARCHAR(200)` | `NOT NULL` | Position title |
| `company_name` | `VARCHAR(150)` | `NOT NULL` | Company name |
| `job_type` | `VARCHAR(50)` | `NOT NULL` | `'REFERRAL'`, `'CAMPUS_DRIVE'`, `'INTERNSHIP'` |
| `min_cgpa` | `DECIMAL(3,2)` | `DEFAULT 0.00` | Minimum CGPA required |
| `deadline` | `TIMESTAMPTZ` | `NOT NULL` | Application deadline |
