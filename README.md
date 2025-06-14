# project LeadFlow ai-Smart Lead Management And Automation For Service Bussinesses
# LeadFlow AI — Smart Lead Management & Automation for Service Businesses 🚀

LeadFlow AI is a fully functional, highly scalable, production-grade CRM SaaS platform that empowers service businesses to manage, automate, and optimize their entire lead pipeline using AI-driven lead scoring and actionable business intelligence.

This system has been fully built using:
-Node.js API Logic
- Supabase as the PostgreSQL Cloud Database
- Windsurf AI Frontend Generator (React)
- Serverless deployment (Vercel/Render/Railway)
- JWT secured authentication
- AI-powered scoring engine for lead prioritization

---

## 📢 Hackathon Problem Statement Solved

> **"Smart Lead Management & Automation for Service Businesses"**

- We built a full-stack SaaS CRM platform focused on solving the problem of how service businesses (gyms, salons, clinics, coaching centers, consultancies, agencies, etc.) can automate & optimize their lead conversion process using modern AI technology with zero technical overhead.

---

## 🎯 Product Features

### ✅ 1️⃣ User Authentication
- Secure Registration, Login, Forgot Password
- JWT-based Token Authentication
- Password hashing and secure storage
- Role-based access control system

### ✅ 2️⃣ Role-Based Access Control (RBAC)
- Admin → Full Access (manage all users, data, settings, analytics)
- Manager → Moderate access (manage leads, assign tasks)
- SalesAgent → Limited access (only handle assigned leads)

### ✅ 3️⃣ Lead Management System (Core Module)
- Create, Edit, Delete, View Leads
- Full Search, Filtering, Sorting
- Paginated API Endpoints
- Assign agents & track ownership of leads

### ✅ 4️⃣ AI-Powered Lead Scoring Engine
- Fully server-side logic scoring leads on:

| Rule | Score |
|------------------|--------|
| Form submitted within 60 seconds | +3 |
| Engagement notes > 20 words | +2 |
| Service interested OR company matches (gyms, salons, clinics) | +2 |
| Lead source is Referral/Instagram DM | +1 |
| Appointment scheduled immediately after submission | +1 |
| Lead responded to follow-up | +1 |
| No response within 3 days | -2 |
| Invalid or missing email/phone | -1 |

- Final Lead Scores:
  - 🔥 Hot (8-10) → Schedule Zoom demo immediately.
  - Warm (5-7) → Nurture with reminders.
  - Cold (0-4) → Apply "last attempt" automation.

- Human-readable AI Explanation generated for every lead.

### ✅ 5️⃣ Appointment Scheduling System
- Book appointments for leads
- Assign agent for meeting
- Track appointment status (Pending, Completed, Cancelled, Rescheduled)
- Enforce no appointment scheduling in the past

### ✅ 6️⃣ Client Feedback Collection
- Leads give 1-5 star feedback post-interaction
- Managers review feedback and agents’ performance

### ✅ 7️⃣ Notifications System
- Task notifications
- System alerts
- AI updates
- Reminder notifications
- Mark as read/unread

### ✅ 8️⃣ Full Admin Panel & Audit Logs
- Admins view all platform changes
- Track actions by users
- Complete system observability

### ✅ 9️⃣ Full Analytics Dashboard
- Total leads count
- Hot/Warm/Cold ratio
- Weekly lead generation trendline
- Conversion ratio calculations
- Top performing agent metrics

### ✅ 🔒 Security Features
- JWT secured API endpoints
- SQL Injection prevention (sanitized inputs)
- Rate limiting on login
- Encrypted tokens and credentials
- Hashed passwords using bcrypt
- Full activity logs

### ✅ ⚙️ Scalability Features
- Supabase cloud-native Postgres (scalable to millions of leads)
- Serverless backend compatible (Railway, Render, Vercel)
- Fully decoupled frontend-backend architecture
- Horizontally scalable microservice ready APIs

---

## 🧩 Database Schema (Supabase)

### `users` Table
| Field | Type | Description |
|----|----|----|
| id | UUID (PK) | User ID |
| full_name | Text | User's full name |
| email | Text | Unique email |
| password | Hashed | Encrypted password |
| role | Enum | Admin, Manager, SalesAgent |
| phone_number | Text | Contact |
| profile_picture | Text | URL |
| is_active | Boolean | Active status |
| created_at | Timestamp | Created timestamp |

### `leads` Table
| Field | Type | Description |
|----|----|----|
| id | UUID (PK) | Lead ID |
| user_id | UUID | Assigned agent |
| lead_name | Text | Lead full name |
| lead_email | Text | Email |
| lead_phone | Text | Phone |
| company_name | Text | Company |
| company_size | Text | Size of business |
| service_interested | Text | Service interest |
| budget_range | Text | Budget |
| timeframe | Text | Timeframe to buy |
| engagement_notes | Text | Message details |
| lead_score | Enum | Hot, Warm, Cold |
| ai_explanation | Text | AI explanation |
| lead_source | Enum | Website, Referral, Instagram, etc |
| assigned_by | UUID | Assigned by whom |
| assigned_date | Timestamp | Assigned timestamp |
| created_at | Timestamp | Created timestamp |

### Additional Tables:  
- `appointments`  
- `feedback`  
- `notifications`  
- `audit_logs`  
- `settings`

---

## 🔧 API Endpoints

| Method | Endpoint | Description |
|----|----|----|
| POST | `/register` | User Registration |
| POST | `/login` | User Login |
| POST | `/forgot-password` | Password Reset |
| GET/POST/PUT/DELETE | `/leads` | Lead CRUD |
| POST | `/leads/{lead_id}/score` | AI Scoring Endpoint |
| CRUD | `/appointments` | Appointment Module |
| CRUD | `/feedback` | Feedback Module |
| CRUD | `/notifications` | Notifications |
| CRUD | `/audit-logs` | Audit Logs |
| CRUD | `/settings` | System Settings |

---

## 💻 Tech Stack Summary

| Layer | Tech |
|---|---|
| Frontend | React (Windsurf) |
| Backend | Node.js (Horizon Generated) |
| Database | Supabase PostgreSQL |
| Authentication | JWT |
| File Storage | Supabase Storage |
| Deployment | Vercel / Railway / Render |
| AI Logic | Horizon Rule-based engine |

---

## 🚀 Deployment Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-team-name/leadflow-ai.git
cd leadflow-ai
2️⃣ Install Frontend Dependencies
bash
Copy
Edit
npm install
3️⃣ Setup Environment Variables (.env)
bash
Copy
Edit
VITE_API_URL=https://your-deployed-backend-url/api
VITE_SUPABASE_URL=https://your-supabase-url
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
JWT_SECRET=your-jwt-secret
4️⃣ Deploy Backend
Deploy Node.js backend to Railway/Render/Vercel.

Connect to your Supabase Database.

5️⃣ Deploy Frontend
Deploy React frontend using Vercel or Netlify.

6️⃣ Supabase SQL Setup
Run full database SQL schema script inside Supabase SQL Editor.

👨‍💻 Team Members
Name	Role
Pankaj	Team Leader(front-end developer)
Rajnandini database(supabase)
Bhagyashree	front-end desiner
Akash	Testing & Validation

🎥 Demo Video
👉 Watch Demo

🔬 Future Scope (Post Hackathon)
Payment Integration for SaaS licensing

Team Collaboration

Pipeline Kanban Boards

Lead Enrichment APIs

Zapier Integration

WhatsApp + Email Bots

Marketing Automation Sequences

📩 Contact
📧 your-team-email@example.com
