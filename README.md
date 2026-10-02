# Koi Mil Gaya

Koi Mil Gaya is a project repository for building a modern web application with a clean, scalable structure. This README serves as the project landing page while the application is being set up and developed.

## Project Overview

This project is currently in its early development stage. The repository has been initialized and is ready for the application source code, configuration, and documentation to be added.

## Current Status

- Repository initialized
- Project structure being defined
- Core application implementation pending
- README prepared for onboarding and setup

## Features

The following features are planned for the project and can be refined as development progresses:

- User-friendly interface
- Responsive design
- Modern front-end experience
- Easy project onboarding
- Scalable application structure

## Tech Stack

This project is built with the following stack:

- Frontend: HTML, CSS, JavaScript
- Backend: PHP
- Database: MySQL (via XAMPP)
- Local Server Environment: XAMPP (Apache + PHP + MySQL)
- Code Editor: Visual Studio Code
- Version Control: Git and GitHub

## Project Structure

```text
koi_mil_gaya/
├── README.md
├── .gitignore
├── package.json
├── src/
├── public/
├── backend/
├── docs/
└── tests/
```

> The exact structure may change as the project evolves.

## Git and GitHub Setup Guide

This section explains the exact steps for setting up Git on a local machine, creating a GitHub repository, adding collaborators, forking and cloning the repo, generating SSH keys, adding them to GitHub, and setting up the remote origin correctly.

### 1) Install Git on Local Machine

Check if Git is already installed:

```bash
git --version
```

If Git is not installed, install it from:

- https://git-scm.com/downloads
- For Windows, install Git Bash or Git for Windows

After install, configure your identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Optional but recommended:

```bash
git config --global init.defaultBranch main
git config --global credential.helper manager
```

---

### 2) Create a Repository on GitHub

1. Open GitHub.
2. Click the + sign in the top-right corner.
3. Select New repository.
4. Give the repo a name, for example:
   - `koi_mil_gaya`
5. Choose:
   - Public or Private
   - Add a README if needed
6. Click Create repository.

---

### 3) Give Access to Others Using Their GitHub IDs

1. Open the repository on GitHub.
2. Go to Settings.
3. Click Collaborators and teams.
4. Click Add people.
5. Enter each teammate's GitHub username.
6. Select permission level (Write/Read/Admin).
7. Click Add.

This allows everyone to access the repo with their own GitHub accounts.

---

### 4) Fork the Repository

If the repository is owned by someone else and you want to work on your own copy:

1. Open the original repo on GitHub.
2. Click Fork.
3. Choose your own GitHub account.
4. GitHub creates a fork under your account.

Then clone your fork locally:

```bash
git clone https://github.com/<your-github-username>/<repo-name>.git
cd <repo-name>
```

If the repo is already yours and you are working directly in it, you can skip the fork step.

---

### 5) Generate SSH Keys Locally

SSH keys are the cleanest way to authenticate with GitHub without typing a password every time.

Generate a key:

```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

Then press Enter for the default file location, or choose a custom path.

You will be asked for a passphrase. You may leave it empty or add one.

Check the generated public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

On Windows PowerShell:

```powershell
Get-Content ~/.ssh/id_ed25519.pub
```

Copy the entire output. It starts with:

```text
ssh-ed25519 AAAA...
```

---

### 6) Add the SSH Key to GitHub

1. Open GitHub.
2. Go to Settings.
3. Click SSH and GPG keys.
4. Click New SSH key.
5. Paste the public key.
6. Give it a label like `Laptop` or `Work PC`.
7. Click Add SSH key.

---

### 7) Test the SSH Connection

```bash
ssh -T git@github.com
```

If successful, GitHub will show a message like:

```text
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

This confirms the SSH handshake is working.

---

### 8) Set Up the Remote Origin

After cloning, check your remotes:

```bash
git remote -v
```

If using SSH, set the origin to the SSH URL:

```bash
git remote set-url origin git@github.com:<your-github-username>/<repo-name>.git
```

If using HTTPS, set it like this:

```bash
git remote set-url origin https://github.com/<your-github-username>/<repo-name>.git
```

Verify again:

```bash
git remote -v
```

You should see your fork or repository as `origin`.

---

### 9) Add Upstream for Syncing with the Main Project

If you forked the repo and want to keep it synced with the original project, add `upstream`:

```bash
git remote add upstream https://github.com/<owner-username>/<repo-name>.git
```

Or with SSH:

```bash
git remote add upstream git@github.com:<owner-username>/<repo-name>.git
```

Then fetch changes:

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

---

### 10) Push the Initial Project to GitHub

From the project folder:

```bash
git status
git branch -M main
git add .
git commit -m "Initial project setup"
git push -u origin main
```

If you are working from a freshly created GitHub repo, this will upload your project to GitHub.

---

### 11) Typical Developer Workflow

```bash
git checkout -b feature/my-task
git status
git add .
git commit -m "Add feature"
git push origin feature/my-task
```

Then open a Pull Request on GitHub.

---

### 12) Quick Summary of the Full Process

1. Install Git on your local machine.
2. Set your Git username and email.
3. Create a GitHub repository.
4. Add teammates using their GitHub IDs.
5. Fork the project if needed.
6. Clone the repository locally.
7. Generate SSH keys locally.
8. Add the public key to GitHub.
9. Test GitHub SSH authentication.
10. Set `origin` correctly.
11. Push the project and start collaborating.

---

## Getting Started

### Prerequisites

Make sure the following tools are installed:

- Git
- PHP 8.x
- MySQL
- Apache or another PHP-compatible local web server
- A browser such as Chrome or Edge

### Local Setup

```bash
git clone https://github.com/<your-github-username>/koi_mil_gaya.git
cd koi_mil_gaya
```

### Configure the Database

Create a MySQL database and update your PHP configuration file with the correct database credentials:

```php
$db_host = "localhost";
$db_name = "koi_mil_gaya";
$db_user = "root";
$db_pass = "";
```

Then import the SQL file if one is provided:

```bash
mysql -u root -p koi_mil_gaya < database.sql
```

### Run the Project

For a local PHP setup, start the project from the project root using a local web server:

```bash
php -S localhost:8000
```

Then open the browser and visit:

```text
http://localhost:8000
```

If the project uses a different server setup, update these commands to match your local environment.

## Development Workflow

1. Create a feature branch for your work.
2. Keep commits focused and descriptive.
3. Test your changes before opening a pull request.
4. Document any environment or setup requirements.

## Contributing

Contributions are welcome as the project grows. To contribute:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes with a clear message.
4. Open a pull request with a summary of the update.

## License

This project does not yet declare a license. Add a license file and specify the license here when the repository is ready for public or team use.

## Contact

For questions or project collaboration, please use the repository owner or project maintainer contact information available on the GitHub project page.

---

This README can be expanded with screenshots, architecture details, API documentation, and setup notes as development progresses.
