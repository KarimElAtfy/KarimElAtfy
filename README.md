# Hi, I'm Karim

**Cloud & DevOps Engineer** at **Dev4Side Software**, a Microsoft consultancy in Milan, in the Infrastructure & Security team.

I work on live enterprise Azure environments: I bring them under **Bicep**, deploy them through gated **Azure DevOps** pipelines, automate **Entra ID** with PowerShell and Microsoft Graph, and look for where the money goes. My default is read-only first, what-if before every change and decisions backed by data.

This GitHub is my public lab. Client work stays under NDA; the projects here are where I rebuild the same patterns in the open with **Terraform, AKS, GitOps and GitHub Actions**, and document what broke.

[kaystack.dev](https://kaystack.dev) · [LinkedIn](https://www.linkedin.com/in/karim-el-atfy) · [CV](https://kaystack.dev/Karim-El-Atfy-CV.pdf)

---

## At work

Enterprise clients in luxury, pharmaceutical and food distribution. Names and code stay private; the outcomes don't have to.

| What | Result |
| --- | --- |
| Entra ID app registration export to Dynatrace (Azure Automation, Graph) | **In production.** API permissions of ~1,500 apps visible to the client's security team |
| CI/CD lifecycle redesign for a shared Azure DevOps template | **In production.** Draft / Candidate / Released flow across ~50 MuleSoft repositories |
| Bicep baseline of a brownfield Azure estate | 55 live resources, 25+ types, validated with **zero unintended changes** in What-If |
| Five-stage IaC pipeline | Validate → What-If → Approval → Deploy → post-deploy What-If, least-privilege identities |
| FinOps review across 14 subscriptions | ~€33k/year in reservations, right-sizing and decommissioning identified |
| Entra ID guest lifecycle automation | Bicep + Azure DevOps with workload identity federation: **no secrets anywhere** |
| AI agent platform on Azure | Platform HLD and LLD: landing zone, private networking, identity, FinOps |

Case studies: [Azure IaC baseline](https://kaystack.dev/work/azure-iac-baseline) · [MuleSoft release lifecycle](https://kaystack.dev/work/mulesoft-release-lifecycle) · [FlowLedger](https://kaystack.dev/work/flowledger)

---

## Public lab

A progression: each project adds one major infrastructure concept on top of the previous one.

| Level | Project | What it adds |
| --- | --- | --- |
| L6 | [AKS GitOps Secure Platform](https://github.com/KarimElAtfy/Azure-Terraform-AKS-GitOps-Secure-Platform) | AKS, Flux v2, Helm, Workload Identity, Key Vault CSI, NetworkPolicy |
| L5 | [DevSecOps Container Platform](https://github.com/KarimElAtfy/Azure-Terraform-DevSecOps-Container-Platform) | Container Apps, ACR, OIDC deploys, Checkov, Trivy, smoke tests |
| L4 | [Load Balanced Web Platform](https://github.com/KarimElAtfy/Azure-Terraform-Load-Balanced-Web-Platform) | Load Balancer, health probes, private ARM64 backends |
| L3 | [Secure Private Platform](https://github.com/KarimElAtfy/Azure-Terraform-Secure-Private-Platform) | Bastion, no public IPs, Key Vault, Log Analytics |
| L2 | [Secure Two-Tier Infrastructure](https://github.com/KarimElAtfy/Azure-Terraform-IaC-Secure-Two-Tier-Infrastructure) | Management and workload subnets, scoped NSGs |
| L1 | [Azure Terraform Linux VM](https://github.com/KarimElAtfy/Azure-Terraform-IaC-LinuxVM) | First clean VM with Terraform and cloud-init |

### Featured: AKS GitOps Secure Platform

The full chain, end to end:

```text
Terraform → AKS + ACR + Key Vault
GitHub Actions (OIDC, no stored secrets) → build → scan → push to ACR → bump image tag in Git
Flux → reconcile → Helm release → pod with Key Vault secret mounted via Workload Identity
```

**A real incident from it.** A RollingUpdate on a single-node dev cluster could not schedule the new pod while the old one was still running. Helm timed out and rolled back. The fix was a configurable deployment strategy in the chart, with `Recreate` for the cost-conscious dev environment. It's documented because scheduling, resources and rollout strategy interacting is exactly what happens in real clusters.

**Next hardening:** private AKS, private endpoints for ACR and Key Vault, controlled egress, managed Prometheus and Grafana, Kyverno, Flux image automation, staging and production environments.

---

## Stack

**Azure:** App Service · Functions · API Management · Event Hubs · Storage · SQL / SQL MI · Redis · AKS · Container Apps · ACR · Private Endpoints · VNets · Bastion · Load Balancer · Automation · Policy · Monitor

**Identity & security:** Entra ID (app registrations, RBAC, Conditional Access, B2B, Cross-Tenant Sync) · Managed Identity · Workload Identity Federation · Key Vault · least privilege

**IaC & automation:** Bicep · Terraform · ARM · What-If · PowerShell 7 (Pester) · Microsoft Graph · Azure CLI · Python · Bash · cloud-init

**CI/CD & DevSecOps:** Azure DevOps (YAML templates, environments, approvals) · GitHub Actions · GitLab CI · Jenkins · Gitleaks · Trivy · Checkov

**Containers:** Docker · Kubernetes · Helm · Flux

**Observability & FinOps:** Log Analytics · KQL · Resource Graph · Application Insights · Dynatrace · Prometheus · Grafana · Cost Management · Reservations

---

## How I work

1. **Read before writing.** Inventory and evidence first; a live environment is never assumed.
2. **What-if before every change.** Zero unintended creates, modifies or deletes, or it doesn't ship.
3. **No secrets.** OIDC, managed identities, federation.
4. **Measure before fixing.** Sometimes the right answer is "no change, here's the data".
5. **Document the limits.** What it deploys, how to validate it, how to destroy it and what it doesn't do yet.

---

## Learning

- ✅ Microsoft Certified: Azure Fundamentals (AZ-900)
- 🎯 AZ-104 Azure Administrator → AZ-400 DevOps Engineer Expert → AZ-305 Solutions Architect Expert
- 🌐 Networking with CCNA material
- 🎓 Computer Engineering, Politecnico di Milano

**Languages:** Italian (native) · English (C1) · French (B1) · German (beginner) · Swiss German (learning) · Russian (beginner)
