# Cloud-1: Automated WordPress Deployment Infrastructure

## Overview
This project implements an automated deployment system for a WordPress infrastructure using Docker containers and Infrastructure as Code principles. It focuses on creating a secure, scalable, and maintainable deployment process on cloud platforms.

## 🎯 Key Features
- Fully automated deployment process
- Container-based architecture (1 process = 1 container)
- Persistent data storage
- Automatic service recovery
- TLS encryption support
- Secure database access
- Multi-server deployment capability

## 🛠️ Technical Stack
- **Automation**: Ansible
- **Containerization**: Docker, Docker Compose
- **Web Server**: WordPress, PHP-MyAdmin
- **Database**: MySQL
- **Operating System**: Ubuntu 20.04 LTS
- **Security**: TLS, SSH

## 📋 Prerequisites
- Ubuntu 20.04 LTS target machine
- SSH daemon running on target
- Python installed on target
- SSH key access configured
- Docker and Docker Compose
- Ansible

## 🏗️ Architecture
```
                           HTTPS
                             │
                        ┌────▼────┐
                        │  nginx  │
                        └────┬────┘
                             │
              ┌──────────────┴──────────────┐
              │                             │
         ┌────▼────┐                   ┌────▼──────┐
         │WordPress│                   │PHP-MyAdmin│
         └────┬────┘                   └────┬──────┘
              │                             │
              └─────────────┬───────────────┘
                            │
                       ┌────▼────┐
                       │  MySQL  │
                       └─────────┘
```

## 📦 Components
- **WordPress Container**: Main application server
- **MySQL Container**: Database server
- **PHP-MyAdmin Container**: Database management interface
- **Nginx Container**: Web server and reverse proxy

## 💾 Persistence
Data persistence is maintained through Docker volumes for:
- WordPress files
- MySQL database
- Uploaded media
- Configuration files

## 🔒 Security Considerations
- Limited public access to services
- Database accessible only within internal network
- TLS encryption for all public endpoints
- SSH key-based authentication
- Regular security updates
