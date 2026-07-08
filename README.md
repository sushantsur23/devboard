# 🚀 Enterprise DevSecOps CI/CD Pipeline using GitHub Actions

<p align="center">

<img src="https://img.shields.io/badge/GitHub-Actions-blue?logo=githubactions"/>
<img src="https://img.shields.io/badge/DevSecOps-Enterprise-success"/>
<img src="https://img.shields.io/badge/CI/CD-Automation-orange"/>
<img src="https://img.shields.io/badge/SonarQube-Code%20Quality-blue"/>
<img src="https://img.shields.io/badge/OWASP-ZAP-red"/>
<img src="https://img.shields.io/badge/Trivy-Container%20Security-brightgreen"/>
<img src="https://img.shields.io/badge/GitLeaks-Secrets%20Scanning-critical"/>
<img src="https://img.shields.io/badge/Docker-Buildx-2496ED?logo=docker"/>
<img src="https://img.shields.io/badge/Go-1.22%20|%201.23%20|%201.24-00ADD8?logo=go"/>
<img src="https://img.shields.io/badge/NodeJS-20-green?logo=node.js"/>
<img src="https://img.shields.io/badge/License-MIT-blue"/>

</p>

---

# 📖 Overview

This repository demonstrates an **Enterprise DevSecOps CI/CD Pipeline** built entirely using **GitHub Actions**.

The project showcases how modern organizations implement **Shift Left Security**, **Continuous Integration**, **Continuous Delivery**, **Automated Security Validation**, and **Quality Gates** before software reaches production.

Unlike traditional pipelines where security is performed at the end, this project integrates security throughout the Software Development Lifecycle (SDLC).

The repository contains reusable GitHub workflows that execute independently and in parallel to maximize efficiency while enforcing security and quality standards.

---

# 🎯 Project Objectives

- Build Enterprise DevSecOps Pipeline
- Learn GitHub Actions Reusable Workflows
- Implement Matrix Build Strategy
- Execute Parallel Jobs
- Integrate Shift Left Security
- Perform Static & Dynamic Security Testing
- Automate Code Quality Validation
- Scan Third-party Dependencies
- Detect Secrets
- Scan Docker Images
- Deploy Secure Applications
- Execute Runtime Security Testing

---

# 🏗 Enterprise Pipeline Architecture

```

Developer Push

│

▼

GitHub Actions Trigger

│

▼

Master Workflow (devsecops.yml)

│

├──────────────────────────────────────────────┐

│ │

▼ ▼

Parallel Workflow Execution

│

├────────────────────────────────────────────────────────────┐

│ │ │ │ │ │

▼ ▼ ▼ ▼ ▼ ▼

Code Quality Unit Tests Secret Scan Dependency Scan Sonar Docker Scan

│ │ │ │ │ │

└──────────────────────────────┬───────────────────────────────┘

▼

Docker Build & Push

(Matrix Strategy)

│

▼

Deploy to Self Hosted Runner

│

▼

OWASP ZAP DAST

│

▼

Security Gate Validation

│

▼

Production Ready

```

---

# 📁 Repository Structure

```

.github/

└── workflows/

├── devsecops.yml

├── matrix.yml

├── code-quality.yml

├── code-tests.yml

├── dependency-scan.yml

├── sonar-scan.yml

├── docker-scans.yml

├── docker-push.yml

├── secret-scanning.yml

├── deploy.yml

└── dast.yml

backend/

frontend/

docker-compose.yml

README.md

```

---

# ⚙ Workflow Overview

| Workflow | Purpose |
|------------|--------------------------------|
| devsecops.yml | Master orchestration pipeline |
| matrix.yml | Matrix build demonstration |
| code-quality.yml | Linting, Formatting & Static Validation |
| code-tests.yml | Unit Testing |
| dependency-scan.yml | Third-party dependency scanning |
| sonar-scan.yml | SonarQube Code Quality Analysis |
| docker-scans.yml | Docker Security Scanning |
| docker-push.yml | Build & Push Docker Images |
| deploy.yml | Application Deployment |
| dast.yml | OWASP ZAP Dynamic Security Testing |
| secret-scanning.yml | GitLeaks Secret Detection |

