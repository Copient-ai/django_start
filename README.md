
# Django Starter Project Setup Guide

This guide will help you create a new project repository based on the starter Django project template. The template has been slightly modified from [William Vincent’s DjangoX project](https://github.com/wsvincent/djangox) to match recent best practices and includes **UV** integration while removing Docker support.

## Steps to Set Up Your New Project

### 1. Create an Empty Repository

1. Go to your Git hosting service (e.g., GitHub, GitLab, Bitbucket).
2. Create a new repository. **Do not** initialize it with a README, `.gitignore`, or license file—this will be handled locally.

### 2. Clone the Starter Project

On your local machine:

1. Clone the starter project **without including its Git history**:

   ```bash
   git clone --depth 1 https://github.com/yourusername/your-starter-django-project.git my-new-project
   ```

   This command clones the starter project but only the most recent commit, effectively ignoring its Git history.

2. Navigate into your new project directory:

   ```bash
   cd my-new-project
   ```

3. Remove the existing Git configuration to unlink it from the original repository:

   ```bash
   rm -rf .git
   ```

### 3. Initialize a New Git Repository

1. Initialize a new Git repository:

   ```bash
   git init
   ```

2. Add all files and make your initial commit:

   ```bash
   git add .
   git commit -m "Initial commit based on Django starter project"
   ```

3. Link your new repository to the remote location created in Step 1:

   ```bash
   git remote add origin https://github.com/yourusername/my-new-project.git
   ```

4. Push your initial commit to the remote repository:

   ```bash
   git push -u origin main
   ```

### 4. Sync Requirements

Sync your requirements using UV:

   ```bash
   uv sync
   ```

### 6. Activate VM

Activate the VM (the following assumes OhMyZsh):

   ```bash
   vrun .venv
   ```

### 6. Initial Migration (assumed sqlite)

If you want to go ahead and set up PostgreSQL now is the time. If not, migrate as follows:

   ```bash
   uv run manage.py migrate
   ```

### 7. Confirm Setup

Make sure everything is set up. Run the server and you should see the django start page:

   ```bash
   uv run manage.py runserver
   ```


You’re all set!
