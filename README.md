# MediCare — Hospital Management System

> A full-stack healthcare management platform built as a BCA project to bring patients, doctors, appointments, prescriptions and billing into one organized workflow.

**Built by:** Dhvanit & Tirth  
**Project:** BCA Academic Project  
**Location:** Modasa, Gujarat, India  
**Year:** 2026

---

## Overview

**MediCare** is a full-stack hospital management system designed to simplify common healthcare workflows through a single web application.

The project provides separate experiences for **patients, doctors and administrators**, with role-aware authentication and dashboards. Patients can manage appointments, view prescriptions, maintain their profiles and handle invoices, while doctors can manage availability, appointments and prescriptions. An administrative dashboard provides a high-level view of platform activity.

The application was developed with a focus on practical backend logic, database relationships, authentication, responsive UI and deployment readiness.

---

## What MediCare Solves

Traditional hospital workflows can become fragmented across appointments, patient information, prescriptions and billing.

MediCare brings these core workflows together:

- Patient and doctor accounts
- Role-based access
- Doctor discovery and availability
- Appointment booking and management
- Digital prescriptions
- Patient profiles and medical history
- Appointment-linked billing
- Administrative monitoring
- Responsive web interface
- Secure password hashing and session-based authentication

---

## Core Features

### Patient Portal

Patients can:

- Create an account and sign in
- View their personal dashboard
- Browse available doctors
- Search doctors by name or specialization
- Book appointments
- Reschedule or cancel appointments
- View appointment status and notes
- View prescriptions
- View invoices
- Pay pending invoices within the application
- Update personal information
- Change their password

### Doctor Portal

Doctors can:

- Register and sign in using the doctor role
- View their dashboard
- Manage availability
- Review appointments
- Confirm or complete appointments
- Add appointment notes
- Create prescriptions for patients
- View patient-related prescription information
- Maintain professional profile information

### Admin Panel

The admin area provides a system-level overview including:

- Total patients
- Total doctors
- Total appointments
- Total prescriptions
- Pending bills
- Completed appointments
- Recent appointment activity
- Protected admin authentication

### Appointment Workflow

The appointment system includes:

1. Doctor availability checking
2. Future-date validation
3. Appointment conflict detection
4. Booking
5. Confirmation
6. Rescheduling
7. Cancellation
8. Completion with doctor notes
9. Automatic invoice creation

### Prescription Management

Doctors can create prescriptions containing:

- Medication
- Dosage
- Duration
- Instructions
- Patient association
- Doctor association
- Creation timestamp

Patients can access prescriptions connected to their account.

### Billing

Each newly created appointment can generate an associated invoice.

The billing workflow supports:

- Pending invoices
- Paid invoices
- Appointment-linked billing records
- Patient-only invoice access
- Payment status updates

---

## Technology Stack

| Layer | Technology |
|---|---|
| Backend | Python |
| Framework | Flask |
| ORM | Flask-SQLAlchemy |
| Database | PostgreSQL / SQLite |
| Authentication | Flask Sessions |
| Password Security | Werkzeug Password Hashing |
| Frontend | HTML5, CSS3, JavaScript |
| Icons | Font Awesome |
| Fonts | Inter / Manrope |
| Production Server | Gunicorn |
| Deployment | Railway-ready |
| Configuration | python-dotenv |

---

## Architecture

MediCare follows a lightweight Flask application architecture:

```text
Browser
   │
   ▼
Flask Routes
   │
   ├── Authentication
   ├── Patient Portal
   ├── Doctor Portal
   ├── Admin Panel
   ├── Appointment APIs
   ├── Prescription APIs
   ├── Billing APIs
   └── Profile APIs
          │
          ▼
   SQLAlchemy ORM
          │
          ▼
 PostgreSQL / SQLite
```

The frontend uses Jinja templates for page rendering and JavaScript for API-driven dashboard interactions.

---

## Project Structure

