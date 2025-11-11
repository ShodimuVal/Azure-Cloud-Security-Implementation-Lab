# Azure-Cloud-Security-Implementation-Lab

##  Description
This project was completed as part of my **D485 Cloud Security Final Assessment**.  
I was allotted **4 hours** to complete the lab, but successfully finished it in **2 hours**.  
The lab demonstrates applied cloud security skills in a hybrid Azure environment, aligned to compliance and business continuity requirements. It was one of my favorite assignments in my degree. 

---

##  Objective
A hands-on lab completed in a Windows 11 VM using the Azure portal to implement:
- Role-Based Access Control (RBAC)
- Key Vault protections
- Azure Policy guardrails
- Encryption safeguards
- Resource tagging for compliance
- VM backup configurations aligned to business RPO/RTO targets

Goal: Secure and segment a hybrid Azure environment for **SWBTL LLC** while meeting compliance requirements.

---

##  Skills Learned
- Designing hybrid cloud security architectures (IaaS + PaaS)
- Implementing least-privilege access with RBAC
- Hardening Azure Key Vault with purge protection and soft delete
- Applying Azure Policy for compliance guardrails
- Configuring VM backup policies aligned to business continuity targets
- Using tags for auditability and compliance reporting
- Mapping controls to frameworks (FISMA, PCI DSS, NIST SP 800-53)

---

## 🛠️ Tools Used
- **Azure Portal** (Windows 11 VM)
- **Azure RBAC**
- **Azure Key Vault**
- **Azure Policy**
- **Azure Backup**
- **Privileged Identity Management (PIM)**

---

##  Steps
1. **Resource Group Segmentation**  
   - Created separate RGs for Marketing, Accounting, and IT.  
   - Applied RBAC with scoped roles (Network Contributor, Reader).  
   - Used PIM for timebound assignments.

2. **Key Vault Access Controls**  
   - Restricted management to admins.  
   - Reader access granted cross-team only where needed.  
   - Enforced PoLP to reduce secret exposure.

3. **Azure Policy Guardrails**  
   - Applied “Allowed locations for resource groups” policy.  
   - Prevented RG creation/moves outside approved regions.

4. **Encryption Safety**  
   - Enabled Soft Delete and Purge Protection on all Key Vaults.  
   - Recommended TLS 1.2+ and automated key rotation.

5. **Tagging for Auditability**  
   - Tagged resources by department, location, and subscription.  
   - Improved compliance reporting and inventory hygiene.

6. **VM Backup & Recovery Policy**  
   - Configured daily backups at 7 PM with 45-day retention.  
   - Instant restore snapshots retained for 3 days.  
   - Validated backup pre-checks (Accounting VM passed under vault965).

---

##  Architecture & Compliance Context
- **Service Model:** Hybrid approach combining IaaS (VMs, OS management) and PaaS (managed services and guardrails).  
- **Compliance Baseline:** FISMA, PCI DSS, NIST SP 800-53.  
- **Business Continuity Targets:**  
  - RPO: 1 day  
  - RTO: 36 hours  
  - Backups: Daily at 7 PM; 45-day retention; instant recovery snapshots for 3 days  

---

##  Shared Responsibility & Risks
- **Azure:** Datacenter/infrastructure, host/network security, compliance frameworks.  
- **Customer (SWBTL LLC):** Data encryption, IAM/RBAC, backup/recovery, application/OS configs.  
- **Joint:** Network configuration, OS management, continuous compliance monitoring.  

**High-Impact Risks:**  
- Misconfigured encryption → data exposure.  
- RBAC gaps → privilege escalation.  

**Mitigations:**  
- PoLP + MFA across identities.  
- Azure Policy guardrails.  
- Automated patching.  
- TLS 1.2+ and automated key rotation.

---

##  Results
- **Segmentation achieved:** Department isolation via RGs and scoped RBAC.  
- **Data protection strengthened:** KV purge protection enabled; encryption controls documented.  
- **Operational resilience improved:** Backup schedules enforced with retention windows and instant restore.  
- **Auditability enhanced:** Tags applied for department, location, and subscription alignment.
