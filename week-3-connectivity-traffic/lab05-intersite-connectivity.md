# Lab 05 – Implement Intersite Connectivity

## Lab Overview
In this lab, I implemented communication between Azure virtual networks by deploying virtual machines in separate VNets, configuring virtual network peering, validating connectivity, and creating a custom user-defined route (UDR). This lab demonstrates a common enterprise networking scenario where isolated environments require controlled communication.

**Region:** East US  
**Estimated Time:** 50 minutes

---

## Lab Scenario
The organization separates core IT services from manufacturing workloads to improve security and management. However, applications across these environments must still communicate securely. This lab demonstrates how Azure virtual network peering and routing enable segmented yet connected network architectures.

---

## Skills Demonstrated
- Azure Virtual Networking
- Virtual Network Peering
- Azure Network Watcher
- Azure PowerShell Networking
- User-Defined Routes (UDR)
- Network Segmentation

---

## Task 1: Create a Core Services Virtual Machine and Virtual Network

### Actions Performed
- Created a virtual machine named **CoreServicesVM**
- Created a new virtual network during VM deployment:
  - **VNet:** CoreServicesVnet
  - **Address Space:** 10.0.0.0/16
  - **Subnet:** Core (10.0.0.0/24)
- Disabled boot diagnostics
- No public inbound ports were allowed

### Result
The core services virtual machine and virtual network were successfully deployed.

---

## Task 2: Create a Virtual Machine in a Different Virtual Network

### Actions Performed
- Created a virtual machine named **ManufacturingVM**
- Created a separate virtual network:
  - **VNet:** ManufacturingVnet
  - **Address Space:** 172.16.0.0/16
  - **Subnet:** Manufacturing (172.16.0.0/24)
- Disabled boot diagnostics
- No public inbound ports were allowed

### Result
The manufacturing virtual machine and virtual network were successfully deployed in an isolated environment.

---

## Task 3: Test Connectivity Using Network Watcher

### Actions Performed
- Used **Network Watcher → Connection troubleshoot**
- Tested TCP connectivity:
  - **Source:** CoreServicesVM
  - **Destination:** ManufacturingVM
  - **Port:** 3389 (RDP)

### Result
- **Connectivity Status:** Unreachable

### Explanation
This result was expected because virtual network peering had not yet been configured.

---

## Task 4: Configure Virtual Network Peering

### Actions Performed
- Created bidirectional virtual network peering between:
  - **CoreServicesVnet**
  - **ManufacturingVnet**
- Enabled:
  - Virtual network access
  - Forwarded traffic

### Result
- Peering status showed **Connected** on both virtual networks

---

## Task 5: Test Connectivity Using Azure PowerShell

### Actions Performed
- Retrieved the private IP address of **CoreServicesVM**
- Used **Run Command** on **ManufacturingVM**
- Executed the following PowerShell command:

```powershell
Test-NetConnection <CoreServicesVM-Private-IP> -Port 3389

--- 

### Result
- TestSucceeded: True

### Explanation
- The successful test confirmed that virtual network peering enabled private communication between the virtual machines.

---

## Task 6: Create a Custom Route (User-Defined Route)

### Actions Performed
- Added a new subnet:
  - Name: perimeter
  - Address Range: 10.0.1.0/24
- Created a route table:
  - Name: rt-CoreServices
  - Disabled gateway route propagation
- Added a custom route:
  - Destination: 10.0.0.0/16
  = Next Hop Type: Virtual appliance
  = Next Hop Address: 10.0.1.7
= Associated the route table with the Core subnet

### Result
- Traffic from the core subnet is now routed through the designated virtual appliance.

## Key Takeaways
- Virtual networks are isolated by default in Azure
- Virtual network peering enables secure inter-VNet communication
- Azure uses Microsoft backbone infrastructure for peered traffic
- User-defined routes provide granular control over network traffic
- Network Watcher is essential for diagnosing connectivity issues

---


