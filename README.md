# 💜 MediCare by FLOREX

> **MediCare V9 --- A modern healthcare management platform built with
> Flask, SQLAlchemy and a responsive web UI.**

```{=html}
<p align="center">
```
`<b>`{=html}🏥 Build • Test • Fix • Improve`</b>`{=html}`<br>`{=html}
`<i>`{=html}FLOREX Healthcare Project`</i>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## ✦ About

**MediCare V9** is a Flask-based healthcare management web application
created as a practical BCA full-stack project.

The purpose is to connect patients, doctors and administration through
one organized platform instead of keeping appointments, prescriptions,
profiles and billing workflows separate.

### Core idea

**Patient → Doctor → Appointment → Prescription → Billing**

The final V9 build focuses on a product-style experience with responsive
UI, authentication, role-aware portals, connected healthcare workflows
and a protected administration area.

------------------------------------------------------------------------

## 🚀 Features

### 👤 Patient Portal

-   Profile management
-   Doctor discovery
-   Appointment booking
-   Appointment status
-   Prescription records
-   Billing information

### 🩺 Doctor Portal

-   Appointment management
-   Availability
-   Patient-related prescription workflows
-   Professional profile
-   Appointment notes

### 🛡️ Admin Panel

-   Protected admin authentication
-   Registered-user statistics
-   Patient/doctor statistics
-   Appointment information
-   Recent registrations and activity
-   System overview

### 📅 Appointments

1.  Check doctor availability
2.  Validate the future date
3.  Detect scheduling conflicts
4.  Book the appointment
5.  Confirm/reschedule
6.  Complete with notes
7.  Connect billing

### 💊 Prescriptions

Doctors can create prescriptions containing medicine, dosage, duration
and instructions.

### 💳 Billing

Appointments can have linked invoices with amount and payment status.

------------------------------------------------------------------------

## 🧠 Technology Stack

  Layer               Technology
  ------------------- -------------------------------
  Backend             **Python + Flask**
  Frontend            **HTML5 + CSS3 + JavaScript**
  Templates           **Jinja**
  ORM                 **SQLAlchemy**
  Database            **PostgreSQL / SQLite**
  Authentication      **Flask Sessions + Werkzeug**
  Production Server   **Gunicorn**
  Deployment          **Railway**
  Icons               **Font Awesome**

------------------------------------------------------------------------

## 🏗️ Architecture

``` text
Browser
   ↓
Responsive UI
   ↓
Flask Routes + Authentication
   ↓
Application / Healthcare Workflows
   ↓
SQLAlchemy ORM
   ↓
PostgreSQL / SQLite
   ↓
Response
```

The main application flow is:

**Browser → Flask → Logic → SQLAlchemy → Database → Response**

------------------------------------------------------------------------

## 🗃️ Core Data Model

``` text
Patient
   │
   ├──────► Appointment ◄────── Doctor
   │                 │
   │                 └──────► Invoice
   │
   └──────► Prescription ◄──── Doctor
```

Main entities:

-   `User / Patient`
-   `Doctor`
-   `Appointment`
-   `Prescription`
-   `Invoice`

------------------------------------------------------------------------

## 🔐 Security

V9 includes security-focused application design such as:

-   🔑 Werkzeug password hashing
-   👥 Role-based authorization
-   🔒 Protected routes
-   🛡️ Ownership checks
-   🍪 HTTP-only / SameSite session configuration
-   🔐 Secure cookies when HTTPS is enabled
-   🌱 Environment-based production secrets
-   🧩 CSRF protection for protected state-changing actions
-   🧱 Security headers
-   🚫 Server-side authorization
-   🔐 Protected admin authentication

**Never commit real passwords, API keys or production secrets to
GitHub.**

------------------------------------------------------------------------

## 🎨 UI / UX

The V9 interface uses a modern healthcare-product style:

-   Deep navy background
-   Purple/pink accents
-   Clean typography
-   Rounded cards
-   Healthcare imagery
-   Responsive layouts
-   Mobile navigation
-   Focused information hierarchy
-   Smooth interactions
-   Accessibility/focus states
-   Reduced-motion support
-   Dark/light experience

The pages use purpose-specific layouts instead of making every screen
look identical.

------------------------------------------------------------------------

## 📱 Responsive Design

MediCare is designed for:

**📱 Mobile • 💻 Desktop • 🖥️ Larger screens**

Navigation, forms, cards, dashboards and hero sections adapt to smaller
displays.

------------------------------------------------------------------------

## 📂 Project Structure

``` text
MediCare_byFLOREX/
│
├── app.py
├── requirements.txt
├── Procfile
├── .env.example
│
├── static/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── img/
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
    ├── admin.html
    ├── admin_login.html
    └── about.html
