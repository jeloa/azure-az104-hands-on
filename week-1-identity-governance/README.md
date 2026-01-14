# Week 1: Identity Governance & Zero Trust Architecture

---
## 1. Project Overview
This module demonstrates the implementation of foundational Cloud Security principles within a Microsoft Azure environment. The objective was to design a secure governance framework using Microsoft Entra ID (formerly Azure AD) and Azure Policy to enforce the Principle of Least Privilege (PoLP) and regional compliance. 

# 2. Security Rationale
In modern cybersecurity, identity is the primary control plane. This lab implements a Zero Trust approach ("never trust, always verify") by: 
Segmenting administrative duties via granular Role-Based Access Control (RBAC).
Automating compliance via Azure Policy to prevent "Shadow IT" (unauthorized resource deployment).
Adhering to controls found in industry standards like NIST 800-53. 

# 3. Implemented Security Controls
 A. Identity Management (Microsoft Entra ID)
User & Group Architecture: Structured administrative accounts into functional security groups (SecOps-Admins, Net-Audit-Team) to allow for efficient, group-based access management.
Centralized Identity: Used Microsoft Entra ID to centralize identity management, preparing for future Multi-Factor Authentication (MFA) enforcement. 

 B. Governance & Compliance (Azure Policy)
Data Residency Enforcement: Deployed a policy to restrict resource deployment to the Southeast Asia region, ensuring alignment with potential local data residency laws.
Cost & Resource Guardrails: Implemented policies to "Deny" the deployment of high-cost VM SKUs, mitigating risk from accidental over-provisioning.
Resource Tagging: Mandated Environment and Department tags for all resources to ensure 100% visibility during security audits and cost allocation (FinOps best practice). 

 C. Role-Based Access Control (RBAC)
Custom Role Scoping: Applied Virtual Machine Contributor at the Resource Group level rather than the Subscription level to limit potential lateral movement within the infrastructure.
Audit Access: Granted Reader roles to a simulated compliance team, ensuring necessary visibility for monitoring without the ability to modify security configurations. 
