
# Django Starter Project Setup Guide

This guide will help you create a new project repository based on the starter Django project template. The template has been slightly modified from [William Vincent’s DjangoX project](https://github.com/wsvincent/djangox) to match recent best practices and includes **UV** integration while removing Docker support.

## Steps to Set Up Your New Project

### 1. Create an Empty Repository

On GitHub

1. Create a new repository (called 'my_new_project' hereafter). **Do not** initialize it with a README, `.gitignore`, or license file—this will be handled locally.

### 2. Clone the Starter Project

On your local machine:

1. Clone the starter project **without including its Git history**:

   ```bash
   git clone git@github.com:Copient-ai/django_start.git
   ```

### 3. Clone and Update Your New Project

1. Now clone your new project (in the same folder is assumed):

   ```bash
   git clone git@github.com:Copient-ai/my_new_project.git
   ```

2. Copy all the files from django_start project to my_new_project EXCEPT the .git folder:

   ```bash
   rsync -av --exclude='.git' django_start/ my_new_project/
   ```

### 4. Add/commit/push initial files to your new project

1. Initialize a new Git repository:

   ```bash
   cd my_new_project
   git add .
   git commit -m "Initial commit based on django starter project files."
   git push
   ```

### 5. Sync Requirements

Sync your requirements using UV:

   ```bash
   uv sync
   ```

### 6. Activate VM

Activate the VM (the following assumes OhMyZsh):

   ```bash
   vrun .venv
   ```

### 7. Initial Migration (assumed sqlite)

If you want to go ahead and set up PostgreSQL now is the time. If not, migrate as follows:

   ```bash
   uv run manage.py migrate
   ```

### 8. Confirm Setup

Make sure everything is set up. Run the server and you should see the django start page:

   ```bash
   uv run manage.py runserver
   ```


You’re all set!
