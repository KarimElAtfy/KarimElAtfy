# Hi, I'm Karim

I'm a Computer Engineering student at Politecnico di Milano, currently building practical skills in Cloud Engineering, Infrastructure as Code and DevSecOps on Azure.

I focus on learning by building real projects: designing infrastructure, writing Terraform, deploying workloads, debugging issues, documenting decisions and improving each project step by step.

My current goal is to grow toward Cloud / Infrastructure / DevOps engineering roles by combining academic foundations with hands-on cloud projects.

---

## Current Focus

* Azure cloud infrastructure
* Infrastructure as Code with Terraform
* Linux fundamentals for cloud environments
* Docker and containerized workloads
* GitHub Actions and CI/CD workflows
* Cloud security fundamentals
* Identity, access control and secret management
* Monitoring, logging and observability

---

## Current Background

* **Azure** — practical familiarity with core infrastructure services, networking, identity and deployment workflows
* **Terraform** — actively using it to build modular Azure infrastructure projects
* **Docker** — containerizing applications and validating images locally and in CI/CD
* **Git / GitHub** — comfortable with commits, branches, Pull Requests and GitHub Actions workflows
* **Linux** — improving operational confidence through cloud infrastructure projects
* **Python** — academic background, now also applied in a containerized FastAPI cloud project
* **Networking** — learning and applying subnetting, access control, load balancing and private infrastructure patterns
* **Security** — practicing RBAC, Managed Identity, Key Vault, secretless CI/CD and security scanning

---

## Certifications

* **AZ-900: Microsoft Azure Fundamentals**
* Currently preparing for **AZ-104** and **CCNA**

---

## Featured Projects

### 1. [Azure Terraform DevSecOps Container Platform](https://github.com/KarimElAtfy/Azure-Terraform-DevSecOps-Container-Platform)

A production-inspired Azure DevSecOps project that deploys a containerized FastAPI application using Terraform, Docker, Azure Container Apps, Azure Container Registry, Managed Identity, Key Vault, Application Insights, Log Analytics and GitHub Actions with OIDC.

**Focus of this step**
Move from VM-based infrastructure projects to a full containerized DevSecOps workflow with CI/CD, identity-based security, secret management, observability and automated deployment validation.

**What it includes**

* Containerized FastAPI application
* Dockerfile with non-root runtime user
* Azure Container Registry with admin user disabled
* Azure Container Apps deployment
* Azure Key Vault secret reference
* Runtime Managed Identity with `AcrPull` and Key Vault access
* GitHub Actions Managed Identity for CI/CD
* GitHub OIDC authentication without Azure client secrets
* Terraform remote state on Azure Storage
* Modular Terraform stacks: bootstrap, core and app
* Pull Request checks with Terraform validation, Docker build, Checkov and Trivy
* Automated deployment workflow on merge to `main`
* Post-deployment smoke test
* Application Insights and Log Analytics integration
* Architecture, security, troubleshooting, cost management and cleanup documentation

**What this project helped me practice**

* End-to-end DevSecOps workflow design
* Azure Container Apps deployment
* Docker image build and registry push workflow
* Managed Identity and Azure RBAC
* Key Vault secret management without storing secret values in Terraform state
* GitHub Actions OIDC authentication
* Terraform remote state and stack separation
* Security scanning with Checkov and Trivy
* Application observability with OpenTelemetry and Application Insights
* Smoke testing after deployment
* Writing recruiter-ready technical documentation

---

### 2. [Azure Terraform Load Balanced Web Platform](https://github.com/KarimElAtfy/Azure-Terraform-Load-Balanced-Web-Platform)

A hands-on Azure infrastructure project built with Terraform to deploy a small load-balanced web platform with a public frontend, private ARM64 Ubuntu backend virtual machines, Azure Bastion for secure administration and automated provisioning with cloud-init.

**Focus of this step**
Move from private infrastructure design to public service delivery through a dedicated frontend while keeping backend virtual machines private.

**What it includes**

* Public Azure Load Balancer
* Two private ARM64 Ubuntu backend web VMs
* Backend pool and HTTP health probe
* Load balancing rule for web traffic on port 80
* Azure Bastion for secure administrative access
* Network Security Group and subnet-based security
* cloud-init bootstrap for automated Nginx provisioning
* Log Analytics Workspace for monitoring foundation

**What this project helped me practice**