---

# 🚀 Workflow Details

---

## 🚀 devsecops.yml

### Purpose

Acts as the **Master Workflow** responsible for orchestrating the entire DevSecOps pipeline.

### Responsibilities

- Executes reusable workflows
- Controls job dependencies
- Executes jobs in parallel
- Builds Docker images
- Pushes images
- Deploys application
- Executes DAST

---

## ⚡ matrix.yml

Demonstrates GitHub Actions Matrix Strategy.

### Matrix Versions

- Go 1.22
- Go 1.23
- Go 1.24

Benefits

- Multi-version testing
- Runtime compatibility
- Faster execution

---

## 🧹 code-quality.yml

### Purpose

Performs Static Code Quality Validation.

### Activities

- Checkout Repository
- Install NodeJS
- Install npm Packages
- ESLint
- Setup Go
- go fmt
- go vet

Benefits

- Coding Standards
- Maintainability
- Early Defect Detection

---

## 🧪 code-tests.yml

Runs automated testing.

### Activities

- npm test
- go test
- Install Dependencies

Benefits

- Regression Testing
- Functional Validation

---

## 🔍 dependency-scan.yml

Scans third-party packages.

### Tools

- govulncheck
- npm audit

Checks

- Known CVEs
- Vulnerable Dependencies
- Outdated Packages

---

## 🔐 secret-scanning.yml

Detects secrets committed into Git repositories.

### Tool

GitLeaks

Detects

- AWS Keys
- Azure Secrets
- GitHub Tokens
- API Keys
- JWT Tokens
- Passwords

---

## 📊 sonar-scan.yml

Static Application Security Testing.

### Validates

- Bugs
- Vulnerabilities
- Code Smells
- Code Coverage
- Maintainability
- Reliability

Includes

Quality Gate Validation

---

## 🐳 docker-scans.yml

Container Security Validation.

### Tools

- Hadolint
- Trivy

Scans

- Base Image CVEs
- Operating System Packages
- Application Libraries
- Misconfigurations

---

## 📦 docker-push.yml

Builds Docker Images.

Uses Matrix Build

Builds

- Backend Image

- Frontend Image

Pushes images to Docker Registry simultaneously.

---

## 🚀 deploy.yml

Deploys application.

Runs on

Self Hosted Runner

Activities

- Docker Login
- Docker Pull
- Docker Compose Pull
- Docker Compose Up

---

## 🛡 dast.yml

Dynamic Application Security Testing.

Tool

OWASP ZAP

Checks

- SQL Injection

- Cross Site Scripting

- Security Headers

- Authentication Issues

- Session Management

- Information Disclosure

- OWASP Top 10

---

# 🖥️ GitHub Runners & Execution Environment

This project demonstrates both **GitHub-hosted runners** and **Self-Hosted GitHub Actions runners** to simulate an enterprise CI/CD environment.

## 🚀 GitHub-Hosted Runners

GitHub-hosted runners provide an ephemeral execution environment, making them ideal for standard CI workloads without requiring infrastructure management.

---

## ☁️ Self-Hosted Runner on AWS EC2

For deployment workloads, the pipeline can be configured to use a **Self-Hosted GitHub Actions Runner** running on an **AWS EC2 instance**. 

Using a self-hosted runner enables deployments within a private network while maintaining full control over compute resources, networking, security groups, IAM roles, and deployment tooling.

---

## 🔒 Repository Requirement

> **Note**
>
> GitHub Self-Hosted Runners are typically configured for **private repositories** in enterprise environments to ensure secure execution and prevent unauthorized workflow access.
>
> Before configuring a self-hosted runner on AWS EC2, convert this repository to a **Private Repository**, then register the runner using the repository or organization-level runner configuration provided by GitHub.
>
> This approach aligns with enterprise security best practices by restricting deployment workflows and protecting sensitive infrastructure credentials.

---

## 🏗️ Runner Strategy

