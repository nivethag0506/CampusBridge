# 🔌 API Specification & Endpoint Directory — CampusBridge

- **Base URL**: `https://api.campusbridge.edu/v1`
- **Protocol**: HTTPS (REST API) / JSON payloads
- **Authentication**: Bearer Token via HTTP Header `Authorization: Bearer <JWT_TOKEN>`

---

## 🔐 1. Authentication & User Management

### `POST /auth/register`
Registers a new user account.
- **Request Body**:
  ```json
  {
    "email": "student@univ.edu",
    "password": "SecurePassword123!",
    "full_name": "Alex Johnson",
    "role": "STUDENT",
    "roll_number": "2024CS101",
    "branch": "Computer Science",
    "passout_year": 2026
  }
  ```
- **Response `201 Created`**:
  ```json
  {
    "message": "Registration successful. Please verify your email.",
    "user_id": "9b1deb4d-3b7d-4bad-9bdd-2b0d7b3dcb6d"
  }
  ```

### `POST /auth/login`
Authenticates a user and issues a JWT token.
- **Response `200 OK`**:
  ```json
  {
    "access_token": "eyJhbGciOi...",
    "token_type": "Bearer",
    "expires_in": 86400,
    "user": {
      "id": "9b1deb4d-3b7d-4bad-9bdd-2b0d7b3dcb6d",
      "email": "student@univ.edu",
      "role": "STUDENT"
    }
  }
  ```

---

## 🤝 2. Mentorship Endpoints

### `GET /mentorship/alumni`
Search and list available alumni mentors with filtering.
- **Query Parameters**: `?domain=Software&company=Google&page=1`
- **Response `200 OK`**:
  ```json
  {
    "total": 42,
    "data": [
      {
        "alumni_id": "c1f7a2b9-...",
        "full_name": "Priya Sharma",
        "company": "Google",
        "designation": "Senior Software Engineer",
        "expertise": ["System Design", "Backend", "FAANG Preparation"],
        "available_slots_count": 3
      }
    ]
  }
  ```

### `POST /mentorship/book`
Book a mentorship slot with an alumni.
- **Request Body**:
  ```json
  {
    "slot_id": "e4a1c8d2-...",
    "note": "Looking for guidance on backend systems interview prep."
  }
  ```

---

## 💼 3. Job Listings & Applications

### `GET /jobs`
Fetch active job listings and referral posts.
- **Query Parameters**: `?type=CAMPUS_DRIVE&min_cgpa=7.5`

### `POST /jobs/:id/apply`
Apply to a job listing with a selected resume.
- **Request Body**:
  ```json
  {
    "resume_url": "https://storage.campusbridge.edu/resumes/alex_2026.pdf"
  }
  ```

---

## 🤖 4. AI Feature Endpoints

### `POST /ai/resume-review`
Analyze a resume against a target role description.
- **Request Body**:
  ```json
  {
    "resume_text": "...",
    "target_role": "Backend Engineer"
  }
  ```
- **Response `200 OK`**:
  ```json
  {
    "ats_score": 82,
    "missing_keywords": ["Docker", "Kubernetes", "Redis"],
    "actionable_improvements": [
      "Add quantifiable metrics to your main project section."
    ]
  }
  ```
