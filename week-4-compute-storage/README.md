# Week 3: Compute & Storage Operations in Azure

## 1. Project Overview
This module focuses on deploying and managing Azure compute and storage resources. The objective was to gain hands-on experience provisioning virtual machines, configuring Azure storage services, and applying operational best practices for availability, security, and cost efficiency.

The labs in this week simulate common administrative tasks performed by cloud and infrastructure teams when supporting production workloads.

---

## 2. Operational Rationale
Compute and storage are core building blocks of any cloud environment. Poor configuration can lead to performance issues, data exposure, and unnecessary costs. This module emphasizes correct provisioning, secure access, and operational validation of these critical resources.

Key goals included:
- Deploying and managing Azure virtual machines
- Understanding Azure storage types and use cases
- Applying access controls and monitoring
- Practicing responsible lifecycle and cost management

---

## 3. Implemented Azure Capabilities

### A. Azure Virtual Machines (Compute)
- Virtual Machine Deployment: Provisioned Azure virtual machines using approved VM sizes available within regional and subscription constraints.
- OS & Resource Configuration: Configured VM settings including region selection, disk options, and networking integration.
- Availability Awareness: Evaluated VM sizing, region availability, and cost trade-offs during deployment.
- Secure Access: Used NSGs and Azure-native access methods to limit exposure.

---

### B. Azure Storage Services
- Storage Account Configuration: Deployed Azure Storage Accounts with appropriate performance and redundancy options.
- Storage Services: Worked with Blob containers and file shares to understand common cloud storage use cases.
- Access Control: Reviewed storage access keys and Azure RBAC integration.
- Data Protection Awareness: Evaluated storage-level security settings and access patterns.

---

### C. Monitoring & Operational Validation
- Resource Health Checks: Verified VM and storage resource states post-deployment.
- Metrics Review: Observed basic metrics such as availability and activity logs.
- Operational Validation: Ensured deployed resources behaved as expected before cleanup.

---

## 4. Operational Metrics

- Compute Deployment:
  - Virtual machines successfully deployed and validated
  - VM sizes adjusted based on regional availability and quota limitations

- Storage Configuration:
  - Storage accounts deployed with correct redundancy and access settings
  - Blob containers and file shares validated for accessibility

- Security & Access:
  - No public exposure beyond required lab access
  - Access reviewed using Azure-native tools

- Cost Control:
  - All compute and storage resources deleted after validation
  - No long-running or idle workloads left active

---

## 5. Key Outcomes
- Developed practical experience managing Azure virtual machines
- Gained foundational knowledge of Azure storage services and configurations
- Improved understanding of cost, availability, and region-based constraints
- Strengthened operational discipline around provisioning and cleanup

---



## 7. Cleanup & Cost Management
- Virtual machines were stopped and deleted after validation
- Storage accounts and associated containers were removed
- Resource groups were reviewed to ensure no orphaned resources remained

This approach reinforces good cloud hygiene and cost-awareness when working in Azure environments.

---

## 8. Key Takeaways
- Virtual machines require careful sizing, region selection, and access control
- Azure Storage provides flexible options for different workload needs
- Operational validation is essential before considering a deployment complete
- Responsible resource cleanup is a critical cloud administration skill

