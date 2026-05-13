# HOSTELLO: Automated Smart Hostel Management System using Django

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

## Overview

**HOSTELLO** is an automated, smart hostel management system designed to streamline and digitize the daily operations of hostel accommodations. Built with Django, this comprehensive platform provides a seamless experience for both hostel administrators (wardens) and students, minimizing manual paperwork and maximizing operational efficiency.

The system handles everything from attendance tracking to automated absence notifications, room allocation, fee management, and handling student requests, all within a secure and user-friendly interface.

## Key Features

- **Smart Attendance System**: Daily tracking of student presence in rooms and the mess, complete with historical records.
- **Automated Guardian Notifications**: Automatically sends email alerts to parents/guardians when a student is absent beyond the warning or critical thresholds.
- **Room Assignment & Management**: Efficient allocation and tracking of hostel rooms, visualizing occupancy and availability.
- **Fee Management**: Transparent tracking of hostel and mess fees, with integrated Stripe payment functionality (if configured).
- **Student Requests Portal**: A centralized ticketing system for students to submit complaints, maintenance requests, or leave applications, and for wardens to manage them.
- **Notice Board**: Digital bulletin board to instantly broadcast announcements to all registered students.

## Tech Stack

- **Backend**: Python 3.10+, Django 5.x, Django REST Framework
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla/ES6+)
- **Database**: SQLite (Development) / PostgreSQL (Ready for Production)
- **Authentication**: Custom User Model, Django Session Authentication
- **Admin Dashboard**: Customized using `django-jazzmin`

## Installation and Setup Guide

Follow these steps to run the HOSTELLO project locally on your machine.

### Prerequisites

- [Python](https://www.python.org/downloads/) (v3.10 or higher)
- [Git](https://git-scm.com/downloads)

### 1. Clone the Repository

```bash
git clone https://github.com/Hashmil-Muhammed/HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django.git
cd HOSTELLO_Automated_Smart_Hostel_Management_System_using_Django
```

### 2. Set Up Virtual Environment

It is recommended to use a virtual environment to manage project dependencies.

```bash
# Create the virtual environment
python -m venv hostello_env

# Activate the virtual environment
# For Windows:
hostello_env\Scripts\activate
# For macOS/Linux:
source hostello_env/bin/activate
```

### 3. Install Dependencies

Navigate to the backend directory and install the required Python packages.

```bash
cd hostello_backend
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file inside the `hostello_backend/hostello_backend/` directory (where `settings.py` is located) and add the following keys. **Do not skip this step, as sensitive keys have been removed from the source code.**

```env
SECRET_KEY=your-secure-django-secret-key-here
DEBUG=True

# Email Configuration (For Automated Notifications)
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password

# Stripe API Keys (Optional for local testing if you don't need payments)
STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
STRIPE_SECRET_KEY=your-stripe-secret-key
STRIPE_WEBHOOK_SECRET=your-stripe-webhook-secret
```

### 5. Run Database Migrations

Apply the database migrations to set up your local SQLite database.

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create Superuser (Admin)

Create an admin account to access the Jazzmin dashboard.

```bash
python manage.py createsuperuser
```

### 7. Run the Development Server

Start the Django development server.

```bash
python manage.py runserver
```

You can now access the application at `http://127.0.0.1:8000/`. To access the admin panel, navigate to `http://127.0.0.1:8000/admin/` and log in with your superuser credentials.

## License

This project is licensed under the MIT License.