```text
MEDICARE-main/
├── app.py
├── requirements.txt
├── Procfile
├── .env.example
├── README.md
│
├── static/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── img/
│       ├── dhvanit.jpg
│       ├── tirth.jpg
│       └── hero-fuji.jpg
│
└── templates/
    ├── base.html
    ├── index.html
    ├── login.html
    ├── register.html
    ├── dashboard.html
    ├── doctors.html
    ├── appointments.html
    ├── prescriptions.html
    ├── billing.html
    ├── profile.html
    ├── about.html
    ├── admin_login.html
    └── admin.html
```

---

## Database Design

The application uses relational models for its main healthcare entities:

```text
Patient
   │
   ├── Appointments ───── Doctor
   │
   ├── Prescriptions ──── Doctor
   │
   └── Invoices ───────── Appointment
```

### Main Models

- `Patient`
- `Doctor`
- `Appointment`
- `Prescription`
- `Invoice`

Relationships are managed through SQLAlchemy, with foreign keys connecting appointments, prescriptions and invoices to their related users and records.

---

## Authentication & Security

MediCare implements session-based authentication with role-aware access control.

Security-related implementation includes:

- Password hashing using Werkzeug
- HTTP-only session cookies
- SameSite cookie configuration
- Configurable secure cookies for HTTPS deployments
- Role-based route protection
- Ownership checks before modifying appointments
- Patient-only billing access
- Doctor-only prescription creation
- Environment-based production secrets
- Separate admin authentication flow

> This project is an academic/demo system and should receive additional security hardening before being used with real patient data or in a production healthcare environment.

---

## Environment Variables

Create a `.env` file for local configuration.

```env
SECRET_KEY=replace-with-a-long-random-secret

DATABASE_URL=postgresql://user:password@host:5432/database

ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=replace-with-a-strong-password

SESSION_COOKIE_SECURE=0
```

For a production HTTPS deployment, use:

```env
SESSION_COOKIE_SECURE=1
```

Never commit real passwords, database credentials or production secrets to GitHub.

---

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/hereflorex/Medicare_by_FLOREX.git
cd Medicare_by_FLOREX
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**Linux / macOS**

```bash
source .venv/bin/activate
```

**Windows**

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Copy `.env.example` to `.env` and add your local configuration.

### 5. Start the application

```bash
python app.py
```

The application runs on:

```text
http://127.0.0.1:5000
```

---

## Railway Deployment

MediCare is structured for deployment on **Railway**.

Recommended production variables:

```env
SECRET_KEY=<strong-random-secret>
DATABASE_URL=<railway-postgresql-url>
ADMIN_EMAIL=<admin-email>
ADMIN_PASSWORD=<strong-admin-password>
SESSION_COOKIE_SECURE=1
```

The included `Procfile` uses Gunicorn as the production application server.

---

## Application Routes

### Public

```text
/
 /login
 /register
 /about
 /admin/login
```

### Authenticated Application

```text
/dashboard
/doctors
/appointments
/prescriptions
/billing
/profile
```

### Admin

```text
/admin
/admin/login
/admin/logout
```

### API

```text
/api/auth/register
/api/auth/login
/api/auth/logout
/api/auth/me

/api/doctors
/api/doctors/availability

/api/dashboard

/api/appointments
/api/appointments/<id>

/api/prescriptions

/api/billing
/api/billing/<id>/pay

/api/profile
/api/auth/change-password
```

---

## UI & Experience

The interface was designed around a modern healthcare dashboard concept rather than a traditional basic college-project layout.

The frontend includes:

- Responsive layouts
- Patient and doctor dashboards
- Dedicated admin interface
- Dark/light theme support
- Mobile navigation
- Reusable buttons and cards
- Status indicators
- Appointment and billing panels
- Developer/project information page
- Responsive typography
- Font Awesome iconography

---

## Project Screens

The repository includes the main application screens for:

- Landing page
- Authentication
- Patient dashboard
- Doctor dashboard
- Doctor directory
- Appointments
- Prescriptions
- Billing
- Profile
- Admin dashboard
- Project / developer information

---

## Development Notes

MediCare was developed as a practical learning project around:

