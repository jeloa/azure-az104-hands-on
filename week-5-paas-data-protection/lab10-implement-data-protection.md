# Lab 10 – Implement Data Protection

## Lab Introduction
In this lab, you learn how to implement backup, recovery, and disaster recovery for Azure virtual machines. You create Recovery Services vaults, configure VM-level backups, monitor backup jobs, and enable virtual machine replication using Azure Site Recovery.


---

## Lab Scenario
Your organization is evaluating solutions to protect Azure virtual machines from accidental or malicious data loss. In addition, the organization wants to implement disaster recovery using Azure Site Recovery to ensure business continuity in case of a regional outage.

---

## Job Skills
- Provision infrastructure using an ARM template
- Create and configure Recovery Services vaults
- Configure Azure VM-level backup
- Monitor Azure Backup jobs and logs
- Enable virtual machine replication using Azure Site Recovery

---

## Task 1: Use a Template to Provision Infrastructure

An ARM template was used to deploy a virtual network and virtual machine for backup and recovery testing.

### Deployment Details
- Resource group: az104-rg-region1
- Region: East US
- Virtual machine: az-104-10-vm0
- Username: localadmin
- Password: Complex password (secure)

The template deployment completed successfully, creating:
- One virtual machine
- One virtual network

This virtual machine is used throughout the lab to test backup and disaster recovery features.

## Template deployed
![Template Deployed](screenshots/lab09c-create-container-app.jpg)

---

## Task 2: Create and Configure a Recovery Services Vault

A Recovery Services vault was created to store backup and replication data.

### Vault Configuration
- Vault name: az104-rsv-region1
- Resource group: az104-rg-region1
- Region: East US
- Storage replication: Geo-redundant (default)

### Security Settings
- Soft Delete: Enabled
- Retention period: 14 days

The vault was successfully deployed and configured with default security and replication settings.

---

## Task 3: Configure Azure Virtual Machine-Level Backup

Azure Backup was enabled for the virtual machine using a custom backup policy.

### Backup Policy Configuration
- Policy name: az104-backup
- Backup frequency: Daily
- Backup time: 12:00 AM
- Time zone: Local time zone
- Instant recovery snapshot retention: 2 days

The policy was created and assigned to:
- Virtual machine: az-104-10-vm0

### Backup Status
- Backup enabled successfully
- Initial backup status: Pending
- Manual backup triggered using **Backup now**

---

## Task 4: Monitor Azure Backup

A storage account was created and linked to the Recovery Services vault for logging and monitoring.

### Storage Account
- Resource group: az104-rg-region1
- Region: East US
- Purpose: Store backup logs and metrics

### Diagnostic Settings
The following logs and metrics were sent to the storage account:
- Azure Backup Reporting Data
- Azure Backup Job Data
- Azure Backup Alert Data
- Azure Site Recovery Jobs
- Azure Site Recovery Events

Backup job details were reviewed, confirming job execution and monitoring visibility.

---

## Task 5: Enable Virtual Machine Replication (Azure Site Recovery)

A second Recovery Services vault was created to enable disaster recovery replication.

### Secondary Vault
- Vault name: az104-rsv-region2
- Resource group: az104-rg-region2
- Region: West US

### Replication Configuration
- Source VM: az-104-10-vm0
- Target region: West US
- Automation account: Created automatically
- Replication status: Enabled

Initial synchronization began and replication health was verified as **Healthy** after completion.

---

## Key Takeaways
- Azure Backup provides secure and cost-effective backup for Azure and on-premises workloads
- Recovery Services vaults store and manage backup and replication data
- Backup policies define backup frequency and retention periods
- Azure Site Recovery enables disaster recovery across Azure regions
- VM replication allows quick failover with minimal downtime
- Monitoring and diagnostics improve visibility into backup and recovery operations

