# Week 2: Resource Lifecycle Management & Operational Efficiency

## 1. Project Overview
This module focuses on managing Azure resources efficiently across their lifecycle. The objective was to gain hands-on experience with infrastructure deployment, networking configuration, and operational validation using Azure-native tools and Infrastructure as Code (IaC).

The labs in this week emphasize practical Azure administration skills required for maintaining scalable, organized, and cost-aware cloud environments.

---

## 2. Operational Rationale
Effective cloud environments depend on consistent resource deployment, proper network segmentation, and controlled lifecycle management. Without structured provisioning and cleanup processes, environments can quickly become costly, insecure, and difficult to manage.

This module supports operational best practices by:
- Using Infrastructure as Code to ensure repeatable deployments
- Designing isolated and functional virtual networks
- Validating connectivity and network security behavior
- Practicing disciplined resource cleanup to control cloud spend

---

## 3. Implemented Azure Capabilities

### A. Infrastructure as Code (ARM Templates)
- Template-Based Deployment: Deployed Azure resources using ARM templates to ensure consistent and repeatable provisioning.
- Parameterization: Used parameter files to separate configuration from deployment logic.
- Resource Standardization: Validated naming conventions and dependency relationships within templates.

---

### B. Virtual Networking
- Virtual Network Design: Created virtual networks with multiple subnets to simulate real-world segmentation.
- Network Security Groups (NSGs): Applied inbound and outbound rules to control traffic flow between subnets and virtual machines.
- System Routing Validation: Verified default system routes and next-hop behavior using Azure Network Watcher.

---

### C. Connectivity & Network Validation
- Network Watcher Diagnostics:  
  - Connectivity checks  
  - NSG diagnostics  
  - Next hop analysis  
  - Port scanning  

- Traffic Validation: Confirmed expected traffic behavior based on NSG rules, including intentional deny scenarios to validate security controls.

---

## 4. Operational Metrics

- Deployment Consistency:  
  - 100% of infrastructure deployed via ARM templates  
  - Zero manual configuration drift observed during validation  

- Network Segmentation:  
  - Multiple subnets successfully isolated using NSGs  
  - East-west traffic controlled as designed  

- Connectivity Validation:  
  - Network Watcher diagnostics used to validate all VM-to-VM paths  
  - Misconfigurations identified and corrected through testing  

- Cost Control:  
  - All lab resources decommissioned after validation  
  - No persistent idle resources left running  

---

## 5. Key Outcomes
- Gained hands-on experience deploying Azure resources using Infrastructure as Code  
- Developed practical understanding of Azure virtual networking and NSGs  
- Learned to validate and troubleshoot network connectivity using Azure-native tools  
- Improved operational discipline around resource lifecycle and cost management  

---


## 7. Cleanup & Cost Management
- All virtual machines, networks, and supporting resources were deleted after lab completion
- Resource groups were reviewed to ensure no orphaned resources remained
- Demonstrated awareness of operational cost management in Azure environments

---

## 8. Key Takeaways
- Infrastructure as Code improves consistency, repeatability, and operational reliability  
- Proper network design and validation are critical for secure and scalable deployments  
- Azure Network Watcher is an essential tool for troubleshooting connectivity issues  
- Effective resource lifecycle management helps reduce cost and operational risk  



