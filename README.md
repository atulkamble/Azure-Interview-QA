# 🎯 **Azure + DevOps Theory Questions and Answers (2025 Edition)**

## **SECTION 1 — Azure Fundamentals (Theory Q&A)**

### **1. What is Microsoft Azure?**

**Answer:**
Azure is a cloud computing platform offering services across compute, networking, storage, databases, AI, DevOps, security, and more. It supports IaaS, PaaS, and SaaS models.

---

### **2. What is the difference between Azure Subscription and Azure Tenant?**

**Answer:**

* **Tenant** = Entra ID Authentication boundary (Identity).
* **Subscription** = Billing + Resource boundary.
  One tenant can contain multiple subscriptions.

---

### **3. What is Azure Resource Manager (ARM)?**

**Answer:**
Azure Resource Manager (ARM) is the deployment and management layer for Azure resources.
Features include:

* Role-based access control (RBAC)
* ARM templates / Bicep
* Consistent REST API
* Tagging and resource grouping

---

### **4. What are Azure Regions and Availability Zones?**

**Answer:**

* **Regions:** Geo locations where Azure datacenters exist.
* **AZs:** Separate datacenters within a region providing fault isolation.
  Provide **99.99%** uptime when used with zone-redundant architecture.

---

### **5. What is the difference between Availability Set vs Availability Zone?**

| Feature             | Availability Set | Availability Zone     |
| ------------------- | ---------------- | --------------------- |
| Fault domain        | Yes              | Yes                   |
| Update domain       | Yes              | No                    |
| Physical separation | Same datacenter  | Different datacenters |
| SLA                 | 99.95%           | 99.99%                |

---

## **SECTION 2 — Azure Compute (Theory Q&A)**

### **6. What is the difference between VM Scale Sets and Availability Sets?**

**Answer:**

* **VMSS** provides auto-scaling + automated load-balancing.
* **AS** only provides fault/update domain protection.

---

### **7. What is Azure App Service?**

**Answer:**
A fully managed hosting platform for web apps, APIs, and mobile apps with features like:

* Auto-scaling
* CI/CD integration
* Deployment slots
* Built-in authentication

---

### **8. What are Deployment Slots in App Service?**

**Answer:**
Separate environments (e.g., staging, production) within the same App Service.
Benefits:

* Zero-downtime swap
* Warm-up
* Testing environment before going live

---

### **9. What is Azure Function?**

**Answer:**
A serverless compute platform where you only pay per execution. Supports triggers like HTTP, Timer, Event Grid, Queue.

---

### **10. What is Azure Container Instances (ACI)?**

**Answer:**
A lightweight, serverless container hosting system—no orchestration, fast startup.

---

## **SECTION 3 — AKS (Azure Kubernetes Service) Theory Q&A**

### **11. What is AKS?**

**Answer:**
Managed Kubernetes service that automates:

* Control plane management
* Upgrades
* Auto-healing
* Monitoring

---

### **12. Difference between System Node Pool and User Node Pool in AKS?**

| System Node Pool                                     | User Node Pool             |
| ---------------------------------------------------- | -------------------------- |
| Runs critical services like CoreDNS, Kube-proxy, CNI | Runs application workloads |
| Must use Linux                                       | Can use Linux or Windows   |
| Must be small and stable                             | Can scale as needed        |

---

### **13. What is CNI vs Kubenet?**

* **Kubenet:** Simpler, NAT-based, not fully routable.
* **Azure CNI:** Each pod gets an IP, better visibility, supports advanced networking.

---

### **14. How does AKS integrate with ACR?**

Using:

* Managed Identity
* `az aks update --attach-acr`
  Allows AKS to pull private images.

---

## **SECTION 4 — Azure Networking Theory Q&A**

### **15. What is a VNet?**

Azure’s private network space enabling:

* Subnets
* NSGs
* Routing
* Peering
* VPN Gateways
* Private Links

---

### **16. What is NSG?**

Network Security Group = stateful firewall controlling inbound/outbound traffic.

---

### **17. What is Azure Firewall?**

Managed, scalable firewall with:

* Threat intelligence
* SNAT
* Central policy
* Logging integration

---

### **18. Difference between VNet Peering and VPN Gateway?**

| VNet Peering             | VPN Gateway             |
| ------------------------ | ----------------------- |
| Low latency              | Higher latency          |
| No encryption            | Encrypted               |
| Same or different region | Supports hybrid/on-prem |

---

### **19. What is Private Endpoint?**

A network interface that connects to Azure services privately over VNet, securing:

* KV
* Blob
* SQL
* ACR
* Web Apps

---

### **20. What is Azure Load Balancer vs Application Gateway?**

| Azure Load Balancer | Application Gateway |
| ------------------- | ------------------- |
| Layer 4             | Layer 7             |
| TCP/UDP             | HTTP/HTTPS          |
| No WAF              | WAF enabled         |
| Health probes       | URL-based routing   |

---

## **SECTION 5 — Azure Storage & Databases Theory Q&A**

### **21. What is Azure Storage Account?**

A container for services: Blob, File, Queue, Table.

