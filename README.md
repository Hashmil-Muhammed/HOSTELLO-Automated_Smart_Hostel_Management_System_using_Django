<div align="center">
  <img src="https://img.shields.io/badge/HOSTELLO-Admin-092E20?style=for-the-badge&logo=django" alt="Hostello Logo">
  
  <h3>HOSTELLO</h3>
  <p>Automated Smart Hostel Management System using Django</p>

  <p>
    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
    <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white" alt="Django">
    <img src="https://img.shields.io/badge/SQLite-07405E?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite">
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5">
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" alt="CSS3">
    <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
    <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white" alt="Bootstrap">
  </p>
</div>

> **HOSTELLO** is a comprehensive, automated smart hostel management system designed to streamline and digitize daily hostel operations. By minimizing manual paperwork and maximizing efficiency, it provides a seamless experience for administrators and students alike—handling attendance, absence alerts, room allocation, and fee management in one secure platform.

---

## 📋 Table of Contents
- [🌟 Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🏗️ System Architecture](#️-system-architecture)
- [💻 Tech Stack](#-tech-stack)
- [📁 Project Structure](#-project-structure)
- [🗄️ Database Schema](#️-database-schema)
- [📸 Application Screens](#-application-screens)
- [🚀 Running the Application](#-running-the-application)
- [🔒 Security](#-security)
- [📜 License](#-license)

---

## 🌟 Project Overview
HOSTELLO tackles the chaotic administration of student accommodations by moving all critical operations—from daily room/mess attendance to grievance reporting—onto a centralized digital platform. The inclusion of automated guardian notifications ensures safety and accountability are maintained seamlessly.

---

## ✨ Key Features
- **⏰ Smart Attendance System:** Daily tracking of student presence in rooms and the mess, complete with historical records.
- **📩 Automated Guardian Alerts:** Automatically sends email alerts to parents/guardians when a student is absent beyond the warning or critical thresholds.
- **🛏️ Room Assignment & Management:** Efficient allocation and tracking of hostel rooms, visualizing occupancy and availability.
- **💳 Fee Management:** Transparent tracking of hostel and mess fees, with integrated Stripe payment functionality.
- **📝 Student Requests Portal:** A centralized ticketing system for students to submit complaints, maintenance requests, or leave applications.
- **📢 Notice Board:** Digital bulletin board to instantly broadcast announcements to all registered students.

---

## 🏗️ System Architecture

```text
    +-------------------+           HTTP/JSON            +-----------------------+
    |                   |  <==========================>  |                       |
    |  Frontend Web UI  |                                |   Django Web Server   |
    |  (HTML/CSS/JS)    |  <-------------------------->  |   (Views/URLs/APIs)   |
    |                   |           Templates            |                       |
    +-------------------+                                +-----------+-----------+
                                                                     |
                                                                     | ORM
                                                                     v
    +-------------------+                                +-----------+-----------+
    |                   |                                |                       |
    |   External APIs   |  <==========================>  |     Django Models     |
    | (Stripe, SMTP)    |      Payments & Emails         |    (Business Logic)   |
    |                   |                                |                       |
    +-------------------+                                +-----------+-----------+
                                                                     |
                                                                     | SQL
                                                                     v
                                                         +-----------+-----------+
                                                         |                       |
                                                         |    SQLite Database    |
                                                         |     (Data Storage)    |
                                                         |                       |
                                                         +-----------------------+
```

---

## 💻 Tech Stack

### Frontend
| Technology | Description |
| :--- | :--- |
| **HTML5** | Semantic structure for all dashboard views. |
| **CSS3** | Premium styling and responsive layout designs. |
| **JavaScript** | Interactive DOM elements and asynchronous logic. |
| **Bootstrap**| Clean and consistent UI component framework. |

### Backend
| Technology | Description |
| :--- | :--- |
| **Python 3.10+** | Core programming language. |
| **Django 5.x** | High-level web framework for rapid development. |
| **Django REST** | Toolkit for building Web APIs. |

### Database & Tools
| Technology | Description |
| :--- | :--- |
| **SQLite** | Lightweight, robust local data storage. |
| **django-jazzmin** | Premium customized admin panel interface. |

---

## 📁 Project Structure

```text
HOSTELLO/
├── hostello_backend/
│   ├── accounts/             # Custom user models & auth logic
│   ├── attendance/           # Room and Mess attendance tracking
│   ├── fees/                 # Payments and fee management
│   ├── hostello_backend/     # Main project settings & routing
│   │   ├── settings.py
│   │   └── urls.py
│   ├── notices/              # Notice board broadcasting
│   ├── requests/             # Student complaints/leave ticketing
│   ├── students/             # Student profiles & room allocation
│   ├── static/               # CSS, JS, and Images
│   ├── templates/            # HTML Django templates
│   ├── manage.py
│   └── requirements.txt
├── .env                      # Environment variables (git-ignored)
├── .gitignore
├── README.md
├── run_backend.bat           # Startup script
└── run_frontend.bat          # Startup script
```

---

## 🗄️ Database Schema

| Model Name | Purpose | Key Relationships |
| :--- | :--- | :--- |
| **User** | Custom authentication model (Admin/Warden). | Base model. |
| **Student** | Stores student details, guardian info, room info. | O2O with User, FK to Room. |
| **RoomAttendance** | Daily presence/absence tracking in rooms. | FK to Student. |
| **MessAttendance** | Daily presence/absence tracking in the mess. | FK to Student. |
| **Fee** | Logs fee types, amounts, and payment status. | FK to Student. |
| **StudentRequest** | Stores complaints, leave apps, and status. | FK to Student. |
| **Notice** | Global announcements for the dashboard. | Broadcast model. |

---

## 📸 Application Screens

| Login & Authentication | Admin Dashboard |
| :---: | :---: |
| <img src="assets/login.png" alt="Login Screen" width="400" /> | <img src="assets/dashboard.png" alt="Dashboard" width="400" /> |
| **Student Portal** | **Attendance Tracking** |
| <img src="assets/student_portal.png" alt="Student Portal" width="400" /> | <img src="assets/attendance.png" alt="Attendance" width="400" /> |

*(Note: Replace `assets/*.png` with your actual image paths once screens are captured)*

---

## 🚀 Running the Application

### 1. Clone the Repository
```bash
git clone https://github.com/Hashmil-Muhammed/HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django.git
cd HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django
```

### 2. Set Up Virtual Environment
```bash
python -m venv hostello_env
# Windows:
hostello_env\Scripts\activate
# macOS/Linux:
source hostello_env/bin/activate
```

### 3. Install Dependencies
```bash
cd hostello_backend
pip install -r requirements.txt
```

### 4. Configure Environment Variables
Create a `.env` file in the `hostello_backend/hostello_backend/` directory:
```env
SECRET_KEY=your-secure-django-secret-key-here
DEBUG=True

# Email Configuration
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password

# Stripe API Keys (Optional)
STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
STRIPE_SECRET_KEY=your-stripe-secret-key
STRIPE_WEBHOOK_SECRET=your-stripe-webhook-secret
```

### 5. Run Migrations & Create Superuser
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```

### 6. Start the Server
```bash
python manage.py runserver
```
Access the application at `http://127.0.0.1:8000/`.

---

## 🔒 Security
- All sensitive credentials (API keys, Emails, Secrets) are stored securely in `.env`.
- Cross-Origin Resource Sharing (CORS) is strictly configured.
- Protected by Django's native CSRF & XSS prevention layers.

---

## 📜 License
This project is licensed under the MIT License.

<div align="center">
  <br>
  <p>Built with 💻 and ☕ for seamless hostel management.</p>
</div>
