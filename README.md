CREATE

# Create a virtual environment (Windows)
py -m venv myvenv

# Activate virtual environment (Windows)
myvenv\Scripts\activate.bat

--------------------------------------------------------

Install Django & start a new project

# Install Django
pip install django

# Create project
django-admin startproject ชื่อproject

cd project 

# Create the app
python manage.py startapp ชื่อapp

# Start server (ไม่ต้องก็ได้แล้วแต่)
python manage.py runserver

--------------------------------------------------------

ติดตั้ง Postgres Client

> pip install psycopg2

--------------------------------------------------------

แก้ Settings

*คอม มอ จะใช้ 
user = "postgres"
password = "password"

# Database setting
DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "ชื่อdatabase",
        "USER": "postgres",
        "PASSWORD": "password",
        "HOST": "localhost",
        "PORT": "5432",
    }
}

# Add app blogs to INSTALLED_APPS
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    # Add your apps here
    "ชื่อapp",
]

--------------------------------------------------------

Migrate & Makemigrations

python manage.py makemigrations
python manage.py migrate

--------------------------------------------------------

***อยู่ใน path project ที่สร้างก่อนเข้า app

ติดตั้ง django-extensions และ jupyter notebook ด้วยคำสั่ง
pip install django-extensions ipython jupyter notebook

จากนั้นให้แก้ไข version ของ package ภายใน jupyter และ notebook
pip install ipython==8.25.0 jupyter_server==2.14.1 jupyterlab==4.2.2 jupyterlab_server==2.27.2 notebook==6.5.7

จากนั้นสร้าง directory ชื่อ notebooks
mkdir notebooks

--------------------------------------------------------

แก้ settings.py

INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
	# ทุกอย่างค
    "django_extensions",
    "ชื่อapp",
]

--------------------------------------------------------

ทำการ start Jupyter Notebook server ด้วย command
ปล.ต้อง activate myveny ก่อนที่จะรัน

python manage.py shell_plus --notebook