- Flask application development
- REST-style API endpoints
- Relational database design
- SQLAlchemy relationships
- Authentication and authorization
- Frontend/backend integration
- Responsive web design
- Deployment configuration
- Debugging and iterative project development

The goal was not only to create pages, but to connect them into a functional application workflow.

---

## Future Improvements

Potential future versions could introduce:

- Real payment gateway integration
- Email and SMS appointment reminders
- Doctor schedule/calendar management
- File uploads for medical documents
- Advanced admin management
- Appointment time-slot generation
- Better audit logging
- Database migrations with Alembic/Flask-Migrate
- CSRF protection for state-changing requests
- Production-grade API validation
- Automated testing and CI
- More granular permissions
- Real healthcare integrations where appropriate

---

## 🥢 About the Developers

MediCare is not just a college submission — it is a practical project built by two BCA students to turn classroom concepts into a working healthcare platform. The project combines frontend design, backend development, database management, authentication and real-world workflow logic into one system.

### ⚡ Dhvanit — Full-Stack & UI Developer

**GitHub:** `@hereflorex`  
**Contact:** `@ByteCs`

Dhvanit focuses on the overall product experience and the technical integration of MediCare. His work covers the user interface, responsive layouts, frontend-backend connection, project structure and the visual presentation of the application.

**Key contribution areas:**
- 🎨 Professional and responsive web interface
- 🧩 Frontend and backend integration
- 🛠️ Flask application structure and feature integration
- 🔐 Authentication, sessions and role-based access
- 🗄️ Database-connected healthcare workflows
- 📱 Responsive experience across different screen sizes
- 🚀 Railway-ready deployment and project configuration
- 📦 GitHub project organization and documentation

The goal behind his contribution is simple: make the application feel like a usable product rather than just a basic academic demo.

### 🛠️ Tirth — Backend & Application Logic Developer

Tirth focuses on the application logic and backend workflow that keeps the MediCare system functional and organized.

**Key contribution areas:**
- ⚙️ Backend workflow implementation
- 🗄️ Database models and relationships
- 📅 Appointment management logic
- 💊 Prescription workflow
- 💳 Billing and invoice handling
- 👨‍⚕️ Doctor and patient management
- 🔒 Role-based application access
- 🔗 Connecting different modules into one workflow

His contribution helped turn individual healthcare features into a connected system where patients, doctors and administrators can work through their respective portals.

### 🚀 Our Approach

The development of MediCare follows a practical approach: **build → test → fix → improve**.

Instead of stopping at basic CRUD functionality, the project focuses on real application behavior such as appointment conflicts, user roles, authentication, ownership checks, doctor availability, prescriptions and billing relationships.

The project is also designed with future expansion in mind, allowing additional healthcare features and improvements to be added without rebuilding the entire system from scratch.

### 🥢 FLOREX Development

MediCare is also part of the wider **FLOREX** development work, where the focus is on building practical software, experimenting with modern web technologies and turning ideas into usable projects.

**Developer:** Dhvanit / FLOREX  
**GitHub:** `@hereflorex`  
**Telegram:** `@ByteCs`

## Academic Context

MediCare was developed as a **BCA academic project** by students from:

**M. L. Gandhi Modasa**  
Modasa, Gujarat, India

The project demonstrates how a real-world healthcare workflow can be modeled using a modern web application stack.

---

## Project Status

**Current status:** Active academic / portfolio project

The core healthcare workflow is implemented, including authentication, role-based portals, appointments, prescriptions, billing, profiles and administration.

Further improvements can be made as the project evolves.

---

## License

This project is intended primarily for educational, demonstration and portfolio purposes.

If you plan to reuse or redistribute the project, please review and define an appropriate license for your intended use.

---

## Developer

**FLOREX**

Building projects around software development, automation, web applications and practical technology experiments.

GitHub: `@hereflorex`  
Telegram: `@ByteCs`

---

<p align="center">
  Built with Python, Flask, SQLAlchemy and a lot of iteration.
</p>
