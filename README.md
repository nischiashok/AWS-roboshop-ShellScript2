# AWS Roboshop Shell Scripting 2 🚀  
Automate the deployment and configuration of Roboshop microservices on AWS with modular Bash scripts.

<details>
  <summary><strong>📑 Table of Contents</strong></summary>

- [✨ Features](#-features)
- [🧭 Quickstart](#-quickstart)
- [🔧 Commands](#-commands)
- [🖼️ Screenshots / Images](#-screenshots--images)
- [🧪 Testing & Linting](#-testing--linting)
- [🛡️ Security Notes](#-security-notes)
- [🧰 Troubleshooting & FAQ](#-troubleshooting--faq)
- [📋 Contributing](#-contributing)
- [📄 License](#-license)
</details>

---

## ✨ Features

- Automated setup for Roboshop microservices: frontend, MongoDB, catalogue, Redis, user, cart, MySQL, RabbitMQ, shipping, payment.
- Centralized logging for all operations.
- Root privilege checks for safe execution.
- Modular validation for each installation/configuration step.
- Downloads and configures service artifacts from S3.
- Service management via systemd.
- Custom Nginx configuration deployment.
- Easy extensibility for new services.

---

## 🧭 Quickstart

### Requirements

- **OS:** Linux (RHEL/CentOS/Amazon Linux recommended)
- **Shell:** Bash 4.x+
- **Tools:** `dnf`, `curl`, `unzip`, `systemctl`
- **Permissions:** Root access required

### Installation

```sh
git clone https://github.com/nischiashok/AWS-roboshop-ShellScript2.git
cd AWS-roboshop-ShellScript2/repo/AWS-roboshop-ShellScript2
```

### Configuration

- Ensure all required service config files (e.g., `nginx.conf`, `mongo.repo`, `*.service`) are present in the script directory.
- No `.env.example` detected; configuration is handled via script arguments and environment.

### Usage Example

To set up the frontend service:

```sh
sudo ./frontend.sh
```

Repeat similarly for other microservices (`mongodb.sh`, `catalogue.sh`, etc.).

### 🖼️ Showcase

Below are key screenshots demonstrating the Roboshop UI and workflow:

![Cart page showing items and checkout](screenshot/Screenshot%202025-07-20%20122948.png)
*Cart page with items and checkout summary*

![Order history after login](screenshot/Screenshot%202025-07-20%20123016.png)
*Order history and user greeting after login*

![Welcome page with technology stack](screenshot/Screenshot%202025-07-20%20123030.png)
*Welcome page listing supported technologies*

![Login and registration forms](screenshot/Screenshot%202025-07-20%20123105.png)
*Login and registration forms*

![Order history empty state](screenshot/Screenshot%202025-07-20%20123130.png)
*Order history empty state*

---

## 🔧 Commands

| Script Name      | Purpose                                 | Usage                   | Example                   |
|------------------|-----------------------------------------|-------------------------|---------------------------|
| `frontend.sh`    | Setup and configure Nginx frontend      | `sudo ./frontend.sh`    | `sudo ./frontend.sh`      |
| `mongodb.sh`     | Install and configure MongoDB           | `sudo ./mongodb.sh`     | `sudo ./mongodb.sh`       |
| `catalogue.sh`   | Deploy catalogue microservice           | `sudo ./catalogue.sh`   | `sudo ./catalogue.sh`     |
| `redis.sh`       | Install and configure Redis             | `sudo ./redis.sh`       | `sudo ./redis.sh`         |
| `user.sh`        | Deploy user microservice                | `sudo ./user.sh`        | `sudo ./user.sh`          |
| `cart.sh`        | Deploy cart microservice                | `sudo ./cart.sh`        | `sudo ./cart.sh`          |
| `mysql.sh`       | Install and configure MySQL             | `sudo ./mysql.sh`       | `sudo ./mysql.sh`         |
| `rabbitmq.sh`    | Install and configure RabbitMQ          | `sudo ./rabbitmq.sh`    | `sudo ./rabbitmq.sh`      |
| `shipping.sh`    | Deploy shipping microservice            | `sudo ./shipping.sh`    | `sudo ./shipping.sh`      |
| `payment.sh`     | Deploy payment microservice             | `sudo ./payment.sh`     | `sudo ./payment.sh`       |
| `common.sh`      | Shared functions for validation/logging | Sourced by other scripts| -                         |

> All scripts require root privileges.

---

## 🖼️ Screenshots / Images

![Cart page](screenshot/Screenshot%202025-07-20%20122948.png)
*Cart page with items and checkout summary*

![Order history](screenshot/Screenshot%202025-07-20%20123016.png)
*Order history and user greeting after login*

![Welcome page](screenshot/Screenshot%202025-07-20%20123030.png)
*Welcome page listing supported technologies*

![Login/Register](screenshot/Screenshot%202025-07-20%20123105.png)
*Login and registration forms*

![Order history empty](screenshot/Screenshot%202025-07-20%20123130.png)
*Order history empty state*

![Additional UI](screenshot/Screenshot%202025-07-20%20123155.png)
*Additional UI view*

![More UI](screenshot/Screenshot%202025-07-20%20123215.png)
*More UI elements*

![UI details](screenshot/Screenshot%202025-07-20%20123230.png)
*UI details*

![UI overview](screenshot/Screenshot%202025-07-20%20123249.png)
*UI overview*

---

## 🧪 Testing & Linting

Run [ShellCheck](https://www.shellcheck.net/) on all scripts:

```sh
shellcheck *.sh
```

Format scripts with [shfmt](https://github.com/mvdan/sh):

```sh
shfmt -w -i 4 *.sh
```

No automated unit/integration tests detected. Manual validation recommended after each deployment.

---

## 🛡️ Security Notes

- No hardcoded secrets detected in scripts.
- Service credentials should be managed via environment or secure vaults.
- Run scripts with root only when required.

---

## 🧰 Troubleshooting & FAQ

1. **ERROR:: Please run this script with root access**
   - Solution: Prefix command with `sudo`.
2. **Missing binaries (`dnf`, `curl`, `unzip`)**
   - Solution: Install required packages via your OS package manager.
3. **Service fails to start**
   - Solution: Check logs and systemd status.
4. **Permission denied on log folder**
   - Solution: Ensure log folder is writable by root.
5. **Network issues downloading artifacts**
   - Solution: Verify internet connectivity and S3 URL accessibility.

---

## 🛠️ Related Repositories & Continuous Learning 📚✨

Ready to advance your shell scripting and automation skills? Explore these curated repositories for a hands-on journey from foundational scripts to cloud-scale automation:

- [AWS-roboshop-ShellScript1](https://github.com/nischiashok/AWS-roboshop-ShellScript1)  
  ☁️ **Roboshop Automation Scripts for AWS** – Dive into practical, cloud-ready scripts powering resilient microservices on AWS! 🚀

- [AWS-roboshop-ShellScript2](https://github.com/nischiashok/AWS-roboshop-ShellScript2)  
  🤖 **Integrated Infrastructure Setup** – Experience seamless Roboshop deployments with unified automation for common folders and services. 🌐⚙️

---

## 🤝 Credits & Connect 💬❤️

Inspired by cloud-native DevOps workflows and automation best practices.  
Created with dedication by [nischitha A](https://github.com/nischiashok/) 👩‍💻✨
