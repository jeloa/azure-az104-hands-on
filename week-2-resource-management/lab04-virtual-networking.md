# Lab 03 – Manage Azure Resources Using ARM Templates

## Objective
- Design and deploy virtual networks with scalable IP addressing

- Automate virtual network deployment using ARM templates

- Control network traffic using NSGs and ASGs

- Configure public and private DNS zones in Azure

---

## Scenario
Your global organization plans to implement virtual networks. The immediate goal is to accommodate all the existing resources. However, the organization is in a growth phase and wants to ensure there is additional capacity for the growth.

---

## Tools & Services Used
- Azure Resource Manager (ARM) Templates (JSON)
- Azure Bicep
- Azure Cloud Shell
- Azure PowerShell
- Azure CLI
- Managed Disks

---

## Tasks Performed

### 1. Created Virtual Network and Subnets Using Azure Portal
- Created a managed disk named `az104-disk1` in the resource group `az104-rg3`
- Configured disk settings:
  - Region: East US
  - Performance: Standard HDD
  - Size: 32 GiB
- Exported the deployed disk as an ARM template
- Reviewed the generated `template.json` and `parameters.json` files
- Downloaded and extracted the template files for reuse

---

### 2. Modified and Redeployed an ARM Template
- Uploaded the exported ARM template to the **Custom deployment** editor
- Modified template parameters to:
  - Rename disk parameter to `disk_name`
  - Change disk name to `az104-disk2`
- Updated the parameters file to match template changes
- Redeployed the template to the same resource group
- Verified that a second managed disk was successfully created
- Reviewed deployment history and inputs in the resource group

---

### 3. Deployed ARM Template Using Azure PowerShell
- Configured Azure Cloud Shell with PowerShell
- Mounted a Cloud Shell storage account
- Uploaded ARM template and parameters files
- Edited the template to deploy `az104-disk3`
- Deployed the template using PowerShell:
