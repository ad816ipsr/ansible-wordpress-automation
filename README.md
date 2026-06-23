# 🚀 Ansible WordPress Automation

Automated deployment of a secure WordPress hosting environment on AWS EC2 using Ansible.

This project provisions a production-ready WordPress server with Nginx, PHP, MariaDB, SSL (Let's Encrypt/Certbot), phpMyAdmin, and SFTP access through reusable Ansible playbooks.

---

## 📌 Project Overview

This project automates the complete setup of a WordPress web server from scratch.

Instead of manually installing and configuring every component, a single Ansible playbook deploys the entire infrastructure in minutes.

The automation includes:

- Linux server configuration
- MariaDB installation and database creation
- PHP 8.x installation
- Nginx web server configuration
- WordPress installation
- phpMyAdmin configuration
- SFTP user setup
- Automatic SSL certificate generation using Certbot
- HTTPS-enabled website deployment

---

# 🏗️ Architecture

```
                +----------------------+
                |    Ansible Master    |
                |  (Control Node)      |
                +----------+-----------+
                           |
                      SSH (Ansible)
                           |
                           |
                +----------v-----------+
                |    AWS EC2 Server    |
                | (Managed Node)       |
                +----------+-----------+
                           |
        --------------------------------------------
        |           |           |          |         |
      Nginx      PHP-FPM     MariaDB   phpMyAdmin  SFTP
        |
    WordPress
        |
 HTTPS (Let's Encrypt SSL)
```

---

# ⚙️ Technologies Used

- Ansible
- AWS EC2
- Amazon Linux 2023
- Nginx
- PHP 8.x
- MariaDB 10.6
- WordPress
- phpMyAdmin
- Certbot (Let's Encrypt)
- OpenSSH / SFTP
- Git
- GitHub

---

# 📂 Project Structure

```
project-ansible/
│
├── inventory
├── ansible.cfg
├── site.yml
│
├── playbooks/
│   ├── 01-users.yml
│   ├── 02-nginx.yml
│   ├── 03-php.yml
│   ├── 04-mariadb.yml
│   ├── 05-database.yml
│   ├── 06-wordpress.yml
│   ├── 07-sftp.yml
│   ├── 08-phpmyadmin.yml
│   └── 09-ssl.yml
│
├── templates/
│   ├── nginx-site.conf.j2
│   └── wp-config.php.j2
│
└── vars/
    └── main.yml
```

---

# ✨ Features

- Automated server provisioning
- Automated WordPress installation
- Automated database creation
- Nginx virtual host configuration
- HTTPS with Let's Encrypt SSL
- Secure SFTP access
- phpMyAdmin integration
- Idempotent Ansible playbooks
- Reusable templates using Jinja2
- Centralized variable management

---

# 🚀 Deployment

Run the complete automation using:

```bash
ansible-playbook site.yml
```

The playbook automatically:

- Creates the website directory
- Installs required packages
- Configures Nginx
- Configures PHP-FPM
- Creates the MariaDB database
- Deploys WordPress
- Configures phpMyAdmin
- Creates the SFTP user
- Generates SSL certificates
- Restarts required services

---

# 🌐 Result

After successful execution:

### WordPress

```
https://your-domain/wp-admin
```

### phpMyAdmin

```
https://your-domain/phpmyadmin
```

### SFTP

```
Host: your-domain
```

---

# 📷 Screenshots

Add screenshots here:

- Home Page
- WordPress Dashboard
- phpMyAdmin
- SFTP Login
- Successful Ansible Playbook Run

---

# 📚 Skills Demonstrated

- Infrastructure Automation
- Configuration Management
- Linux Administration
- Web Server Administration
- Database Administration
- SSL/TLS Configuration
- Ansible Playbooks
- Jinja2 Templates
- AWS EC2
- DevOps Fundamentals

---

# 🔒 Security

Sensitive credentials are managed through Ansible variables.

Before publishing a public repository, replace passwords with placeholders.

Example:

```yaml
db_password: "<YOUR_DB_PASSWORD>"
wordpress_admin_password: "<YOUR_PASSWORD>"
sftp_password: "<YOUR_PASSWORD>"
```

---

# 📈 Future Improvements

- Docker support
- Kubernetes deployment
- Ansible Roles
- CI/CD with GitHub Actions
- Automated backups
- Monitoring with Prometheus & Grafana
- Multi-server deployment
- AWS Load Balancer support

---

# 👨‍💻 Author

**Adarsh Prasad**

GitHub:
https://github.com/ad816ipsr

LinkedIn:
(Add your LinkedIn profile here)

---

## ⭐ If you found this project useful, consider giving it a Star!
