# Django Blog Application

A Django blog app with authentication, user profiles, and production deployment support for **Render + Supabase Postgres**.

## Key Features
- User registration, login, logout, and password reset via email
- User profile management with profile picture uploads
- Environment-based configuration using `.env`
- Static files served in production via WhiteNoise
- PostgreSQL support via `DATABASE_URL`

## Tech Stack
- Python 3.12
- Django 6.0
- Gunicorn + WhiteNoise
- Supabase Postgres (production)
- SQLite (local fallback)

## Environment Variables
Set these in Render (and optionally in local `.env`):

```bash
SECRET_KEY=your_django_secret_key
DEBUG=False
DATABASE_URL=postgresql://postgres:<password>@<host>:6543/postgres?sslmode=require
ALLOWED_HOSTS=your-service.onrender.com,your-custom-domain.com
CSRF_TRUSTED_ORIGINS=https://your-service.onrender.com,https://your-custom-domain.com
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password
```

Notes:
- `DATABASE_URL` should point to your Supabase Postgres connection string.
- If `DATABASE_URL` is not set, the app falls back to local SQLite (`db.sqlite3`) for development.

## Local Setup
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Render Deployment

### Build Command
```bash
pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate
```

### Start Command
```bash
gunicorn django_project.wsgi
```

## Media Uploads (Current Limitation)
- Media is currently configured to local filesystem storage (`/media`) for development simplicity.
- On Render, filesystem storage is ephemeral, so user uploads are **not persistent** across deploys/restarts.
- Next stage: connect Django media storage to Supabase Storage for persistent uploads in production.
