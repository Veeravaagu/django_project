![Django](https://img.shields.io/badge/Django-6.0-green)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Supabase-blue)
![Render](https://img.shields.io/badge/Render-Deployed-purple)
# 🚀 Django Blog App

A full-stack blog application built with Django, featuring authentication, user profiles, and full CRUD functionality.
Deployed in production using **Render (backend hosting)** and **Supabase (PostgreSQL database)** with production-grade configurations.

---

## 🌐 Live Demo

👉 [https://django-project-p85n.onrender.com](https://django-project-p85n.onrender.com)

---

## ✨ Features

* 🔐 User authentication (Register, Login, Logout)
* 👤 User profiles with profile picture support
* 📝 Create, update, and delete blog posts
* 📄 Paginated post feed
* 🖼️ Default avatar fallback (handled at model level)
* 🧠 Clean Django architecture (apps, models, templates)
* 🚀 Production deployment with environment variables
* 🗄️ PostgreSQL database via Supabase
* ⚡ Static file serving using WhiteNoise

---

## 🛠️ Tech Stack

**Backend**

* Django
* PostgreSQL (Supabase)

**Frontend**

* HTML
* CSS
* Bootstrap

**Deployment**

* Render (Web Service)
* Supabase (Managed PostgreSQL)

**Other Tools**

* Gunicorn
* WhiteNoise
* dj-database-url

---

## ⚙️ Architecture

Client (Browser)
↓
Render (Django + Gunicorn)
↓
Supabase (PostgreSQL)

---

## 🔧 Environment Variables

Set these in Render or `.env`:

SECRET_KEY=your_secret_key
DEBUG=False
DATABASE_URL=your_supabase_database_url
ALLOWED_HOSTS=your-render-domain
CSRF_TRUSTED_ORIGINS=[https://your-render-domain](https://your-render-domain)
EMAIL_USER=your_email
EMAIL_PASS=your_app_password

---

## 💻 Local Setup

Clone the repo:

git clone [https://github.com/your-username/django_project.git](https://github.com/your-username/django_project.git)
cd django_project

Create virtual environment:

python -m venv venv
source venv/bin/activate   (Mac/Linux)
venv\Scripts\activate      (Windows)

Install dependencies:

pip install -r requirements.txt

Run migrations:

python manage.py migrate

Start server:

python manage.py runserver

---

## 🚀 Deployment (Render + Supabase)

1. Create a Supabase project and copy the database URL
2. Push your code to GitHub
3. Create a new Web Service on Render
4. Add environment variables
5. Use the following commands:

**Build Command**

pip install -r requirements.txt && python manage.py collectstatic --noinput

**Start Command**

python manage.py migrate && gunicorn django_project.wsgi:application

---

## 🔮 Future Improvements

* Django REST Framework API layer
* Comment system
* Like / Bookmark functionality
* Rich text editor
* CI/CD pipeline integration

---

## 📌 Key Learnings

* Migrated deployment from Heroku to Render + Supabase
* Managed environment variables securely in production
* Fixed production issues (CSRF, ALLOWED_HOSTS, static files)
* Debugged database connectivity issues (network + config)
* Built a production-ready Django deployment workflow

---

## 🤝 Contributing

Feel free to fork this repo and improve it.

---

## 📄 License

This project is open-source.
---

If you want to make this **10/10 recruiter-level**, next step is:

* add **2–3 screenshots of UI**
* add a **GIF demo (login → post → profile)**

Say the word — I’ll generate that for you too 🚀
