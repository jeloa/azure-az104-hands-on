# Week 5: Platform Services & Data Protection

## 1. Project Overview
This module focuses on deploying and securing Azure Platform-as-a-Service (PaaS) workloads and implementing foundational data protection strategies. The objective was to understand how Azure abstracts infrastructure management while still requiring strong security, monitoring, and data protection controls.

The labs cover web applications, container-based services, and backup strategies commonly used in production cloud environments.

---

## 2. Cloud & Security Rationale
PaaS services reduce operational overhead but do not remove security responsibility. Under the Shared Responsibility Model, customers remain responsible for identity, data protection, access control, and monitoring.

This module emphasizes:
- Secure deployment of managed application platforms
- Container-based workload execution without cluster management
- Protection of business-critical data against accidental deletion or failure

---

## 3. Implemented Azure Services & Controls

### A. Web Applications (Azure App Service)
- App Service Deployment: Deployed a web application using Azure App Service to evaluate managed hosting capabilities.
- Platform Abstraction: Observed how Azure handles OS patching, scaling, and availability.
- Secure Access: Verified application access through platform-provided endpoints.
- Operational Awareness: Reviewed configuration settings relevant to security and reliability.

---

### B. Containerized Workloads (Azure Container Instances & Container Apps)

#### Azure Container Instances (ACI)
- Container Deployment: Deployed containerized applications without managing virtual machines.
- On-Demand Execution: Evaluated ACI for lightweight, short-lived workloads.
- Resource Isolation: Observed container-level isolation and execution behavior.

#### Azure Container Apps (ACA)
- Managed Container Platform: Deployed a container app using a managed Kubernetes-based environment.
- Application Exposure: Verified external access through Azure-provided DNS endpoints.
- Simplified Orchestration: Evaluated scaling and platform-managed infrastructure features.
- Operational Validation: Confirmed successful deployment through application testing.

---

### C. Data Protection & Backup
- Azure Backup: Configured backup protection for supported workloads.
- Recovery Awareness: Reviewed recovery points and restore options.
- Data Resilience: Ensured workloads could be recovered from accidental deletion or failure.
- Cost-Conscious Design: Evaluated retention settings to balance protection and cost.

---

## 4. Operational Metrics

- PaaS Deployment:
  - Successful deployment of managed web applications
  - No infrastructure-level configuration required

- Container Workloads:
  - 100% successful container deployments across ACI and ACA
  - Verified external access to containerized applications

- Data Protection:
  - Backup protection enabled for target resources
  - Recovery points successfully created and validated

- Security Posture:
  - Reduced attack surface through platform-managed services
  - Clear separation of infrastructure and application responsibilities

---

## 5. Key Outcomes
- Gained hands-on experience with Azure PaaS offerings
- Understood differences between VM-based and PaaS-based deployments
- Learned practical use cases for ACI vs Azure Container Apps
- Implemented foundational data protection strategies using Azure Backup


---

## 7. Cleanup & Cost Management
- Deleted App Services and container resources after validation
- Reviewed backup configurations to avoid unnecessary retention
- Removed the resource group to minimize ongoing costs

---

## 8. Key Takeaways
- PaaS services simplify operations but still require security oversight
- Containers can be deployed without managing servers or clusters
- Azure Container Apps provide scalable, managed container environments
- Data protection is a critical component of cloud reliability and resilience




