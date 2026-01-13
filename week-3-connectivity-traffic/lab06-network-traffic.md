# Lab 06 – Implement Network Traffic Management (Azure)

## Overview
This lab focuses on implementing **Layer 4** and **Layer 7** traffic management in Azure using **Azure Load Balancer** and **Azure Application Gateway**. The goal is to distribute incoming public traffic across virtual machines and route requests based on URL paths.

---

## Objectives
- Deploy infrastructure using an ARM template
- Configure a public Azure Load Balancer
- Configure an Azure Application Gateway
- Validate load balancing and path-based routing

---

## Azure Services Used
- Azure Virtual Network
- Azure Virtual Machines
- Azure Load Balancer (Standard SKU)
- Azure Application Gateway (Standard V2)
- Network Security Groups

---

## Task 1 – Deploy Infrastructure Using ARM Template

### Steps
1. Sign in to the Azure Portal  
   https://portal.azure.com
2. Search for **Deploy a custom template**
3. Select **Build your own template in the editor**
4. Click **Load file** and upload:
   - az104-06-vms-template.json
5. Click **Save**
6. Select **Edit parameters** and load:
   - az104-06-vms-parameters.json
5. Click **Save**
6. Select **Edit parameters** and load:
7. Click **Save**
8. Complete the deployment details:
- Subscription: Your Azure subscription
- Resource group: `az104-rg6`
- Password: Secure password
- VM size: Any available size with at least **2 vCPUs**
9. Select **Review + create**
10. Select **Create**

### Result
- One virtual network
- Three subnets
- Three virtual machines (one per subnet)

---

## Task 2 – Configure Azure Load Balancer

### Create Load Balancer
- Name: `az104-lb`
- Resource group: `az104-rg6`
- Region: Same as deployed VMs
- SKU: Standard
- Type: Public
- Tier: Regional

---

### Frontend IP Configuration
- Name: `az104-fe`
- IP type: IP address
- Public IP: Create new

**Public IP settings**
- Name: `az104-lbpip`
- SKU: Standard
- Assignment: Static
- Routing preference: Microsoft network

---

### Backend Pool
- Name: `az104-be`
- Virtual network: `az104-06-vnet1`
- Backend configuration: NIC
- Virtual machines:
- `az104-06-vm0`
- `az104-06-vm1`

---

### Load Balancing Rule
- Name: `az104-lbrule`
- Protocol: TCP
- Frontend port: 80
- Backend port: 80
- Frontend IP: `az104-fe`
- Backend pool: `az104-be`

**Health Probe**
- Name: `az104-hp`
- Protocol: TCP
- Port: 80
- Interval: 5 seconds

---

### Validation
1. Copy the Load Balancer public IP
2. Open a browser and navigate to:
  ``` - http://<public-ip> ```
3. Refresh the page multiple times

Expected result:
- Alternates between:
- `Hello World from az104-06-vm0`
- `Hello World from az104-06-vm1`

---

## Task 3 – Configure Azure Application Gateway

### Create Application Gateway Subnet
- Virtual network: `az104-06-vnet1`
- Subnet name: `subnet-appgw`
- Address range: `10.60.3.224/27`

> Application Gateway requires a dedicated subnet of **/27 or larger**

---

### Create Application Gateway

**Basics**
- Name: `az104-appgw`
- Resource group: `az104-rg6`
- Tier: Standard V2
- Instance count: 2
- HTTP2: Disabled
- Virtual network: `az104-06-vnet1`
- Subnet: `subnet-appgw`

---

### Frontend
- Frontend IP type: Public
- Public IP name: `az104-gwpip`
- Availability zone: 1

---

### Backend Pools
**Default backend**
- Name: `az104-appgwbe`
- Virtual machines:
- `az104-06-nic1`
- `az104-06-nic2`

**Images backend**
- Name: `az104-imagebe`
- Virtual machine: `az104-06-nic1`

**Videos backend**
- Name: `az104-videobe`
- Virtual machine: `az104-06-nic2`

---

### Routing Rule (Path-Based Routing)
- Rule name: `az104-gwrule`
- Listener name: `az104-listener`
- Protocol: HTTP
- Port: 80

**Path rules**
- `/image/*` → `az104-imagebe`
- `/video/*` → `az104-videobe`

---

### Validation
1. Open **Backend health**
- Ensure all backends show **Healthy**

2. Copy the Application Gateway public IP

3. Test in browser:
  - http://<appgw-ip>/image/
  - http://<appgw-ip>/video/
   
Expected result:
- `/image/` routes to image VM
- `/video/` routes to video VM

---

## Cleanup
To avoid unnecessary charges, delete the resource group:
```bash
az group delete --name az104-rg6 
```
---

### Validation
- Azure Load Balancer operates at Layer 4 (TCP/UDP)
- Azure Application Gateway operates at Layer 7 (HTTP/HTTPS)
- Load Balancer is ideal for high-performance network traffic
- Application Gateway supports path-based routing and advanced web traffic management
