# 🛠️ DB-Automation-Lab

[![MySQL](https://img.shields.io/badge/database-MySQL-blue.svg?style=flat-square&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Flyway](https://img.shields.io/badge/migration-Flyway-red.svg?style=flat-square&logo=redhat&logoColor=white)](https://flywaydb.org/)
[![Docker](https://img.shields.io/badge/container-Docker-blue.svg?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-darkcyan.svg?style=flat-square&logo=github-actions&logoColor=white)](https://github.com/features/actions)

An automated, production-ready Database CI/CD pipeline designed to manage schema migrations, version tracking, and continuous deployment for a MySQL database instance. This lab demonstrates how to eliminate manual database scripts and integrate schema evolutionary changes safely into a delivery pipeline using modern DevOps practices.

---

## 🏗️ Architecture & Workflow Overview

1. **Local Development:** Infrastructure components (MySQL, Flyway) are containerized using Docker Compose for instant replication.
2. **Versioned Migration:** SQL migration scripts are managed chronologically inside the `sql/` directory following strict Flyway naming conventions.
3. **CI/CD Pipeline:** On every push or pull request to the `main` branch, a GitHub Actions workflow triggers to automatically validate, test, and apply migrations.

---

## 🚀 Key Features

* **Automated Schema Migrations:** Tracks, versions, and applies database changes seamlessly using Flyway.
* **Infrastructure as Code (Lightweight):** Zero-install local setup using multi-container Docker environments.
* **Automated CI/CD Validation:** Continuous integration via GitHub Actions ensures broken SQL syntax or migration conflicts never reach production environments.
* **Persistent Storage:** Dockerized MySQL database utilizes named volumes to guarantee data persistence across container lifecycles.

---

## 🧰 Tech Stack & Tools

* **Database:** MySQL
* **Migration Engine:** Flyway (Community Edition)
* **Containerization:** Docker & Docker Compose
* **CI/CD Automation:** GitHub Actions

---

## 📁 Repository Structure

```text
├── .github/workflows/    # GitHub Actions CI/CD configuration
├── flyway/conf/          # Flyway configuration profiles (connection strings, schemas)
├── sql/                  # Chronological SQL migration files (V1__, V2__, etc.)
├── docker-compose.yml    # Defines local MySQL and infrastructure services
└── README.md             # Project documentation
