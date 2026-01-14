# Week 3: Network Connectivity & Traffic Management

## 1. Project Overview
This module focuses on Azure networking fundamentals related to intersite connectivity and traffic control. The objective was to understand how resources communicate within and across virtual networks, and how Azure-native tools enforce secure and predictable network traffic flows.

The labs simulate real-world networking scenarios commonly encountered by cloud administrators and security teams when designing and validating secure cloud environments.

---

## 2. Networking & Security Rationale
Network connectivity is a critical control plane in cloud environments. Misconfigured routing, open network paths, or weak traffic filtering can expose workloads to unauthorized access.

This module emphasizes:
- Controlled network communication between Azure resources
- Visibility into traffic flow and routing decisions
- Defense-in-depth using layered network security controls

---

## 3. Implemented Azure Networking Capabilities

### A. Intersite Connectivity
- Virtual Network Design: Reviewed and worked with multiple Azure virtual networks to understand isolation boundaries.
- Connectivity Validation: Tested connectivity paths between virtual machines across network segments.
- Routing Awareness: Observed system routes and how Azure determines next-hop behavior for inter-VM traffic.
- Network Dependency Mapping: Evaluated how subnet and network placement affects reachability.

---

### B. Network Traffic Control
- Network Security Groups (NSGs): Applied inbound and outbound NSG rules to control permitted traffic between workloads.
- Least Privilege Networking: Allowed only required ports and protocols while explicitly denying unnecessary traffic.
- Directional Filtering: Differentiated inbound vs outbound traffic rules and validated their impact.
- Rule Evaluation Order: Observed priority-based rule processing and its effect on traffic flow.

---

### C. Traffic Visibility & Diagnostics
- Azure Network Watcher: Used Network Watcher tools to test and validate network connectivity.
- Connectivity Checks: Performed connection tests between source and destination virtual machines.
- NSG Diagnostics: Identified NSG rules blocking traffic during failed connectivity tests.
- Next Hop Analysis: Verified routing paths and confirmed system route usage.
- Port Scanning: Evaluated port accessibility to validate security posture.

---

## 4. Operational Metrics

- Connectivity Testing:
  - Successful identification of blocked and permitted traffic paths
  - 100% correlation between NSG rules and connectivity test results

- Traffic Control:
  - All non-essential traffic effectively denied
  - Required traffic explicitly allowed through NSG configuration

- Diagnostics & Visibility:
  - Network Watcher successfully used to diagnose connectivity failures
  - Clear attribution of failures to specific NSG rules

- Security Posture:
  - No unintended lateral movement between network segments
  - Defense-in-depth applied at the network layer

---

## 5. Key Outcomes
- Strengthened understanding of Azure virtual network communication
- Gained hands-on experience diagnosing network connectivity issues
- Learned to interpret Network Watcher diagnostic outputs
- Applied least privilege principles at the network level

---




## 7. Cleanup & Cost Management
- Virtual machines used for connectivity testing were deleted after validation
- Network resources were reviewed to ensure no unused components remained
- Resource groups were removed to prevent unnecessary costs

---

## 8. Key Takeaways
- Network connectivity must be explicitly designed and validated
- NSGs are a foundational control for restricting traffic in Azure
- Network Watcher provides critical visibility into traffic flow and failures
- Secure cloud networking relies on continuous validation and monitoring


