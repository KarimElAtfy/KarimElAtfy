# Hi, I'm Karim

I'm a Computer Engineering student at Politecnico di Milano, building a junior profile around cloud infrastructure, Linux, networking, Terraform and DevOps.

I use GitHub as a public lab notebook for my cloud projects. Not everything here is meant to be perfect production architecture, but everything is built to teach me something real: how Azure resources fit together, how infrastructure breaks, how to document decisions, and how to improve the next deployment.

My portfolio is here: [kaystack.dev](https://kaystack.dev)

---

## What I'm aiming for

I'm currently looking for junior roles or internships in areas like:

* Junior Cloud Engineer
* Junior System Administrator
* Cloud Operations
* Junior DevOps / Platform Engineering
* Infrastructure or monitoring-focused roles

I am still early in my career, but I try to build projects that show how I think: start simple, add one layer at a time, document the choices, and be honest about what still needs hardening.

---

## Main project path

My Azure projects follow the same progression shown on my portfolio: from the most complete DevSecOps project down to the foundation infrastructure labs.

| Level | Project                        | Main idea                                               |
| ----- | ------------------------------ | ------------------------------------------------------- |
| L5    | DevSecOps Container Platform   | Containers, CI/CD, OIDC, security checks, observability |
| L4    | Load Balanced Web Platform     | Load balancer, private backends, health probes          |
| L3    | Secure Private Platform        | Bastion, private access, Key Vault, monitoring          |
| L2    | Secure Two-Tier Infrastructure | Subnet separation, management VM, workload VM           |
| L1    | Azure Terraform Linux VM       | First clean Azure VM deployment with Terraform          |

---

## Featured projects

### L5 · [Azure Terraform DevSecOps Container Platform](https://github.com/KarimElAtfy/Azure-Terraform-DevSecOps-Container-Platform)

This is my strongest project so far.

It takes a small FastAPI application, containerizes it with Docker, pushes the image to Azure Container Registry, and deploys it to Azure Container Apps through GitHub Actions. Terraform handles the Azure infrastructure, GitHub authenticates to Azure through OIDC, and the pipeline includes validation and security checks before deployment.

The point of this project was not just "run a container on Azure". I wanted to connect the pieces that usually appear together in a real workflow: infrastructure, identity, image build, secrets, deployment, logs, checks and cleanup.

**Main technologies**

* Azure Container Apps
* Azure Container Registry
* Azure Key Vault
* Managed Identity
* Log Analytics
* Application Insights
* Terraform
* Docker
* FastAPI
* GitHub Actions
* OIDC
* Checkov
* Trivy

**What this project shows**

* I can build a full deployment flow instead of only isolated resources.
* I understand why secretless authentication matters.
* I can separate Terraform layers instead of putting everything into one giant file.
* I can use CI checks to catch problems before deployment.
* I can validate a deployment with smoke tests and logs, not just by hoping the portal looks fine.
* I can document architecture, troubleshooting, cost and cleanup.

**What I would harden next**

* Private endpoints for ACR, Key Vault and state storage.
* GitHub Environments with approval gates.
* Stronger policy enforcement.
* Image signing or SBOM generation.
* More production-like network boundaries.

---

### L4 · [Azure Terraform Load Balanced Web Platform](https://github.com/KarimElAtfy/Azure-Terraform-Load-Balanced-Web-Platform)

This project moves from single-machine deployments to a more realistic web platform pattern.

It deploys a public Azure Load Balancer in front of private ARM64 Ubuntu backend VMs. The backend machines are provisioned with Nginx through cloud-init, administration goes through Bastion, and health probes decide whether traffic should reach each VM.

**Main technologies**

* Azure Load Balancer
* Backend pools
* Health probes
* Private backend VMs
* Azure Bastion
* NSGs
* Terraform
* cloud-init
* Nginx
* ARM64 Ubuntu

**What this project shows**

* I understand the basic shape of a load-balanced web platform.
* I can separate public entry points from private compute.
* I can use health probes and backend pools instead of manually pointing traffic to one VM.
* I can keep administrative access away from public SSH.
* I can automate VM provisioning consistently.

---

### L3 · [Azure Terraform Secure Private Platform](https://github.com/KarimElAtfy/Azure-Terraform-Secure-Private-Platform)

This project focuses on private-first infrastructure.

Instead of exposing a VM directly to the internet, it uses Azure Bastion for access and introduces platform components like Key Vault and Log Analytics. The goal was to stop treating "open SSH to the world" as the default and start thinking more like an infrastructure engineer.

**Main technologies**

* Azure Virtual Network
* Private Linux VM
* Azure Bastion
* Key Vault
* Log Analytics
* NSGs
* Terraform modules
* Remote state concepts

**What this project shows**

* I can design infrastructure where the VM does not need a public IP.
* I understand the role of Bastion for administrative access.
* I can add basic security and monitoring components around compute.
* I can structure Terraform in a cleaner, more reusable way.
* I am starting to think in terms of platform foundations, not only single resources.

---

### L2 · [Azure Terraform Secure Two-Tier Infrastructure](https://github.com/KarimElAtfy/Azure-Terraform-IaC-Secure-Two-Tier-Infrastructure)

This project introduces a more structured network layout.

It uses separate management and workload subnets, subnet-scoped NSGs, a dedicated admin VM and a web VM. It is still simple, but it moves beyond the "one VM in one subnet" pattern.

**Main technologies**

* Azure Virtual Network
* Subnets
* NSGs
* Management VM
* Web VM
* Terraform
* cloud-init
* Linux

**What this project shows**

* I can split infrastructure into different network areas.
* I understand the difference between management access and workload access.
* I can provision multiple VMs with different purposes.
* I can use NSG rules more intentionally.
* I can keep the code understandable while adding complexity.

---

### L1 · [Azure Terraform Linux VM](https://github.com/KarimElAtfy/Azure-Terraform-IaC-LinuxVM)

This was my first clean Azure infrastructure project with Terraform.

It deploys a Linux VM with custom networking, NSG rules, SSH key access and automated Nginx provisioning through cloud-init. It is intentionally simple, because it is the base I used before moving into segmented networks, private access, load balancing and container deployment.

**Main technologies**

* Azure Linux VM
* Azure Virtual Network
* NSG rules
* SSH keys
* Terraform
* cloud-init
* Nginx

**What this project shows**

* I can provision basic Azure infrastructure with Terraform.
* I understand the minimum pieces needed to expose a simple Linux web server.
* I can automate first boot configuration.
* I can document a foundation project clearly enough to build on it later.

---

## Technical skills

### Cloud and infrastructure

* Azure Resource Groups
* Azure Virtual Networks and Subnets
* Network Security Groups
* Azure Virtual Machines
* Azure Bastion
* Azure Load Balancer
* Azure Container Registry
* Azure Container Apps
* Azure Key Vault
* Managed Identity
* Log Analytics
* Application Insights

### Infrastructure as Code

* Terraform
* Terraform modules
* variables and outputs
* remote state on Azure Storage
* environment separation
* repeatable deployment workflows
* infrastructure documentation

### DevOps and security

* Git and GitHub
* GitHub Actions
* CI/CD pipelines
* OIDC-based Azure authentication
* Docker image builds
* Checkov for Terraform scanning
* Trivy for container scanning
* deployment smoke tests
* least privilege thinking
* basic cloud security hardening

### Systems and networking

* Linux fundamentals
* SSH key-based access
* cloud-init automation
* Nginx provisioning
* subnetting fundamentals
* routing and switching concepts
* private access patterns
* basic troubleshooting

### Programming and scripting

* Python fundamentals
* FastAPI used in a containerized Azure deployment project
* PowerShell fundamentals
* Bash basics
* automation-oriented scripting

---

## Certifications and study

* Microsoft Certified: Azure Fundamentals AZ-900
* Preparing for Microsoft Azure Administrator AZ-104
* Studying networking fundamentals with CCNA-oriented material

I try not to study cloud services only in theory. When I learn a concept, I usually turn it into a small deployment and write down what worked, what broke and what I would improve.

---

## How I work

My usual project flow is:

1. build the simplest working version
2. make it repeatable with Terraform
3. add one realistic constraint
4. break something
5. debug it properly
6. document the fix
7. use the lesson in the next project

I care about documentation because infrastructure that only works in my head is not good infrastructure.

A project should explain:

* what it deploys
* why it is designed that way
* how to run it
* how to destroy it
* what the limitations are
* what should be improved in a more production-like setup

---

## Currently improving

Right now I am focusing on:

* Azure administration for AZ-104
* stronger Terraform structure
* Docker and container workflows
* CI/CD patterns with GitHub Actions
* Linux troubleshooting
* networking fundamentals
* cloud security basics
* monitoring and observability
* cleaner technical documentation

---

## Languages

* Italian: native
* English: advanced
* French: intermediate
* Spanish: learning
* German: learning
* Russian: learning

---

## Links

* Portfolio: [kaystack.dev](https://kaystack.dev)
* LinkedIn: [linkedin.com/in/karim-el-atfy](https://www.linkedin.com/in/karim-el-atfy)

---
