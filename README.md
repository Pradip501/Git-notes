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

## 🔐 Setting up SSH Key for GitHub

#### Step 1: Generate SSH Key
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- Press Enter to accept default file location.
- Enter a passphrase (optional).

### Step 2: Start SSH Agent