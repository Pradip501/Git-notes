# cPanel Management & Server Information

## 📌 Overview

This document provides guidance on managing hosting using **cPanel** and contains key server-related information. It is intended for developers, administrators, or anyone working with the hosting environment.

---

## 🔐 Accessing cPanel

1. **Login URL**:

```bash
    https://yourdomain.com/cpanel
```

OR

```bash
    https://yourserverip:2083
```

2. **Credentials**:

- **Username**: `your_cpanel_username`
- **Password**: `**********` (stored securely in a password manager)

3. **cPanel Dashboard Highlights**:

- **File Manager**: Upload/edit website files.
- **MySQL Databases**: Manage databases and users.
- **phpMyAdmin**: GUI to access and manage MySQL.
- **Domains**: Addon, Subdomains, Redirects.
- **Email Accounts**: Create and manage email addresses.
- **Cron Jobs**: Schedule scripts or tasks.
- **SSL/TLS**: Manage and install SSL certificates.

---

## 🌐 Server Information

- **Server IP**: `123.456.789.123`
- **Hosting Provider**: `YourHostingProviderName`
- **Operating System**: CentOS / CloudLinux / AlmaLinux
- **PHP Version**: 8.1 (can be changed via MultiPHP Manager)
- **MySQL Version**: 5.7+
- **Apache Version**: 2.4+
- **Nameservers**:
- `ns1.yourdomain.com`
- `ns2.yourdomain.com`

---

## 📁 Website File Structure

- All website files should reside inside `public_html/`.

---

## 🛠️ Common Tasks

| Task                  | Tool               | Notes                            |
| --------------------- | ------------------ | -------------------------------- |
| Upload website files  | File Manager / FTP | Use `public_html/`               |
| Create database       | MySQL Databases    | Assign user after creation       |
| Backup website        | Backup Wizard      | Download full or partial backups |
| Manage cron jobs      | Cron Jobs          | Add script paths and schedule    |
| Monitor errors & logs | Metrics > Errors   | Useful for debugging             |

---

## 🌐 How can we get or purchase the a server ?

- Choose a Hosting Provider
  - Pick based on your needs (budget, control, location).
    E.g. Hostinger, DigitalOcean, AWS, Azure.
  - Sign Up / Log In
    - Create an account on the provider’s website.
    - Add billing method (credit card, PayPal, etc.).
  - Create a Server (VPS or Cloud Instance)
    - OS: Ubuntu 22.04,
    - Plan: e.g. 1 vCPU, 1GB RAM (start small)
    - Region: Closest to your audience
    - Authentication: SSH key (preferred) or password.
    - E.g. On Demand Instance, Spot Instance, Reserved Instance, Ec2 Saving plan,

## 🌐 How to Add an Addon Domain in cPanel ?

- ✅ Step 1: Log in to cPanel

  - Visit: https://yourdomain.com/cpanel
  - Enter your username and password.

- ✅ Step 2: Go to Addon Domains

  - Find and click on "Addon Domains" under the Domains section.

- ✅ Step 3: Fill in Domain Info

| Field               | Description                                              |
| ------------------- | -------------------------------------------------------- |
| **New Domain Name** | Your new domain (e.g., `example.com`)                    |
| **Subdomain**       | Auto-filled (e.g., `example`) — keep default             |
| **Document Root**   | Folder name (e.g., `public_html/example.com`) — can edit |

- ✅ Step 4: Click Add Domain

  - Now your domain is added to cPanel and ready to host files in the specified directory.

- ✅ Step 5: Point Domain to Server
  Go to your domain registrar (e.g., GoDaddy, Namecheap) and:

  - Update the domain’s A Record to your hosting IP address,
    OR
  - Set Nameservers to your hosting provider’s (e.g., ns1.yourhost.com, ns2.yourhost.com).

- ✅ Step 6: Upload Files
  - Go to File Manager → public_html/example.com/
  - Upload your files.

## 🌐 How to Create a Subdomain in cPanel

---

## ✅ Steps to Create a Subdomain

1. **Log in to cPanel**  
   URL: `https://yourdomain.com/cpanel`

2. **Go to "Subdomains"**  
   Find it under the **Domains** section.

3. **Fill in the Subdomain Form**

   - **Subdomain**: `app` (or any prefix)
   - **Domain**: Select the main domain (e.g., `yourdomain.com`)
   - **Document Root**: Auto-filled (e.g., `public_html/app`)

4. **Click "Create"**  
   The subdomain is now added and ready to use.

---

# 🗃️ How to Create MySQL User and Database in cPanel

This guide shows how to create a **MySQL database**, a **user**, and connect them using **cPanel**. Perfect for setting up Laravel, WordPress, or any PHP application.

---

## ✅ Step-by-Step Instructions

### 1. **Log in to cPanel**

- URL: `https://yourdomain.com/cpanel`

---

### 2. **Open "MySQL® Databases"**

- Found under the **Databases** section.

---

### 3. **Create a New Database**

- In the **Create New Database** field:
  - Enter a name (e.g., `myapp_db`)
  - Click **“Create Database”**

---

### 4. **Create a New Database User**

- Scroll down to **MySQL Users > Add New User**
  - Username: `myapp_user`
  - Password: (Use a strong password or the password generator)
  - Click **“Create User”**

---

### 5. **Add User to Database**