```

------------------------------------------------------------------------

## ⚙️ Local Setup

### 1. Clone

``` bash
git clone https://github.com/hereflorex/Medicare_byFLOREX.git
cd Medicare_byFLOREX
```

### 2. Virtual environment

``` bash
python -m venv venv
```

Linux/macOS:

``` bash
source venv/bin/activate
```

Windows:

``` bash
venv\Scripts\activate
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

### 4. Configure `.env`

Use `.env.example` as the template. Production configuration can
include:

``` env
SECRET_KEY=your-secret-key
DATABASE_URL=your-database-url
ADMIN_EMAIL=your-admin-email
ADMIN_PASSWORD=your-admin-password
```

Keep real credentials private.

### 5. Run

``` bash
python app.py
```

------------------------------------------------------------------------

## ☁️ Deployment

MediCare is prepared for production deployment with **Gunicorn** and
**Railway**.

``` text
GitHub
  ↓
Railway
  ↓
Dependencies
  ↓
Gunicorn
  ↓
Flask
  ↓
PostgreSQL
```

Production secrets should be supplied through environment variables.

------------------------------------------------------------------------

## 🧩 Development Journey

### V1 → V7

The application grew from a functional healthcare website into a larger
database-driven healthcare platform.

### V8

The focus moved toward responsive behavior, navigation and a more
polished UI.

### V9

The final iteration focused on:

-   Complete UI refinement
-   Responsive/mobile improvements
-   Authentication improvements
-   Protected admin workflows
-   Security hardening
-   Appointment validation
-   Healthcare-specific visuals
-   Accessibility improvements
-   Deployment readiness

------------------------------------------------------------------------

## 🧠 What I Learned

Building MediCare involved more than creating pages.

### Flask

Routes, requests, sessions, templates and server-side application logic.

### SQLAlchemy

Using an ORM to connect application models with relational database
records.

### Authentication

Understanding:

**Authentication → Who are you?**

**Authorization → What are you allowed to access?**

### Database Design

Connecting patients, doctors, appointments, prescriptions and invoices.

### Frontend Integration

Connecting HTML, CSS, JavaScript and Flask/Jinja into one application.

### Deployment

Working with dependencies, environment variables, Gunicorn and Railway.

### Debugging

Finding and fixing route, template, dependency, authentication,
responsive and deployment issues.

------------------------------------------------------------------------

## 🌌 FLOREX Build Mindset

> **Code doesn't have to look ordinary.**

``` text
Think → Build → Break → Debug → Improve → Ship
```

A little anime-inspired developer mindset:

**Train like a shonen protagonist.\
Debug like a detective.\
Ship like a builder. ⚔️**

No magic. Just iterations.

------------------------------------------------------------------------

## 👨‍💻 Developer Credits

### 💜 DHVANIT / SIR FLOREX

**Full-Stack & UI Developer**

-   GitHub: [@hereflorex](https://github.com/hereflorex)
-   Instagram: [@attached_being](https://instagram.com/attached_being)
-   Brand: **FLOREX**

Focus: - Flask integration - Frontend/UI - Authentication workflows -
Database integration - Responsive design - Deployment - Project
organization - Product experience

### ⚡ TIRTH / ZORRO

**Collaborator**

-   Contribution: collaborative development and application workflow
-   Instagram: Coming soon

------------------------------------------------------------------------

## 🏷️ Credits

**MediCare V9**\
Built under the **FLOREX** project identity.

> Designed, developed, tested and improved as a practical BCA full-stack
> project.

------------------------------------------------------------------------

## 🔗 Links

-   🌐 **Live Project:** https://icareflorex.up.railway.app
-   💻 **GitHub:** https://github.com/hereflorex/Medicare_byFLOREX.git

------------------------------------------------------------------------

## 📌 Project Status

**MediCare V9 --- Final Academic / Portfolio Build**

Demonstrates:

-   Full-stack web development
-   Flask backend development
-   Database-driven workflows
-   Authentication & authorization
-   Responsive UI/UX
-   Healthcare workflow design
-   Cloud deployment

------------------------------------------------------------------------

```{=html}
<p align="center">
```
### 💜 MediCare by FLOREX

**Build • Test • Fix • Improve**

`Python` `Flask` `SQLAlchemy` `PostgreSQL` `JavaScript` `Railway`

```{=html}
</p>
```
