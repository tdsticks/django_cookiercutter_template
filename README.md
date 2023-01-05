# dsc_django_template
Detroit Software Co. Django template for new Python projects

# Summary
This project is a general Django template to help get us up and running quickly per POC and project. 
We also include the fundamental Python requirements for setting up your virtual environment, etc. per MacOS and Windows.

# Requirements

- Python 3.10.0
- Pip 22.2
- pyenv 2.2.5
- Python Main libraries
  - Cookiecutter
  - Django
  - django-extensions (Handy Tools)
  - django-import-export (Import / Export CSV)
  - django-reversion (Revisioning)
  - django-filter
  - djangorestframework (REST API)
  - Markdown
  - mysqlclient (MySQL)
  - python-dotenv (.env reader)
  - Werkzeug (Debugger and WSGI)
  


## MacOS
1. Install **Brew** - https://brew.sh/
    > /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
2. Install **Python** (with Pip) - https://docs.brew.sh/Homebrew-and-Python
    > python3 -m pip install --upgrade pip
3. Install **pyenv** (Python Virtual Environment) - https://github.com/pyenv/pyenv#homebrew-in-macos or https://formulae.brew.sh/formula/pyenv
    >   brew install pyenv
4. Additional brew packages (optional)
   - graphviz - https://formulae.brew.sh/formula/graphviz
      > brew install graphviz
5. Create you virtual environment
    > 
    > pyenv virtual environment {Python version} {FakeProject}
    >
    - Example:
    > 
    > pyenv virtual environment 3.10.0 FakeProject


> **TIP:**
> 
> *** Add an alias for your Mac virtual environment and project folder, as so: ***
> 
> > alias abc="pyenv deactivate; source /Users/{username}/.pyenv/versions/3.10.0/envs/FakeProject/bin/activate; cd ~/Projects/FakeProject/dev/"

6. Once the above is installed and setup, run:
    > pip install --upgrade pip

7. Clone the repository where you want the Django project to go:
    > git clone https://github.com/Detroitsoftware/dsc_django_template.git

8. Rename the cloned repo to the project name
    > mv dsc_django_template {FakeProject}

9. Change directory into the new Djanog project directory
    > cd {Fake Project}

10. Install this requirements file first, then optionally you can install the Cookiecutter setup for further libraries / configuration.
    > pip install -r requirements.txt
   

## Windows

https://www.tutorialspoint.com/how-to-install-python-in-windows

1. Install **Python** - https://www.python.org/downloads/windows/
2. Install **pyenv** https://github.com/pyenv/pyenv#windows
3. Create you Python virtual environment 

> **TIP**
> Add an alias for your Mac virtual environment to your environment path, as so:

3. Clone the repository where you want the Django project to go:
    > git clone https://github.com/Detroitsoftware/dsc_django_template.git

4. Rename the cloned repo to the project name
    > rename dsc_django_template {FakeProject}

5. Change directory into the new Djanog project directory
    > cd {Fake Project}

6. Once the above is installed and setup, run:
    > pip install --upgrade pip

7. Install this requirements file first, then optionally you can install the Cookiecutter setup for further libraries / configuration.
    > pip install -r requirements.txt
   
# Project Setup

1. I personally like to setup my projects with standard folders (short and sweet). This folder structure allows for various types of projects that include: assets, databases, development and documentation

   1. MacOS
    > mkdir ~/Projects/{FakeProject}

    > mkdir assets; mkdir data; mkdir dev; mkdir doc;
    2. Windows
    > md C:\Projects\{FakeProject}

    > mkdir assets; mkdir data; mkdir dev; mkdir doc;


# Django Setup

> TIP
> 
> If you optionally want to use Cookiecutter Django, skip down to that section

1. Setup Django - https://realpython.com/django-setup/#set-up-a-django-project
   1. Create folder for Django Project
      - MacOS
      > ~/Projects/{FakeProject}/dev/{DjangoProjectName}/
      - Windows
      > C:\Projects\{FakeProject}\dev\{DjangoProjectName}\
2. Setup the Django project - https://docs.djangoproject.com/en/4.0/intro/tutorial01/
    > run: django-admin startproject {projectname}
3. Add an app (one or more)
    > run: python manage.py startapp {appname}