---

### **22. What is the difference between Blob Hot vs Cool vs Archive?**

| Tier    | Purpose         | Availability | Cost       |
| ------- | --------------- | ------------ | ---------- |
| Hot     | Frequent access | High         | Expensive  |
| Cool    | Infrequent      | Medium       | Lower cost |
| Archive | Rare            | Offline      | Very cheap |

---

### **23. What is Azure SQL DTU vs vCore model?**

* **DTU:** Combined CPU + memory + IO in a bundle
* **vCore:** Independent scaling (CPU/memory) and flexible pricing

---

## **SECTION 6 — Identity & Security (Theory Q&A)**

### **24. What is Azure RBAC?**

Role-based access control—assign roles to users/groups/managed identities.

---

### **25. Difference between RBAC and Access Policies (Key Vault)?**

* **RBAC:** Modern authorization system.
* **Access Policies:** Legacy method; still required for some scenarios.

---

### **26. What is Managed Identity?**

Identity assigned to Azure services that allows them to authenticate without secrets.

Types:

* System-assigned
* User-assigned

---

### **27. What is Conditional Access?**

Enforces identity conditions such as MFA, device compliance, locations.

---

### **28. What is Azure Defender?**

Security threat protection solution for Azure workloads.

---

## **SECTION 7 — DevOps Theory Q&A (Core Concepts)**

### **29. What are the main stages of DevOps lifecycle?**

* Plan
* Code
* Build
* Test
* Release
* Deploy
* Monitor
* Operate

---

### **30. What is GitOps?**

A methodology where Git is the single source of truth for infrastructure and deployments. Tools: Flux, ArgoCD.

---

### **31. Difference between CI and CD?**

* **CI:** Build + Test automation after every commit
* **CD:** Automatic deployment to test/prod

---

### **32. What is Infrastructure as Code (IaC)?**

Automating infrastructure provisioning using declarative code (Terraform, Bicep, ARM).

---

### **33. Terraform vs ARM vs Bicep?**

| Tool      | Type           | Pros                            |
| --------- | -------------- | ------------------------------- |
| Terraform | Multi-cloud    | Modular, plan/apply, state mgmt |
| ARM       | JSON templates | Native but verbose              |
| Bicep     | DSL for ARM    | Simple, clean, modern           |

---

### **34. What is a Terraform State File?**

Stores current infrastructure details.
State is needed for:

* Tracking changes
* Detecting drift
* Planning updates

---

### **35. What is Git Rebase vs Git Merge?**

* **Merge:** Adds a new commit combining branches.
* **Rebase:** Rewrites commit history for cleaner linear structure.

---

### **36. What is Artifact Feed?**

Storage for packages: npm, Maven, NuGet, Python.

---

## **SECTION 8 — CI/CD Theory Q&A (Azure DevOps, GitHub Actions)**

### **37. What are Hosted Agents vs Self-Hosted Agents?**

* **Hosted:** Microsoft-managed; good for general workloads.
* **Self-hosted:** Used for custom tools, private networks, large builds.

---

### **38. What are Stages, Jobs, and Tasks in Azure Pipelines?**

* **Stage:** Major division (Build, Test, Deploy).
* **Job:** A collection of tasks.
* **Task:** Individual build/deploy unit.

---

### **39. What are Release Pipelines?**

Classic UI-based deployments used for multi-environment manual approvals.

---

### **40. Difference between GitHub Actions and Azure DevOps?**

| Feature   | GitHub Actions  | Azure DevOps                   |
| --------- | --------------- | ------------------------------ |
| Best for  | Open-source, CI | Enterprises, full DevOps suite |
| Boards    | No              | Yes                            |
| Repos     | GitHub only     | Azure Repos + GitHub           |
| Templates | YAML            | YAML + Classic                 |

---

## **SECTION 9 — Monitoring & SRE Theory Q&A**

### **41. What is Azure Monitor?**

Unified monitoring platform supporting:

* Logs
* Metrics
* Alerts
* Dashboards

---

### **42. What is Log Analytics Workspace?**

Central repository for storing logs using Kusto Query Language (KQL).

---

### **43. What is an SLO?**

Service Level Objective — measurable reliability target (e.g., 99.9% availability).

---

### **44. What is Error Budget?**

Allowance for downtime/error within an SLO period.

---

### **45. What is Distributed Tracing?**

Tracking requests across microservices to identify bottlenecks.

---

## **SECTION 10 — Containers & Microservices Theory Q&A**

### **46. What is a Container Image vs Container?**

* **Image:** Template
* **Container:** Running instance of image

---

### **47. What is Dockerfile?**

Instructions to build an image.

---

### **48. What is a Helm Chart?**

Package manager for Kubernetes applications.
Includes templates for:

* Deployments
* Services
* ConfigMaps
* Values.yaml

---

### **49. What is Service Mesh?**

Dedicated infrastructure layer handling:

* Observability
* Traffic routing
* Encryption
  Tools: Istio, Linkerd, Open Service Mesh.

---

### **50. What is ACR Build Task?**

Automated image builds triggered by Git commits or base image updates.

---