* Public frontend and private backend platform design
* Azure Load Balancer fundamentals
* Health probes and traffic distribution
* Multi-VM infrastructure design with Terraform
* Secure VM administration through Bastion
* cloud-init automation across multiple instances
* More resilient web platform design on Azure

---

### 3. [Azure Terraform Secure Private Platform](https://github.com/KarimElAtfy/Azure-Terraform-Secure-Private-Platform)

A Terraform-based Azure infrastructure project focused on private compute, secure administrative access and monitoring foundations, using Azure Bastion instead of direct public VM exposure.

**Focus of this step**
Shift from segmented infrastructure to a private-first platform design with more secure administrative access and monitoring components.

**What it includes**

* Private Linux virtual machine with no public IP
* Azure Bastion for secure administrative access
* Virtual network with dedicated subnets
* Log Analytics Workspace for monitoring foundation
* Key Vault included as a security-oriented platform component
* Modular Terraform structure
* ARM64 Ubuntu deployment on Azure

**What this project helped me practice**

* Private infrastructure design on Azure
* Secure VM administration without direct public SSH
* Terraform module organization
* Bastion-based access patterns
* Monitoring and security service integration
* More production-aware platform design

---

### 4. [Azure Terraform Secure Two-Tier Infrastructure](https://github.com/KarimElAtfy/Azure-Terraform-IaC-Secure-Two-Tier-Infrastructure)

A more realistic Azure infrastructure project built with Terraform to simulate a two-tier environment with separate management and workload layers, subnet-based security and automated provisioning.

**Focus of this step**
Move from a single VM design to a more structured infrastructure with separated roles and tighter network control.

**What it includes**

* Virtual network with separate management and web subnets
* Subnet-based Network Security Groups
* Dedicated management VM for administrative access
* Public-facing web VM running Nginx
* SSH key-based access control
* Automated VM provisioning through cloud-init
* ARM64 Ubuntu virtual machines on Azure

**What this project helped me practice**

* Azure virtual network and subnet design
* Network Security Groups and controlled access paths
* Infrastructure as Code with Terraform
* Linux VM provisioning and SSH authentication
* cloud-init automation
* More realistic infrastructure design

---

### 5. [Azure Terraform Linux VM](https://github.com/KarimElAtfy/Azure-Terraform-IaC-LinuxVM)

A practical Azure infrastructure project built with Terraform to deploy a Linux virtual machine with basic networking, secure access and automated web server provisioning.

**Focus of this step**
Build and deploy a first Azure virtual machine environment with Infrastructure as Code.

**What it includes**

* Resource Group, Virtual Network and Subnet
* Network Security Group rules
* Linux virtual machine with SSH key-based access
* Automated Nginx installation through cloud-init

**What this project helped me practice**

* Azure resource structure
* Infrastructure as Code fundamentals
* Basic networking and access control
* Practical deployment workflow from code to running VM

---

## Project Progression

My projects are intentionally built as a progression:

```text
Linux VM
   ↓
Two-tier infrastructure
   ↓
Private platform with Bastion
   ↓
Load-balanced web platform
   ↓
DevSecOps container platform with CI/CD
```

Each project adds a new layer of complexity:

* First, basic Azure infrastructure and Terraform.
* Then, subnet separation and security rules.
* Then, private compute and secure administration.
* Then, load balancing and private backend services.
* Finally, containerized workloads, CI/CD, Managed Identity, Key Vault, observability and security scanning.

This progression helps me learn cloud engineering through real implementation rather than isolated theory.

---

## How I Approach Learning

I learn best by building.

My approach is:

```text
Build something
Break something
Understand the problem
Fix it
Document what happened
Improve the next project
```

I try to make each project more complete than the previous one, both technically and in the way it is documented.

I care about being able to explain not only what I built, but also why each design choice was made.

---

## Currently Improving

* Azure administration knowledge
* Terraform best practices
* Docker and container workflows
* GitHub Actions CI/CD
* Linux operational confidence
* Networking fundamentals
* Cloud security fundamentals
* Infrastructure design mindset
* Monitoring and troubleshooting skills

---

## Languages

* Italian — native
* English — C1
* French — conversational
* German — currently learning
* Russian — currently learning

---

## Contact

* LinkedIn: [www.linkedin.com/in/karim-el-atfy](https://www.linkedin.com/in/karim-el-atfy)
* Portfolio [www.kaystack.dev](https://www.kaystack.dev)