4. Create the .env file
   1. Copy the .env.example file to the root of your Django project (not the git repo)
   2. Rename to .env
   3. Again, be sure the .env file is in the root or the Django project folder (you should also have the manage.py file there)
   4. Edit and update the environment variables


# Cookiecutter Django

Cookiecutter Django is a framework for jumpstarting production-ready Django projects quickly.

- Documentation: https://cookiecutter-django.readthedocs.io/en/latest/
- Github:
  - For Postgres:
    - https://github.com/cookiecutter/cookiecutter-django
  - For MySQL:
    - https://github.com/mabdullahadeel/cookiecutter-django-mysql

## Usage

Let's pretend you want to create a Django project called "redditclone". Rather than using startproject and then editing the results to include your name, email, and various configuration issues that always get forgotten until the worst possible moment, get cookiecutter to do all the work.

First, get Cookiecutter. Trust me, it's awesome:

> $ pip install cookiecutter

Now run it against this repo:

For Postgres:
> $ cookiecutter https://github.com/cookiecutter/cookiecutter-django

For MySQL:
> $ cookiecutter https://github.com/mabdullahadeel/cookiecutter-django-mysql



Walk through the prompts as required:

### Project Generation Options

- https://cookiecutter-django.readthedocs.io/en/latest/project-generation-options.html
- https://cookiecutter-django.readthedocs.io/en/latest/settings.html

This page describes all the template options that will be prompted by the cookiecutter CLI prior to generating your project.

**project_name**:
- Your project’s human-readable name, capitals and spaces allowed.

**project_slug**:
   - Your project’s slug without dashes or spaces. Used to name your repo and in other places where a Python-importable version of your project name is needed.

**description:**
 - Describes your project and gets used in places like README.rst and such.

**author_name:**
 - This is you! The value goes into places like LICENSE and such.

**email:**
- The email address you want to identify yourself in the project.

**domain_name:**
 - The domain name you plan to use for your project once it goes live. Note that it can be safely changed later on whenever you need to.

**version:**
- The version of the project at its inception.

**open_source_license:**
A software license for the project. The choices are:
1. MIT
2. BSD
3. GPLv3
4. Apache Software License 2.0
5. Not open source

**timezone:**
 - The value to be used for the TIME_ZONE setting of the project.

**windows:**
 - Indicates whether the project should be configured for development on Windows.

**use_pycharm:**
 - Indicates whether the project should be configured for development with PyCharm.

**use_docker:**
 - Indicates whether the project should be configured to use Docker and Docker Compose.

**postgresql_version:**
 - Select a PostgreSQL version to use. The choices are:
1. 14 
2. 13 
3. 12 
4. 11 
5. 10

**cloud_provider:**
 - Select a cloud provider for static & media files. The choices are:
1. AWS 
2. GCP 
3. None

> Note that if you choose no cloud provider, media files won’t work.

**mail_service:**
 - Select an email service that Django-Anymail provides
1. Mailgun 
2. Amazon SES 
3. Mailjet 
4. Mandrill 
5. Postmark 
6. SendGrid 
7. SendinBlue 
8. SparkPost 
9. Other SMTP

**use_async:**
 - Indicates whether the project should use web sockets with Uvicorn + Gunicorn.

**use_drf:**
 - Indicates whether the project should be configured to use Django Rest Framework.

**frontend_pipeline:**
 - Select a pipeline to compile and optimise frontend assets (JS, CSS, …):
1. None 
2. Django Compressor 
3. Gulp: support Bootstrap recompilation with real-time variables alteration.

**use_celery:**
 - Indicates whether the project should be configured to use Celery.

**use_mailhog:**
 - Indicates whether the project should be configured to use MailHog.

**use_sentry:**
 - Indicates whether the project should be configured to use Sentry.

**use_whitenoise:**
 - Indicates whether the project should be configured to use WhiteNoise.

**use_heroku:**
 - Indicates whether the project should be configured so as to be deployable to Heroku.

**ci_tool:**
 - Select a CI tool for running tests. The choices are:
1. None 
2. Travis CI 
3. Gitlab CI 
4. Github Actions

