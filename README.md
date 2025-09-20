# Ansible Projects – 1st Lab

This repository contains a structured Ansible lab setup to automate deployment of:

- **MariaDB Galera Cluster**
- **Flask Web Application**
- **Nginx as a Reverse Proxy**

---

## 📁 Project Structure

1st-lab/
├── app/ # Standalone App Setup (DB + Web + Config)
├── maria-galera/ # Galera Cluster Setup
├── webhost/ # Web Server (Flask + Nginx)


### 🔹 maria-galera/
- `deploy_maria`: Installs and configures MariaDB
- `deploy_galera`: Sets up Galera cluster with handlers and templated config
- `test_cluster`: Testing tasks for validating the cluster

### 🔹 webhost/
- `flask`: Installs Flask and runs sample app
- `nginx`: Configures Nginx as reverse proxy to Flask

### 🔹 app/
- `db`, `config`, `code`: Modular roles to set up a sample stack (database + configs + application logic)

---

## 📦 Requirements

- Ansible 2.10+
- CentOS/RHEL-based hosts (192.168.100.x)
- SSH access to managed nodes
- Python installed on nodes (for Ansible)

---

📁 Project Structure

<pre> ``` 1st-lab/ ├── app/ # Standalone App Setup (DB + Web + Config) │ ├── code/ │ │ ├── files/ │ │ │ ├── app.py │ │ │ └── app.service │ │ ├── handlers/main.yml │ │ └── tasks/main.yml │ ├── config/ │ │ ├── files/app │ │ ├── handlers/main.yml │ │ ├── tasks/main.yml │ │ └── templates/app.conf.j2 │ ├── db/ │ │ ├── files/employee_db.sql │ │ └── tasks/main.yml │ ├── dbplay.yml │ ├── inventory.ini │ ├── mplay.yml │ └── whplay.yml ├── maria-galera/ # Galera Cluster Setup │ ├── inventory.ini │ ├── mplay.yml │ └── roles/ │ ├── deploy_galera/ │ │ ├── handlers/main.yml │ │ ├── tasks/main.yml │ │ └── templates/galera.cnf.j2 │ ├── deploy_maria/ │ │ ├── files/maria.repo │ │ ├── handlers/mail.yml │ │ └── tasks/main.yml │ └── test_cluster/ ├── webhost/ # Web Server Setup (Flask + Nginx) │ ├── inventory.ini │ ├── mplay.yml │ └── roles/ │ ├── flask/ │ │ ├── handlers/main.yml │ │ └── tasks/main.yml │ └── nginx/ │ ├── handlers/main.yml │ ├── tasks/main.yml │ └── templates/nginx.conf.j2 ├── LICENSE └── README.md ``` </pre>


---
## 🚀 Usage

Each directory is an independent Ansible setup. You can run any playbook with:

```bash
ansible-playbook -i inventory.ini mplay.yml



PRODUCT BY AHMEDANAS - FOR EDUCATION 