Django Blog Application

A full-stack Django web application featuring user authentication, profile management with image uploads, and cloud-hosted static/media assets. The application is deployed on Heroku   and uses AWS S3 for scalable media storage.
  
🔗 Live Demo:
https://mydjangoapplication-e19111bdacb0.herokuapp.com/

Key Features
* User registration, login, logout, and password reset via email
* User profile management with profile picture uploads
* Media files hosted on AWS S3 for scalability
* Environment-based configuration using .env
* Production deployment on Heroku
* Secure handling of secrets and credentials
* Django Crispy Forms for clean, responsive UI
* Static asset handling with Whitenoise (production-ready)

Tech Stack

Backend
  * Python 3.12
  * Django 6.0
  * Django Authentication Framework

Storage & Infrastructure
  * AWS S3 (media file storage)
  * django-storages + boto3
  * Heroku (deployment)

Database
  * SQLite (local development)
  * PostgreSQL (production-ready configuration)

Frontend
  * Django Templates
  * Bootstrap (via crispy-bootstrap4)

Architecture Highlights
* Media uploads are stored in AWS S3 instead of the local filesystem, allowing the application to scale horizontally.
* Environment variables are managed using python-dotenv locally and Heroku config vars in production.
* Separate storage backends for static files and media files using Django’s STORAGES setting.
* Secure email delivery via SMTP (Gmail) for password reset flows.
* Explicit Python version locking using .python-version to ensure environment consistency.

Environment Variables

  The following environment variables are required:
  
    SECRET_KEY=your_django_secret_key
    DEBUG=False
    EMAIL_USER=your_email@gmail.com
    EMAIL_PASS=your_email_app_password
    AWS_ACCESS_KEY_ID=your_aws_access_key
    AWS_SECRET_ACCESS_KEY=your_aws_secret_key
    AWS_STORAGE_BUCKET_NAME=your_s3_bucket_name


Local Setup

    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    python -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    python manage.py migrate
    python manage.py runserver


Deployment
* Deployed using Heroku (Heroku-24 stack)
* Python version specified via .python-version
* Static files collected using collectstatic
* Media served directly from AWS S3

Future Improvements
* Add social authentication (Google/GitHub OAuth)
* Replace SQLite with managed Postgres in production
* Add pagination and search to blog posts
* Improve test coverage with Django TestCase and pytest
* Introduce CI/CD pipeline (GitHub Actions)

