# Cloud Security Implementation Plan (Masters Project)

##  Description
This project focused on implementing a secure hybrid cloud environment using Microsoft Azure.  
It was my favorite project during my master's program because it combined compliance, encryption, RBAC, and backup strategies into a real-world scenario.

##  Objective
- Ensure regulatory compliance (FISMA, PCI DSS, NIST SP 800-53)  
- Implement secure role-based access control (RBAC)  
- Protect sensitive data with encryption and key vaults  
- Configure backups with strict RPO/RTO requirements  
- Apply shared responsibility principles between Azure and the organization  

##  Tools
- Microsoft Azure (RBAC, Key Vault, Recovery Vault, Policies)  
- Azure Backup & Recovery Services  
- Azure Policy for compliance enforcement  
- TLS encryption protocols  

##  Results
- RBAC misconfigurations corrected with least privilege enforcement  
- Key Vaults secured with purge protection and read-only access  
- Automated backups configured with instant recovery snapshots  
- Compliance maintained with federal and industry standards  
- Risks identified and mitigated through zero trust and continuous monitoring  

##  Skills Learned
- Cloud security architecture design  
- Regulatory compliance implementation  
- Encryption and key management  
- Backup and disaster recovery planning  
- Shared responsibility model in hybrid cloud environments  

##  Steps
1. **RBAC Configuration**  
   - Applied least privilege principles to Marketing, Accounting, and IT groups  
   - Segmented resource groups and enforced access policies  
   - <img width="600" height="718" alt="image" src="https://github.com/user-attachments/assets/d88739ed-242d-4698-afc0-f1ad4caff6ec" />
   - <img width="598" height="536" alt="image" src="https://github.com/user-attachments/assets/e9910a01-4740-4cb5-96ec-41e95e3b0e9d" />


2. **Granting Reading Access Only for Each Group's Key Vault**  
   - Configured Key Vaults with read-only access for non-admin users
   - <img width="317" height="562" alt="image" src="https://github.com/user-attachments/assets/34701759-b0b0-4435-88cb-4cd2f2c5081d" />
   - <img width="629" height="579" alt="image" src="https://github.com/user-attachments/assets/acd2c92b-db6d-4cf5-8052-a894e740e1d3" />



3. **Changing Azure Parameters by Assigning Policies in Relation to Each Group's Needs**  
   - Applied Azure Policy for allowed locations and compliance enforcement  
   - <img width="722" height="669" alt="image" src="https://github.com/user-attachments/assets/1dd276dc-16de-4220-9013-721e373fa4b5" />
   - <img width="647" height="1174" alt="image" src="https://github.com/user-attachments/assets/0a84db80-d300-4165-b410-894482dfebc8" />


4. **Encryption Implementation by Updating the Key Vault to Enable Purge Protection for Each Group**  
   - Enabled purge protection and soft-delete for all Key Vaults  
   - <img width="716" height="646" alt="image" src="https://github.com/user-attachments/assets/2c85ada1-7fc6-4623-9304-bf46e6bff86a" />
   - <img width="686" height="615" alt="image" src="https://github.com/user-attachments/assets/a183b596-ea9a-44b4-8780-498fc5a0e860" />
   - <img width="704" height="641" alt="image" src="https://github.com/user-attachments/assets/819c3eac-f226-4647-a3ce-5ababa9b2b65" />


5. **Created Tags to Identify Groups and Specific Locations During Compliance Tests**  
   - Assigned tags for resource tracking and compliance validation  
   - <img width="707" height="1230" alt="image" src="https://github.com/user-attachments/assets/2d9831c3-96bc-4ca5-b3b9-5b345e05b30a" />
   - <img width="756" height="690" alt="image" src="https://github.com/user-attachments/assets/5c960374-2fb8-4a2e-87c7-eb48876624fb" />



6. **Created Backups for Each Group**  
   - Configured daily backups at 7 PM with 45-day retention  
   - *Note:* Marketing VM backup failed due to time constraints, but Accounting and IT backups succeeded  
   - <img width="1179" height="1041" alt="image" src="https://github.com/user-attachments/assets/b76b5526-c5cc-4c81-aa4d-5c8453609e70" />
   - <img width="880" height="769" alt="image" src="https://github.com/user-attachments/assets/bf5ac9db-e977-4bfe-8b67-aa9f6072c9b8" />



7. **Backed Up Files Using a Recovery Vault**  
   - Ensured all VMs were protected with Recovery Vault policies  
   - *insert photo*

##  Architecture Compliance Context
- Compliance enforced with **FISMA**, **PCI DSS**, and **NIST SP 800-53**  
- Zero trust and least privilege principles applied  
- Continuous monitoring and auditing recommended  

##  Shared Responsibility and Risks
- **Azure Responsibilities:** Infrastructure, compliance updates, network/host security  
- **Organization Responsibilities:** IAM, encryption, backups, software configurations  
- **Shared Responsibilities:** OS management, monitoring, compliance enforcement  

### Risks
- Misconfiguration of RBAC → privilege escalation  
- Weak encryption protocols → data exploitation  
- Insufficient patch management → vulnerability to zero-day attacks  

##  Mitigations
- Enforce least privilege and zero trust  
- Apply automated patch management policies  
- Use TLS 1.2+ for data in transit  
- Rotate encryption keys regularly  
- Conduct regular compliance audits  
