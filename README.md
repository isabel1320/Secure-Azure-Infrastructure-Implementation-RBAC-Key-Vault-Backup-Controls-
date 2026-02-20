# Secure-Azure-Infrastructure-Implementation-RBAC-Key-Vault-Backup-Controls-
Secured a Microsoft Azure IaaS environment by implementing least-privilege RBAC, segmented Key Vault access, encryption controls, and automated backup policies aligned with NIST SP 800-53 and PCI DSS requirements.

## Overview

This project demonstrates the remediation and hardening of a Microsoft Azure Infrastructure-as-a-Service (IaaS) environment following the discovery of multiple security misconfigurations.

The environment simulated a regulated organization subject to FISMA and PCI DSS requirements. A post-deployment review identified excessive access permissions, weak encryption boundaries, inconsistent backup enforcement, and insufficient governance controls.

To address these risks, I implemented least-privilege RBAC scoping, department-based Key Vault segmentation, encryption best practices, automated backup policies, and governance enforcement mechanisms aligned with NIST SP 800-53 control families.

#### Note: This project was completed in a controlled lab environment simulating a regulated financial organization operating within a Microsoft Azure IaaS architecture.
---

## Objectives

- Enforce least privilege using Azure RBAC  
- Segment encryption boundaries with dedicated Key Vaults  
- Implement compliant backup and retention policies  
- Strengthen governance through resource tagging and policy enforcement  
- Align controls with NIST SP 800-53, PCI DSS, and FISMA objectives  

---

## Technologies & Azure Services Used

- Microsoft Azure (IaaS)
- Azure Virtual Machines
- Microsoft Entra ID (Azure AD)
- Azure Role-Based Access Control (RBAC)
- Azure Key Vault
- Azure Backup / Recovery Services Vault
- Azure Policy
- Resource Tagging
- TLS/SSL Certificate Management

---

## Identified Security Risks

Initial assessment revealed:

- Overly permissive cross-department RBAC assignments  
- Shared Key Vault access across business units  
- Missing or misaligned backup policies  
- Virtual machines placed in incorrect resource groups  
- Unmanaged disk configuration preventing backup enforcement  
- Lack of tagging for governance and audit visibility  

These misconfigurations increased risk of:

- Privilege escalation  
- Lateral movement  
- Data exposure  
- Regulatory noncompliance  
- Data loss due to backup failure  

---

## Security Controls Implemented

### RBAC Hardening

- Scoped Contributor roles at the Resource Group level  
- Removed cross-department access  
- Cleaned inherited permissions  
- Enforced least privilege access model  

**Impact:** Reduced lateral movement and privilege escalation risk.

---

### Key Vault Segmentation & Encryption Controls

- Created dedicated Key Vault per department  
- Restricted access policies by role and scope  
- Enforced encryption for data at rest  
- Configured TLS certificate management for secure data in transit  

**Impact:** Isolated encryption boundaries and strengthened compliance posture.

---

### Backup & Disaster Recovery Configuration

- Configured daily backup policy (7:00 PM EST)  
- 24-hour Recovery Point Objective (RPO)  
- 45-day retention period  
- 3-day instant restore snapshots  
- Resolved unmanaged disk issues preventing backup enforcement  

**Impact:** Improved disaster recovery readiness and compliance alignment.

---

### Governance & Policy Enforcement

- Implemented department-based resource tagging  
- Enabled Azure Policy for compliance enforcement  
- Improved audit filtering and resource visibility  

**Impact:** Strengthened cloud governance and long-term security posture management.

---

## Security Improvements Summary

| Control Area | Before | After |
|--------------|--------|--------|
| RBAC | Cross-department access | Scoped at Resource Group level |
| Key Vault | Shared access | Segmented per department |
| Encryption | Unverified | Key Vault-managed controls |
| Backup | Inconsistent | Automated daily policy |
| Governance | No tagging | Enforced tagging standards |

---

## Lessons Learned

- RBAC scope and inheritance must be tightly controlled to prevent privilege creep.  
- Encryption boundaries should reflect organizational segmentation.  
- Backup enforcement depends on correct disk configuration (managed vs. unmanaged).  
- Governance controls (tagging + policy) are critical for scalable cloud security.  
- Misconfigurations introduced by third parties require structured review and remediation.  

---

## Architecture

A simplified architecture diagram illustrating RBAC scoping, Key Vault segmentation, and backup enforcement is included in this repository.

---
