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

## Usage

Let's pretend you want to create a Django project called "redditclone". Rather than using startproject and then editing the results to include your name, email, and various configuration issues that always get forgotten until the worst possible moment, get cookiecutter to do all the work.

First, get Cookiecutter. Trust me, it's awesome:

> $ pip install cookiecutter

Now run it against this repo:

> $ cookiecutter https://github.com/cookiecutter/cookiecutter-django