- Under **Add User to Database**:
  - Select the **user** and **database** you just created
  - Click **“Add”**

---

### 6. **Set User Privileges**

- Check **“All Privileges”**
- Click **“Make Changes”**

---

# ⚙️ How to Increase Max Upload Size, Execution Time, and PHP Limits via cPanel

Follow these steps to increase PHP configuration values like `upload_max_filesize`, `post_max_size`, `max_execution_time`, and others using cPanel.

---

## ✅ Step 1: Log in to cPanel

- URL: `https://yourdomain.com/cpanel`

---

## ✅ Step 2: Open **Select PHP Version** or **MultiPHP INI Editor**

- Go to **"Software"** section
- Click on:
  - ✅ **Select PHP Version** _(if available)_ → then click \*_“Options”_
  - OR
  - ✅ **MultiPHP INI Editor**

---

## ✅ Step 3: Modify PHP Settings

### If Using **Select PHP Version → Options**

- Locate and change the values:

| Setting               | Recommended Value |
| --------------------- | ----------------- |
| `upload_max_filesize` | `64M` or higher   |
| `post_max_size`       | `64M` or higher   |
| `max_execution_time`  | `300`             |
| `max_input_time`      | `300`             |
| `memory_limit`        | `256M` or higher  |

Changes are saved automatically.

---

# 🔧 How to Change PHP Version per Project Using MultiPHP Manager (cPanel)

Use this guide to set a different PHP version for each domain or subdomain individually using **MultiPHP Manager** in cPanel.

---

## ✅ Step-by-Step Instructions

### 1. **Log in to cPanel**

- Go to: `https://yourdomain.com/cpanel`

---

### 2. **Open MultiPHP Manager**

- Under the **Software** section, click **“MultiPHP Manager”**

---

### 3. **Select Domain/Subdomain**

- You’ll see a list of all your domains and subdomains.
- **Check the box** next to the domain you want to change (e.g., `example.com`, `app.example.com`)

---

### 4. **Choose PHP Version**

- On the right, select the desired PHP version from the dropdown menu (e.g., `PHP 8.1`, `PHP 7.4`, etc.)

---

### 5. **Click “Apply”**

- cPanel will apply the selected PHP version only to that domain.

---

## 🔁 Notes

- ✅ Laravel 9+ requires **PHP 8.0 or higher**
- ✅ Each domain or subdomain can use a **different PHP version**
- ✅ Use `phpinfo()` to verify the PHP version if needed

---

## 🧪 Optional: Test PHP Version

Create a `phpinfo.php` file inside your project’s root folder:

```php
<?php phpinfo(); ?>
```

# ⏱️ How to Create a Cron Job in cPanel for a Specific URL

This guide shows how to schedule a cron job in **cPanel** to run a script or task by accessing a specific **URL** (e.g., Laravel task, webhook, or custom PHP script).

---

## ✅ Steps to Add a Cron Job for a URL

### 1. **Log in to cPanel**

- URL: `https://yourdomain.com/cpanel`

---

### 2. **Go to "Cron Jobs"**

- Find it under the **Advanced** section.

---

### 3. **Set the Schedule**

- Choose how often the URL should be triggered:
  - Example: every 5 minutes
    - Minute: `*/5`
    - Hour: `*`
    - Day: `*`
    - Month: `*`
    - Weekday: `*`

---

### 4. **Add the Command**

Use `wget`, `curl`, or `lynx` to access the URL:

#### Option 1: Using `wget`

```bash
wget -q -O /dev/null https://yourdomain.com/your-script
---

# 📧 How to Create Webmail Accounts for a Domain Using cPanel

This guide explains how to create email addresses (e.g., `info@yourdomain.com`) using cPanel’s **Email Accounts** feature.

---

## ✅ Step-by-Step Guide

### 1. **Log in to cPanel**
- URL: `https://yourdomain.com/cpanel`

---

### 2. **Go to "Email Accounts"**
- Found under the **Email** section.

---

### 3. **Click “Create”**

---

### 4. **Fill in Email Details**

| Field            | Description                                 |
|------------------|---------------------------------------------|
| **Domain**        | Select your domain (e.g., `yourdomain.com`) |
| **Username**      | Enter email prefix (e.g., `info`, `admin`)  |
| **Password**      | Set a strong password or use generator      |
| **Storage Space** | Set mailbox quota (e.g., 500MB or Unlimited)|

---

### 5. **Click “Create”**
- Your email account will be created immediately.

---

## 📬 Accessing Webmail

### 1. Via cPanel
- Go to **Email Accounts** → Click **“Check Email”**

### 2. Direct Login
- Visit: `https://yourdomain.com/webmail`
- Login with:
  - **Email**: `info@yourdomain.com`
  - **Password**: (you set earlier)

---

## 🔒 Security Tips

- Use strong passwords and 2FA (if available).
- Always use HTTPS for login.
- Monitor file changes and malware scans.

---

## 📞 Support Info

- **Support Email**: support@yourdomain.com
- **Hosting Provider Contact**: [HostingProviderSupportLink]
- **Emergency Access (root/SSH)**: Not available on shared hosting

---

## 📝 Notes

- Changes via cPanel affect live site immediately.
- For staging, consider using subdomains or separate folders.
- Limit PHP versions per domain if needed via MultiPHP Manager.

---
```
