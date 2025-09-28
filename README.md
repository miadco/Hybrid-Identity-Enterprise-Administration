# 🎩 Hybrid Identity Enterprise Administration Lab  

## 📌 Overview  
This repository captures a step-by-step **Hybrid Identity Lab** that demonstrates how to extend an on-premises Active Directory Domain Services (AD DS) environment into **Microsoft Entra ID** (formerly Azure AD).  

The lab begins with deploying a Windows Server 2022 virtual machine in Microsoft Azure, configuring it as a domain controller, and verifying its health. It then walks through installing and configuring **Microsoft Entra Connect Sync**, applying **OU filtering** to scope synchronization, enabling **Password Hash Synchronization**, and validating that on-premises accounts successfully appear in Microsoft Entra ID.  

By documenting each stage with screenshots and clear explanations, this project shows the **core foundations of hybrid identity administration** used in real-world enterprise environments.    

---

## 🎯 Objectives  
- Deploy a Windows Server 2022 VM in Microsoft Azure  
- Connect to the server remotely via RDP and prepare it for role installation  
- Install and configure Active Directory Domain Services (AD DS)  
- Promote the server to a domain controller and create the corp.hybridlab.local forest  
- Verify domain controller health using PowerShell and `dcdiag`  
- Install and configure Microsoft Entra Connect Sync  
- Scope synchronization with OU filtering (HybridLabUsers OU)  
- Enable Password Hash Synchronization  
- Validate that on-prem users successfully synced into Microsoft Entra ID  
  

---

## 🧠 Key Concepts Reinforced  
| Concept | Description |  
|---------|-------------|  
| **Domain Controller (DC)** | A Windows Server promoted to manage Active Directory Domain Services (AD DS), serving as the on-premises identity source. |  
| **Active Directory Domain Services (AD DS)** | Provides centralized identity and authentication for users, groups, and devices within the corp.hybridlab.local forest. |  
| **Hybrid Identity** | Extending on-prem AD DS identities into Microsoft Entra ID to enable a unified identity model. |  
| **Microsoft Entra Connect Sync** | The tool used to synchronize on-prem AD objects (users, groups) into Microsoft Entra ID. |  
| **OU Filtering** | Restricting synchronization to a specific Organizational Unit (HybridLabUsers) for security and least privilege. |  
| **Password Hash Synchronization** | Syncing password hashes from AD DS to Microsoft Entra ID so users can authenticate in the cloud. |  
| **Verification & Health Checks** | Using tools like `dcdiag`, PowerShell, and the Entra Admin Center to confirm sync success and AD DS health. |  

  

---

## 🧪 Lab Environment & Tools  
- **Platform**: Microsoft Azure  
- **OS**: Windows Server 2022 Datacenter (Gen2)  
- **Directory**: corp.hybridlab.local  
- **Cloud Tenant**: Microsoft Entra ID (micoocopergmail.onmicrosoft.com)  
- **Tools Used**:  
  - Azure Portal  
  - Microsoft Entra Admin Center  
  - Azure AD Connect (Entra Connect Sync)  
  - Active Directory Users & Computers (ADUC)  
  - PowerShell  

---

## 🗂 Project Structure & Phases  
Each phase has its own README with detailed tasks and screenshots.  

- **[Phase 1: Deploy Domain Controller](./Phase%201%20Step%204%3A%20Verify%20Domain%20Controller%20Functionality/README.md)**  
  Provision Windows Server 2022 in Azure, configure RDP, promote to a domain controller, and verify AD DS health.  

- **[Phase 2: Azure AD Connect Setup](./Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/README.md)**  
  Install and configure Azure AD Connect, enable password hash sync & writeback, scope OU filtering, and validate initial sync.  

- **[Phase 3: Hybrid Identity Verification & OU Filtering](./Phase%203%20%E2%80%93%20Hybrid%20Identity%20Verification%20%26%20OU%20Filtering/README.md)**  
  Confirm synchronization in Microsoft Entra ID, refine OU filtering, validate object presence, and confirm labadmin sync.  

---

## 📈 Outcomes Summary  
- ✅ Fully functional domain controller in Azure  
- ✅ Hybrid identity established with Entra Connect Sync  
- ✅ OU filtering configured for least privilege sync  
- ✅ Password hash synchronization enabled  
- ✅ Users successfully synced and validated in Entra  

---

## 💼 Business Relevance  
This lab demonstrates the **foundational building blocks** of hybrid identity, which many organizations still rely on as they transition to the cloud. By setting up a domain controller, configuring Microsoft Entra Connect, scoping synchronization with OU filtering replicates the **core tasks of an IAM or cloud support role**.  

These skills directly support:  
- Managing identity lifecycles across on-premises and cloud environments  
- Enabling secure account synchronization for hybrid workforces  
- Preparing the environment for downstream enhancements like MFA, Conditional Access, and governance controls   
  

---


## 🙏 Acknowledgments  
- Microsoft Learn – [Hybrid Identity & Entra ID](https://learn.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)  
- SC-300 & AZ-104 official lab guides  
- Azure Documentation & Community resources  
- AI-Supported Documentation: This lab’s planning, structure, and step-by-step documentation were enhanced with the assistance of **ChatGPT (OpenAI)** to ensure clarity, accuracy, and professional presentation.

