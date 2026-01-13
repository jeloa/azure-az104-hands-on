# Lab 05 – Implement Intersite Connectivity

## Overview
This lab focuses on enabling communication between Azure virtual networks. It covers virtual network peering, connectivity testing using Network Watcher and Azure PowerShell, and traffic control using user-defined routes. This scenario reflects a common enterprise setup where core services and manufacturing workloads are logically separated but still require secure connectivity.

> **Note:** Due to Azure subscription vCPU quota and regional capacity limitations, virtual machine deployment options were restricted. All networking components and configurations were successfully implemented, and connectivity validation steps were completed where supported.

---

## Objectives
- Create virtual machines in separate virtual networks
- Test connectivity between virtual networks
- Configure virtual network peering
- Validate connectivity using Network Watcher and PowerShell
- Implement a custom route using a route table

---

## Task 1: Create Core Services Virtual Machine and Virtual Network

- Created a virtual machine named **CoreServicesVM**
- Created a new virtual network **CoreServicesVnet**
- Address space: `10.0.0.0/16`
- Subnet:
  - Name: `Core`
  - Address range: `10.0.0.0/24`
- Public inbound ports: **None**
- Boot diagnostics: **Disabled**

This task demonstrates creating a virtual network as part of the virtual machine deployment process.

![VNet Peering](images/lab05/lab05-core-services-vm-basics.jpg)

---

## Task 2: Create Manufacturing Virtual Machine and Virtual Network

- Created a virtual machine named **ManufacturingVM**
- Created a new virtual network **ManufacturingVnet**
- Address space: `172.16.0.0/16`
- Subnet:
  - Name: `Manufacturing`
  - Address range: `172.16.0.0/24`
- Public inbound ports: **None**
- Boot diagnostics: **Disabled**

This setup simulates a separate manufacturing environment isolated from core services.

![VNet Peering](images/lab05/lab05-manufacturing-vm-basics.jpg)

---

## Task 3: Test Connectivity Using Network Watcher

- Used **Network Watcher → Connection troubleshoot**
- Source VM: `CoreServicesVM`
- Destination VM: `ManufacturingVM`
- Protocol: TCP
- Destination port: `3389`

### Result
- Initial connectivity test returned **Unreachable**
- This behavior is expected because the virtual networks were not yet peered

![VNet Peering](images/lab05/lab05-network-watcher-unreachable.jpg)


---

## Task 4: Configure Virtual Network Peering

Configured bidirectional peering between the two virtual networks:

### CoreServicesVnet → ManufacturingVnet
- Allowed virtual network access
- Allowed forwarded traffic

### ManufacturingVnet → CoreServicesVnet
- Allowed virtual network access
- Allowed forwarded traffic

### Result
- Peering status: **Connected**
- Resources in both virtual networks can now communicate using private IP addresses

![VNet Peering](images/lab05/lab05-vnet-peering-connected.jpg)

---

## Task 5: Test Connectivity Using Azure PowerShell

- Retrieved the private IP address of **CoreServicesVM**
- Used **Run Command** on `ManufacturingVM`
- Executed the following PowerShell command:

```powershell
Test-NetConnection <CoreServicesVM-Private-IP> -Port 3389
```

--- 

### Result
- Connection test succeeded

![VNet Peering](images/lab05/lab05-test-netconnection-success.jpg)

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
  - Route name: PerimetertoCore
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

### Cleanup
To avoid unnecessary charges, the lab resource group can be deleted:

Azure Portal: Delete resource group

PowerShell: `` Remove-AzResourceGroup -Name az104-rg5 `` 

Azure CLI: ``az group delete --name az104-rg5``



