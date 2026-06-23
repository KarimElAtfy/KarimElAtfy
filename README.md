# Hi, I'm Karim

I'm a Computer Engineering student at Politecnico di Milano building a hands-on profile around **Azure, Linux, networking, Terraform, Kubernetes, GitOps and DevOps**.

I use GitHub as a public engineering lab: every project is built to prove a specific layer of infrastructure knowledge, from basic Azure VMs to container platforms, CI/CD, AKS, Flux, Helm and identity-based cloud authentication.

My goal is not to pretend that a personal lab is a production enterprise platform. My goal is to show that I can build, break, debug, document and improve real cloud infrastructure with the same mindset used in professional environments.

Portfolio: [kaystack.dev](https://kaystack.dev)

---

## What I'm looking for

I'm currently looking for junior roles or internships in areas such as:

* Junior Cloud Engineer
* Junior DevOps Engineer
* Junior Platform Engineer
* Cloud Operations
* Junior System Administrator
* Infrastructure Support
* Monitoring / NOC / Operations-focused roles
* IT Support roles with growth toward cloud and infrastructure

I am still early in my career, but I am not trying to stay at the "I watched a tutorial" level.

I am building projects that show operational thinking:

* infrastructure as code
* identity and access management
* networking boundaries
* containerization
* CI/CD
* GitOps
* Kubernetes troubleshooting
* documentation
* cost awareness
* security trade-offs
* honest limitations

---

## Current focus

Right now I am focused on becoming operational in:

* Azure administration and cloud infrastructure
* Terraform and Infrastructure as Code
* Linux administration and troubleshooting
* networking fundamentals
* Docker and container workflows
* Kubernetes and AKS
* Helm packaging
* Flux GitOps
* GitHub Actions CI/CD
* cloud security basics
* monitoring and observability
* technical documentation

I am preparing for **Microsoft Azure Administrator AZ-104** and strengthening my networking knowledge with CCNA-oriented material.

---

## Main project path

My Azure portfolio is built as a progression. Each project adds one major infrastructure concept on top of the previous one.

| Level | Project                        | Main idea                                                      |
| ----- | ------------------------------ | -------------------------------------------------------------- |
| L6    | AKS GitOps Secure Platform     | Kubernetes, AKS, Flux, Helm, Workload Identity, DevSecOps      |
| L5    | DevSecOps Container Platform   | Containers, Azure Container Apps, CI/CD, OIDC, security checks |
| L4    | Load Balanced Web Platform     | Load balancer, private backends, health probes                 |
| L3    | Secure Private Platform        | Bastion, private access, Key Vault, monitoring                 |
| L2    | Secure Two-Tier Infrastructure | Subnet separation, management VM, workload VM                  |
| L1    | Azure Terraform Linux VM       | First clean Azure VM deployment with Terraform                 |

---

## Featured projects

### L6 · [Azure Terraform AKS GitOps Secure Platform](https://github.com/KarimElAtfy/Azure-Terraform-AKS-GitOps-Secure-Platform)

This is currently my strongest and most complete project.

It provisions an Azure Kubernetes Service platform with Terraform, builds a FastAPI container image with GitHub Actions, pushes it to Azure Container Registry, and deploys it to AKS through Flux GitOps and Helm.

The project also includes GitHub Actions OIDC authentication to Azure, AKS Workload Identity, Azure Key Vault secret mounting through the Secrets Store CSI Driver, Kubernetes NetworkPolicy, Checkov, Trivy and full platform documentation.

This was not just a "deploy an app to Kubernetes" exercise. The goal was to build the full operational chain:

```text
Terraform infrastructure
→ AKS cluster
→ container image build
→ ACR push
→ GitOps image tag update
→ Flux reconciliation
→ Helm release
→ running pod
→ Key Vault secret mount
→ runtime validation
→ troubleshooting and documentation
```

**Main technologies**

* Azure Kubernetes Service
* Azure Container Registry
* Azure Key Vault
* AKS Workload Identity
* Secrets Store CSI Driver
* Log Analytics
* Terraform
* Kubernetes
* Helm
* Flux v2
* Docker
* FastAPI
* GitHub Actions
* GitHub Actions OIDC
* Checkov
* Trivy
* NetworkPolicy

**What this project shows**

* I can separate infrastructure provisioning from application delivery.
* I can use Terraform for Azure infrastructure and Flux for Kubernetes workloads.
* I understand why GitOps matters for cluster state management.
* I can package an application with Helm instead of manually applying YAML.
* I can use OIDC-based authentication instead of static Azure secrets.
* I can connect AKS workloads to Key Vault through Workload Identity.
* I can build a multi-step CI/CD flow around image build, registry push and deployment reconciliation.
* I can debug real Kubernetes rollout problems instead of only following happy-path tutorials.
* I can document architecture, deployment, security, observability, troubleshooting and cost cleanup.

**Real incident solved**

During testing, a RollingUpdate deployment failed on a small single-node AKS cluster.

The new pod could not be scheduled because the old pod was still running and the node did not have enough temporary capacity for both pods. The Helm release timed out and rolled back.

The fix was to make the Helm chart support configurable deployment strategies and use `Recreate` for the cost-conscious AKS dev environment.

That incident is documented because it shows the kind of operational problem that actually happens in Kubernetes: scheduling, resources, rollout strategy and deployment behavior all interact.

**What I would harden next**

* Private AKS cluster
* Private endpoints for ACR and Key Vault
* Azure Firewall or controlled egress
* managed Prometheus and Grafana
* policy enforcement with Kyverno or OPA Gatekeeper
* Flux Image Automation
* staging and production environments
* progressive delivery or canary rollouts

---

### L5 · [Azure Terraform DevSecOps Container Platform](https://github.com/KarimElAtfy/Azure-Terraform-DevSecOps-Container-Platform)

This project focuses on a complete container deployment workflow without managing Kubernetes directly.

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
* I can validate a deployment with smoke tests and logs.
* I can document architecture, troubleshooting, cost and cleanup.

**What I would harden next**

* Private endpoints for ACR, Key Vault and state storage
* GitHub Environments with approval gates
* stronger policy enforcement
* image signing or SBOM generation
* more production-like network boundaries

---

### L4 · [Azure Terraform Load Balanced Web Platform](https://github.com/KarimElAtfy/Azure-Terraform-Load-Balanced-Web-Platform)

This project moves from single-machine deployments to a more realistic web platform pattern.

It deploys a public Azure Load Balancer in front of private ARM64 Ubuntu backend VMs. The backend machines are provisioned with Nginx through cloud-init, administration goes through Bastion, and health probes decide whether traffic should reach each VM.

**Main technologies**

* Azure Load Balancer
* backend pools
* health probes
* private backend VMs
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
* private Linux VM
* Azure Bastion
* Key Vault
* Log Analytics
* NSGs
* Terraform modules
* remote state concepts

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
* subnets
* NSGs
* management VM
* web VM
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

It deploys a Linux VM with custom networking, NSG rules, SSH key access and automated Nginx provisioning through cloud-init. It is intentionally simple because it is the base I used before moving into segmented networks, private access, load balancing and container deployment.

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
* Azure Kubernetes Service
* Azure Key Vault
* Managed Identity
* AKS Workload Identity
* Log Analytics
* Application Insights

### Infrastructure as Code

* Terraform
* Terraform variables and outputs
* Terraform remote state on Azure Storage
* layered Terraform deployments
* environment-specific configuration
* repeatable deployment workflows
* infrastructure documentation
* cost-aware infrastructure cleanup

### Kubernetes and platform engineering

* Kubernetes workloads
* pods, deployments and services
* rollout strategies
* readiness and liveness probes
* Helm charts
* Helm values
* Flux GitOps
* GitRepository and HelmRelease
* Kubernetes NetworkPolicy
* Secrets Store CSI Driver
* AKS troubleshooting with `kubectl`, `helm` and `flux`

### DevOps and security

* Git and GitHub
* GitHub Actions
* CI/CD pipelines
* GitHub Actions OIDC
* Docker image builds
* Azure Container Registry workflows
* Checkov for IaC scanning
* Trivy for vulnerability, secret and misconfiguration scanning
* deployment smoke tests
* least privilege thinking
* cloud identity and secretless authentication

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
* FastAPI
* PowerShell
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

1. build the smallest version that works
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
* how to validate it
* how to destroy it
* what the limitations are
* what should be improved in a more production-like setup

---

## Currently improving

Right now I am improving:

* Azure administration for AZ-104
* Kubernetes and AKS operations
* Helm and Flux GitOps
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