| Pipeline Stage | Runner Type |
|----------------|------------|
| Code Checkout | GitHub Hosted Runner |
| Code Quality | GitHub Hosted Runner |
| Unit Tests | GitHub Hosted Runner |
| Secret Scanning | GitHub Hosted Runner |
| Dependency Scanning | GitHub Hosted Runner |
| SonarQube Analysis | GitHub Hosted Runner |
| Docker Build | GitHub Hosted Runner |
| Docker Image Scan | GitHub Hosted Runner |
| Docker Push | GitHub Hosted Runner |
| Application Deployment | AWS EC2 Self-Hosted Runner |
| OWASP ZAP DAST | AWS EC2 Self-Hosted Runner |

---

### 💡 Enterprise Deployment Model

In enterprise environments, organizations commonly adopt a **hybrid runner strategy**, where GitHub-hosted runners are used for CI tasks, while self-hosted runners deployed on cloud infrastructure (such as AWS EC2) are reserved for deployment and environment-specific operations. This approach combines the scalability of GitHub-managed infrastructure with the security and control of self-managed deployment environments.


# 🔐 Enterprise Security Controls

| Security Control | Status |
|------------------|--------|
| GitLeaks | ✅ |
| ESLint | ✅ |
| Go Vet | ✅ |
| Go Fmt | ✅ |
| SonarQube | ✅ |
| Govulncheck | ✅ |
| npm audit | ✅ |
| Docker Scan | ✅ |
| Trivy | ✅ |
| OWASP ZAP | ✅ |

---

# 🚦 Production Security Gate

Production deployments should be blocked if any scan reports the following:

| Severity | Action |
|------------|--------------------|
| Critical | ❌ Block Deployment |
| High | ❌ Block Deployment |
| Medium | ⚠ Manual Review |
| Low | Informational |

---

# ⚡ Parallel Execution

The following jobs execute simultaneously:

- Code Quality
- Unit Testing
- Dependency Scan
- Secret Scan
- SonarQube
- Docker Scan

This significantly reduces overall pipeline execution time.

---

# 🔁 Matrix Strategy

Docker Build uses Matrix Strategy.

Example

Backend

Frontend

Both images build simultaneously.

Benefits

- Reduced Build Time
- Better Resource Utilization
- Easier Maintenance

---

# 💻 Technology Stack

| Category | Technology |
|------------|----------------|
| CI/CD | GitHub Actions |
| Source Control | GitHub |
| Backend | Go |
| Frontend | NodeJS |
| Containers | Docker |
| Deployment | Docker Compose |
| Static Analysis | SonarQube |
| Secrets Scan | GitLeaks |
| Dependency Scan | govulncheck |
| npm audit | npm |
| Docker Scan | Trivy |
| Docker Lint | Hadolint |
| DAST | OWASP ZAP |

---

# 📈 DevSecOps Best Practices Implemented

✅ Shift Left Security

✅ Secure SDLC

✅ Infrastructure Ready

✅ Matrix Strategy

✅ Parallel Execution

✅ Reusable Workflows

✅ Security Gates

✅ Quality Gates

✅ Automated Testing

✅ Continuous Integration

✅ Continuous Delivery

✅ Container Security

✅ Runtime Security

✅ Secrets Management

---

# 🔮 Future Enhancements

- Terraform Security (Checkov)

- Kubernetes Deployment

- Helm Charts

- SBOM Generation

- Cosign Image Signing

- SLSA Provenance

- OpenSSF Scorecard

- GitHub Advanced Security

- Slack Notifications

- Microsoft Teams Notifications

- ArgoCD GitOps Deployment

- Kubernetes Admission Controller

- Falco Runtime Security

---

# 📚 Learning Outcomes

This repository demonstrates how enterprise organizations automate secure software delivery using:

- GitHub Actions
- DevSecOps
- Secure CI/CD
- Shift Left Security
- Reusable Workflows
- Parallel Pipelines
- Matrix Builds
- Security Gates
- Docker Security
- Runtime Security
- Automated Deployment

---

# 📷 Recommended Screenshots

To make this repository more attractive, include:

- 📸 GitHub Actions Pipeline
- 📸 SonarQube Dashboard
- 📸 Trivy Scan Report
- 📸 GitLeaks Report
- 📸 OWASP ZAP Report
- 📸 Application Dashboard
- 📸 DockerHub Repository
- 📸 Workflow Visualization

---

