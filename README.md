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
├── index.php
├── config/
│   └── db.php
├── assets/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
├── database/
│   └── schema.sql
```

> This project is currently structured as a simple PHP application ready for local XAMPP development.

## Local Setup with XAMPP

### 1. Install and Start XAMPP

1. Download and install XAMPP for Windows from [apachefriends.org](https://www.apachefriends.org/).
2. Open the XAMPP Control Panel.
3. Start **Apache** and **MySQL**. If either service fails to start, resolve the port conflict shown in the Control Panel before continuing.

### 2. Put the Complete Project in `htdocs`

The whole `koi_mil_gaya` project folder must be directly inside XAMPP's `htdocs` folder. With the default XAMPP installation, the project root is:

```text
C:\xampp\htdocs\koi_mil_gaya
```

To clone it there, open Command Prompt and run:

```bat
cd /d C:\xampp\htdocs
git clone https://github.com/Athena206/koi_mil_gaya.git
```

If you downloaded the project as a ZIP or already cloned it somewhere else, copy the complete `koi_mil_gaya` folder into `C:\xampp\htdocs`. The resulting layout should look like this:

```text
C:\xampp\htdocs\
└── koi_mil_gaya\
    ├── index.php
    ├── README.md
    ├── config\
    │   └── db.php
    ├── database\
    │   └── schema.sql
    └── assets\
        ├── css\
        │   └── style.css
        └── js\
            └── script.js
```

Make sure `index.php` is at `C:\xampp\htdocs\koi_mil_gaya\index.php`. Do not put the project files directly in `htdocs`, and do not leave them nested an extra level deep (for example, `htdocs\koi_mil_gaya\koi_mil_gaya\index.php`).

### 3. Create the MySQL Database and Tables

The project includes `database/schema.sql`, which creates the `koi_mil_gaya` database and a `users` table.

**Using phpMyAdmin:**

1. With Apache and MySQL running, open [http://localhost/phpmyadmin](http://localhost/phpmyadmin).
2. Select the **Import** tab.
3. Choose `database/schema.sql` from the project folder.
4. Click **Import** or **Go** to run the script.
5. Confirm that the `koi_mil_gaya` database and its `users` table appear in the sidebar.

The schema creates the database itself, so you do not need to create it separately first.

**Alternatively, using the MySQL command line** from Command Prompt:

```bat
"C:\xampp\mysql\bin\mysql.exe" -u root < "C:\xampp\htdocs\koi_mil_gaya\database\schema.sql"
```

If you installed XAMPP to a different location, adjust the paths in the command.

### 4. Configure the Database Connection

The connection settings are in `config/db.php`. They default to:

| Setting | Default |
| --- | --- |
| Host | `localhost` |
| Database | `koi_mil_gaya` |
| Username | `root` |
| Password | *(empty)* |

These defaults match a typical local XAMPP MySQL installation. If you configured a MySQL password or use a different database account, update `$dbuser` and `$dbpass` in `config/db.php` to match your local settings.

### 5. Open the Project

Visit [http://localhost/koi_mil_gaya/](http://localhost/koi_mil_gaya/) in your browser. Keep Apache and MySQL running while developing locally.

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
- XAMPP (Apache + MySQL + PHP)
- Visual Studio Code
- Browser (Chrome / Edge)

### Local Setup

1. Install XAMPP and start Apache and MySQL.
2. Clone the repository:

```bash
git clone https://github.com/<your-github-username>/koi_mil_gaya.git
cd koi_mil_gaya
```

3. Copy the project folder into the XAMPP web root, usually:

```text
C:/xampp/htdocs/
```

So the project path becomes:

```text
C:/xampp/htdocs/koi_mil_gaya/
```

### Configure the Database

Create the database in phpMyAdmin or MySQL CLI:

```sql
CREATE DATABASE koi_mil_gaya;
```

Then import the SQL schema:

```bash
mysql -u root koi_mil_gaya < database/schema.sql
```

The database credentials in `config/db.php` are configured as:

```php
$host = 'localhost';
$dbname = 'koi_mil_gaya';
$dbuser = 'root';
$dbpass = '';
```

### Run the Project

Open your browser and visit:

```text
http://localhost/koi_mil_gaya/
```

If you want to run it from the terminal directly:

```bash
php -S localhost:8000
```

Then open:

```text
http://localhost:8000
```

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