**keep_local_envs_in_vcs:**
 - Indicates whether the project’s .envs/.local/ should be kept in VCS (comes in handy when working in teams where local environment reproducibility is strongly encouraged). Note: .env(s) are only utilized when Docker Compose and/or Heroku support is enabled.

**debug:**
 - Indicates whether the project should be configured for debugging. This option is relevant for Cookiecutter Django developers only.

### The Awesome Project (branch) actual settings:

1. **project_name:** Awesome Project 
2. **project_slug:** {default value}
3. **description:** {default value}
4. **author_name:** Steve
5. **email:** steve@awesomeproject.com
6. **domain_name:** awesomeproject.com
7. **version:** 0.1.0
8. **open_source_license:** Not open source
9. **timezone:** America/New_York
10. **windows:** NO (I'm on a Mac, but please use if on Windows)
11. **use_pycharm:** YES
12. **use_docker:** NO
13. **postgres or mysql:** 2 - mysql
    1. 8 - mysql 5.7
14. **cloud_provider:** 1 - AWS
15. **mail_service:** 9 - Other SMTP (Gmail)
16. **use_async:** YES
17. **use_drf:** YES
18. **frontend_pipeline:** 1 - None
19. **use_celery:** NO
20. **use_mailhog:** NO
21. **use_sentry:** YES
22. **use_whitenoise:** NO
23. **use_heroku:** NO
24. **ci_tool:** 4 - Github
25. **keep_local_envs_in_vcs:** NO
26. **debug:** NO

## Cookiecutter Next Steps
Once you have your initial installation, you'll need to install the appropriate python libraries found under the "requirements" folder.


> cd requirements/
> 
> pip install -r base.txt

> ** FOR LOCAL **
> 
> pip install -r local.txt

> ** FOR PRODUCTION ** 
> 
> pip install -r production.txt

> ***
> 
> **To remove and reset all pip packages and libraries!**
>
>> pip freeze | xargs pip uninstall -y


# Environment Variables and Database Setup

Regardless of the above path you take, the standard Django install or 
the Cookiecutter setup, you'll need to be sure to populate and read 
in your environment variables into your Django project.

### Cookiecutter:

THIS IS IMPORTANT!!!

- Add the DJANGO_SETTINGS_MODULE env var to the top of the manage.py file, before the **if __name__ == "__main__":**

```
import environ
env = environ.Env(
    # set casting, default value
    DEBUG=(bool, True)
)
# reading .env file
environ.Env.read_env()

DJANGO_SETTINGS_MODULE = env("DJANGO_SETTINGS_MODULE")
# print(" DJANGO_SETTINGS_MODULE:", DJANGO_SETTINGS_MODULE)
```



- Change the default setting to "True" in the config/settings/base.py file:

```
READ_DOT_ENV_FILE = env.bool("DJANGO_READ_DOT_ENV_FILE", default=False)

*** Change be this ***
READ_DOT_ENV_FILE = env.bool("DJANGO_READ_DOT_ENV_FILE", default=True)
```

- Change the DJANGO_DEBUG setting to DEBUG in the config/settings/base.py file:
```
DEBUG = env.bool("DJANGO_DEBUG", False)

*** Change be this ***
DEBUG = env.bool("DEBUG", default=False)
```

- Add the Copilot environment and application vars in the config/settings/base.py file, if you are using AWS Copilot

```
COPILOT_ENVIRONMENT_NAME = env.str("COPILOT_ENVIRONMENT_NAME")
COPILOT_APPLICATION_NAME = env("COPILOT_APPLICATION_NAME")
# print(" COPILOT_ENVIRONMENT_NAME", COPILOT_ENVIRONMENT_NAME)
# print(" COPILOT_APPLICATION_NAME", COPILOT_APPLICATION_NAME)
```

- Then add the following to the database settings further down in the config/settings/base.py file:

```
# DATABASES
# ------------------------------------------------------------------------------
# https://docs.djangoproject.com/en/dev/ref/settings/#databases
DATABASES = {
    # "default": env.db("DATABASE_URL", default="mysql://root:debug@/awesomeproject"),
    "default": {
        'ENGINE': env.str("MYSQL_ENGINE"),
        'NAME': env.str("MYSQL_DATABASE"),
        'USER': env.str("MYSQL_USER"),
        'PASSWORD': env.str("MYSQL_PASSWORD"),
        'HOST': env.str("MYSQL_HOST"),
        'PORT': env.int("MYSQL_PORT"),
        'OPTIONS': {
            # 'read_default_file': '/usr/local/etc/my.cnf',
            # If this path changes, update the Dockerfile
            # 'read_default_file': 'awesomeproject/my.cnf',
            'sql_mode': 'STRICT_TRANS_TABLES',
            'init_command': 'SET foreign_key_checks = 0;',
        }
    }
}
DATABASES["default"]["ATOMIC_REQUESTS"] = True
# https://docs.djangoproject.com/en/stable/ref/settings/#std:setting-DEFAULT_AUTO_FIELD
DEFAULT_AUTO_FIELD = "django.db.models.BigAutoField"
# print("DATABASES:", DATABASES)
```

- Setup Email if you want to have email work locally and in the cloud. You'll need to setup
a Gmail account with an app password created.

```
# EMAIL
# ------------------------------------------------------------------------------
# https://docs.djangoproject.com/en/dev/ref/settings/#email-backend
EMAIL_BACKEND = env(
    "EMAIL_BACKEND",
    default="django.core.mail.backends.smtp.EmailBackend",
)
# https://docs.djangoproject.com/en/dev/ref/settings/#email-timeout
EMAIL_TIMEOUT =  env(
    "EMAIL_TIMEOUT",
    default=5,
)
# NEED TO INCLUDE THESE FOR DJANGO AUTH EMAIL TO WORK
EMAIL_HOST = env("EMAIL_HOST")
EMAIL_PORT = env("EMAIL_PORT")
EMAIL_USE_TLS = env("EMAIL_USE_TLS")
EMAIL_HOST_USER = env("EMAIL_HOST_USER")
EMAIL_HOST_PASSWORD = env("EMAIL_HOST_PASSWORD")
SERVER_EMAIL = env("SERVER_EMAIL")
DEFAULT_FROM_EMAIL = env("DEFAULT_FROM_EMAIL")
# print("EMAIL_BACKEND:", EMAIL_BACKEND)
# print("EMAIL_TIMEOUT:", EMAIL_TIMEOUT)
# print("EMAIL_HOST:", EMAIL_HOST)
# print("EMAIL_PORT:", EMAIL_PORT)
# print("EMAIL_USE_TLS:", EMAIL_USE_TLS)
# print("EMAIL_HOST_USER:", EMAIL_HOST_USER)
# print("EMAIL_HOST_PASSWORD:", EMAIL_HOST_PASSWORD)
# print("SERVER_EMAIL:", SERVER_EMAIL)
# print("DEFAULT_FROM_EMAIL:", DEFAULT_FROM_EMAIL)
```


### Django Standard Install:

Add the following code to your settings file:

```
import os
import dotenv

# Instantiate the env vars
de = dotenv
de.load_dotenv()
```

```
# Database
# https://docs.djangoproject.com/en/3.2/ref/settings/#databases
# https://docs.djangoproject.com/en/4.0/ref/databases/#mysql-notes
DATABASES = {
    'default': {
        'DATABASE_URL': 'mysql://{}:{}@{}:{}/{}'.
        format(env("MYSQL_USER"), env("MYSQL_PASSWORD"), env("MYSQL_HOST"), env("MYSQL_PORT"), env("MYSQL_DATABASE")),
        'ENGINE': env.str("MYSQL_ENGINE"),
        'NAME': env.str("MYSQL_DATABASE"),
        'USER': env.str("MYSQL_USER"),
        'PASSWORD': env.str("MYSQL_PASSWORD"),
        'HOST': env.str("MYSQL_HOST"),
        'PORT': env.str("MYSQL_PORT"),
        'CONN_MAX_AGE': 500,
        'OPTIONS': {
            # 'read_default_file': '/usr/local/etc/my.cnf',
            # If this path changes, update the Dockerfile
            # 'read_default_file': 'awesomeproject/my.cnf',
            'sql_mode': 'STRICT_TRANS_TABLES',
            "init_command": "SET foreign_key_checks = 0;",
        }
    }
}
DATABASES["default"]["ATOMIC_REQUESTS"] = True
# print("DATABASES:", DATABASES)
```
