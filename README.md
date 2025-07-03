# Git & GitHub Training Guide

## 📌 Table of Contents

1. [Introduction to Git](#introduction-to-git)
2. [Types of Version Control](#types-of-version-control)
3. [Benefits of Using Git & GitHub](#benefits-of-using-git--github)
4. [Git Workflow Overview](#git-workflow-overview)
5. [Installing Git on Windows](#installing-git-on-windows)
6. [Setting up SSH Key for GitHub](#setting-up-ssh-key-for-github)
7. [Basic Git Commands](#basic-git-commands)
8. [Best Practices](#best-practices)

---

## 📘 Introduction to Git

- **Git** is a distributed version control system that helps developers track and manage code changes.
- It was created by **Linus Torvalds** in 2005.
- Git is used locally, and **GitHub** is a cloud-based platform to host Git repositories online.

---

## 📂 Types of Version Control

### 1. **Local Version Control**

- Changes are stored on a local system.
- Limited collaboration and backup.

### 2. **Centralized Version Control (CVCS)**

- Single central server (e.g., SVN).
- Risk of data loss if the central server fails.

### 3. **Distributed Version Control (DVCS)**

- Each user has a full copy of the repository.
- Git is a DVCS. Changes can be pushed/pulled from/to remote repositories.

---

## ✅ Benefits of Using Git & GitHub

- Track changes in source code
- Collaborate with team members
- Revert to previous versions
- Branching and merging
- Open-source collaboration
- Pull Requests for code reviews
- Secure with SSH authentication

---

## 🔄 Git Workflow Overview

- Working Directory → Staging Area → Local Repository → Remote Repository (GitHub)

### Basic Steps:

1. `git init` – Initialize a new repository
2. `git add` – Stage changes
3. `git commit` – Commit staged changes
4. `git push` – Push changes to GitHub
5. `git pull` – Fetch and merge changes from GitHub

---

## 💻 Installing Git on Windows

1. Visit: [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Download and run the installer.
3. Use default settings (recommended):
   - **Git Bash** as terminal emulator
   - **Default editor** as VS Code or Notepad++
   - **Use Git from the command line**
4. Verify installation:
   ```bash
   git --version
   ```

## 🔐 Setting Up SSH Key for GitHub (Using RSA 4096-bit)

Follow these steps to generate and configure an SSH key to connect GitHub securely from your system.

1. Check if SSH keys already exist

```bash
ls -al ~/.ssh
```

If you see files like id_rsa and id_rsa.pub, you already have a key. You can use the existing key or generate a new one.

2. Generate a New SSH Key

```bash
ssh-keygen -t rsa -b 4096 -C "yourmail@gmail.com"
```

- Replace "yourmail@gmail.com" with your actual GitHub email.

- When prompted:

  - Press Enter to save in the default location (~/.ssh/id_rsa)

  - Enter a passphrase (optional but recommended)

3. Start the SSH Agent

```bash
eval "$(ssh-agent -s)"
```

4. Add Your SSH Private Key to the Agent

```bash
ssh-add ~/.ssh/id_rsa
```

5. Copy the Public Key to Clipboard

```bash
clip < ~/.ssh/id_rsa.pub
```

If clip doesn’t work, manually open the key using the next command and copy it:

```bash
cat ~/.ssh/id_rsa.pub
```

6. Add the SSH Key to GitHub

- Go to GitHub → Settings

- Navigate to SSH and GPG keys

- Click New SSH key

- Paste the copied key and give it a recognizable title (e.g., "Work Laptop")

7. Test the Connection

```bash
ssh -T git@github.com
```

On success, you will see a message like:

Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.

## ✅ Your SSH connection is now configured!

## 🛠️ Basic Git Commands

| Command | Description |
|---------------|------------------|
| `git init` | Initialize a new repository |
| `git clone <url>` | Clone a remote repo to local |
| `git status` | Check current repo status |
| `git add <file>` | Stage a specific file |
| `git add .` | Stage all changed files |
| `git commit -m "message"` | Commit changes with a message |
| `git log` | Show commit history |
| `git diff` | Show changes between commits or working tree |
| `git branch` | List all branches |
| `git checkout -b <branch>` | Create and switch to a new branch |
| `git merge <branch>` | Merge a branch into current branch |
| `git remote -v` | Show remote repository URLs |
| `git push origin <branch>` | Push commits to GitHub |
| `git pull origin <branch>` | Fetch and merge changes from GitHub |


## 🌟 Best Practices

- Always write meaningful commit messages.

- Use branches for features/fixes.

- Pull latest changes before starting work.

- Regularly push your work.

- Resolve merge conflicts carefully.

- Use .gitignore to exclude files like .env, node_modules, etc.
