<div align="center">
  <img src="https://img.shields.io/badge/HOSTELLO-Admin-092E20?style=for-the-badge&logo=django" alt="Hostello Logo">
  
  <h1>HOSTELLO</h1>
  <h3>Automated Smart Hostel Management System</h3>

  <p>
    <a href="https://hashmil.pythonanywhere.com/" target="_blank">
      <img src="https://img.shields.io/badge/🔴_Live_Demo-hashmil.pythonanywhere.com-success?style=for-the-badge" alt="Live Demo">
    </a>
  </p>

  <p>
    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
    <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white" alt="Django">
    <img src="https://img.shields.io/badge/SQLite-07405E?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite">
    <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white" alt="Bootstrap">
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5">
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" alt="CSS3">
    <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
  </p>
</div>

---

## 📖 Project Overview
**HOSTELLO** is a comprehensive, automated smart hostel management system built with Django. It is designed to streamline and digitize daily hostel operations, minimizing manual paperwork and maximizing efficiency. The platform provides a seamless experience for both administrators and students—handling attendance, absence alerts, room allocation, fee management, and grievance reporting in one secure, unified portal.

---

## ✨ Key Features

### 👨‍💼 Admin Features
- **Dashboard Analytics:** Visual overview of total students, available rooms, fee collections, and recent activities.
- **Room Assignment & Management:** Efficient allocation and tracking of hostel rooms. Admins can create rooms, set capacities, and assign students based on preferences.
- **Smart Attendance System:** Daily tracking of student presence in rooms and the mess. 
- **Automated Guardian Alerts:** Automatically sends email alerts to parents/guardians when a student is absent beyond warning or critical thresholds.
- **Fee Management:** Transparent tracking of hostel and mess fees. Admins can generate fee invoices and track payment statuses.
- **Notices Broadcasting:** Create and publish digital announcements that instantly reflect on the student dashboard.
- **Request Management:** Handle student complaints, maintenance requests, and leave applications efficiently.
- **Premium Admin Interface:** Integrated with Jazzmin for a beautiful, responsive, and highly customizable administration panel.

### 🎓 Student Features
- **Student Dashboard:** Personalized portal displaying room details, attendance records, and pending dues.
- **Notice Board:** Real-time access to important announcements and hostel notices.
- **Fee Portal:** View detailed fee breakdowns and track payment history securely.
- **Requests & Complaints:** Submit and track the status of maintenance requests, leave applications, or general complaints directly from the portal.

---

## 💻 Tech Stack

- **Backend:** Python, Django 5.x
- **Frontend:** HTML5, CSS3, JavaScript, Bootstrap 5
- **Database:** SQLite (Development) / PostgreSQL (Optional for Production)
- **Admin Theme:** Django Jazzmin
- **Deployment Platform:** PythonAnywhere

---

## ⚙️ How the System Works (Project Workflow)

HOSTELLO simplifies the complex workflow of hostel management into an intuitive digital process:

1. **Student Onboarding & Room Assignment:**
   - The Admin registers a new student profile with guardian details.
   - Using the Room Assignment module, the admin allocates a room based on real-time availability and student preferences (e.g., AC/Non-AC, Single/Double).
2. **Daily Operations (Attendance & Notices):**
   - Wardens or Admins mark daily room and mess attendance through a streamlined interface.
   - If a student's continuous absence crosses the predefined threshold, the system triggers an automated email alert to the registered guardian, ensuring safety and accountability.
   - Admins broadcast notices which immediately appear on every student's personalized dashboard.
3. **Fee Management:**
   - Admins generate monthly or semester-wise fee records for individuals or in bulk.
   - Students access their portal to view pending dues, preventing miscommunication and enabling transparent financial tracking.
4. **Grievance Redressal:**
   - Students submit leave applications or maintenance requests securely.
   - Admins review, approve, or reject these requests from the Jazzmin admin panel, which automatically updates the status for the student in real-time.

---

## 🚀 Installation & Setup Guide

### 📍 Local Setup

**1. Clone the Repository**
```bash
git clone https://github.com/Hashmil-Muhammed/HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django.git
cd HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django
```

**2. Set Up Virtual Environment**
```bash
python -m venv hostello_env

# Activate on Windows:
hostello_env\Scripts\activate

# Activate on macOS/Linux:
source hostello_env/bin/activate
```

**3. Install Dependencies**
```bash
cd hostello_backend
pip install -r requirements.txt
```

**4. Configure Environment Variables**
Create a `.env` file in the `hostello_backend/hostello_backend/` directory and add your configurations:
```env
SECRET_KEY=your-secure-django-secret-key-here
DEBUG=True

# Email Configuration (Required for Automated Guardian Alerts)
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password
```

**5. Run Migrations & Create Superuser**
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```

**6. Start the Local Server**
```bash
python manage.py runserver
```
*Access the frontend at `http://127.0.0.1:8000/` and the admin panel at `http://127.0.0.1:8000/admin/`*

---

### 🌐 PythonAnywhere Deployment Instructions

1. **Create an Account:** Sign up at [PythonAnywhere](https://www.pythonanywhere.com/).
2. **Upload Code:** Clone your repository directly into the PythonAnywhere bash console or upload your project files.
3. **Virtual Environment Setup:** 
   - Open a new Bash console.
   - Create a virtual environment: `mkvirtualenv --python=/usr/bin/python3.10 myenv`
   - Install requirements: `pip install -r hostello_backend/requirements.txt`
4. **Web App Configuration:**
   - Navigate to the **Web** tab and add a new web app (Select **Manual configuration**, Python 3.10).
   - Set the **Source code** directory to your `hostello_backend` folder path.
   - Set the **Virtualenv** path to the environment you just created.
5. **Configure the WSGI File:**
   - Edit the WSGI configuration file linked in the Web tab.
   - Import your Django project and set the environment variable:
     ```python
     import os
     import sys
     
     path = '/home/yourusername/HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django/hostello_backend'
     if path not in sys.path:
         sys.path.append(path)
         
     os.environ['DJANGO_SETTINGS_MODULE'] = 'hostello_backend.settings'
     
     from django.core.wsgi import get_wsgi_application
     application = get_wsgi_application()
     ```
6. **Collect Static Files:**
   - Run `python manage.py collectstatic` in the bash console.
   - In the Web tab, map the URL `/static/` to your project's static files directory.
7. **Database Migration:**
   - Run `python manage.py migrate` in the bash console to initialize your production database.
8. **Reload and Launch:** 
   - Click the green **Reload** button at the top of the Web tab. Your project is now live!

---

## 🔒 Security
- All sensitive credentials (such as Secret Keys and Email Passwords) are stored securely using environment variables (`.env`).
- Cross-Origin Resource Sharing (CORS) is strictly configured.
- Protected by Django's native CSRF & XSS prevention layers.
- Password hashing and secure authentication practices are enforced natively by Django.

---

## 📜 License
This project is licensed under the MIT License.

<div align="center">
  <br>
  <p>Built with 💻 and ☕ for seamless hostel management.</p>
</div>
