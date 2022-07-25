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
  - Django
  - django-extensions (Handy Tools)
  - django-reversion (Revisioning)
  - django-filter
  - djangorestframework
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
      
> **TIP**
> 
> Add an alias for your Mac virtual environment and project folder, as so:
> 
> > alias abc="pyenv deactivate; source /Users/{username}/.pyenv/versions/3.10.0/envs/FakeProject/bin/activate; cd ~/Projects/FakeProject/dev/"

5. Once the above is installed and setup, run:
    > pip install --upgrade pip

    > pip install -r requirements.txt




## Windows

https://www.tutorialspoint.com/how-to-install-python-in-windows

1. Install **Python** - https://www.python.org/downloads/windows/
2. Install **pyenv** https://github.com/pyenv/pyenv#windows

> **TIP**
> Add an alias for your Mac virtual environment to your environment path, as so:

3. Once the above is installed and setup, run:
    > pip install --upgrade pip

    > pip install -r requirements.txt

# Project Setup

1. I personally like to setup my projects with standard folders (short and sweet).
   1. MacOS
    > mkdir ~/Projects/{FakeProject}

    > mkdir assets; mkdir data; mkdir dev; mkdir doc;
    2. Windows
    > md C:\Projects\{FakeProject}

    > mkdir assets; mkdir data; mkdir dev; mkdir doc;
2. This folder structure allows for various types of projects that include: 
assets, databases, development and documentation


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
2. run: django-admin startproject {projectname} 
3. https://docs.djangoproject.com/en/4.0/intro/tutorial01/
4. Add an app
5. run: python manage.py startapp {appname}


# Cookiecutter Django

Cookiecutter Django is a framework for jumpstarting production-ready Django projects quickly.

- Documentation: https://cookiecutter-django.readthedocs.io/en/latest/
- Github:
- For Postgres
  - https://github.com/cookiecutter/cookiecutter-django
- For MySQL
  - https://github.com/mabdullahadeel/cookiecutter-django-mysql

## Usage

Let's pretend you want to create a Django project called "redditclone". Rather than using startproject and then editing the results to include your name, email, and various configuration issues that always get forgotten until the worst possible moment, get cookiecutter to do all the work.

First, get Cookiecutter. Trust me, it's awesome:

> $ pip install cookiecutter

Now run it against this repo:

> $ cookiecutter https://github.com/cookiecutter/cookiecutter-django
> 
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

## Cookiecutter Next Steps
Once you have your initial installation, you'll need to install the appropriate python libraries found under the "requirements" folder.

> cd requirements/
> 
> pip install -f base.txt

> ** FOR LOCAL **
> 
> pip install -f local.txt

> ** FOR PRODUCTION ** 
> 
> pip install -f production.txt

