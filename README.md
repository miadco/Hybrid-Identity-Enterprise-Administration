# 🎩 Hybrid Identity Enterprise Administration Lab  

## 📌 Overview  
This repository documents a full **Hybrid Identity deployment lab** simulating how enterprises integrate on-premises Active Directory with **Microsoft Entra ID** (formerly Azure AD).  
The project follows a **multi-phase structure**, starting with the deployment of a Windows Server 2022 domain controller in Azure, continuing through **Azure AD Connect setup, OU filtering, password writeback, and validation**.  

The goal is to showcase **hands-on identity administration skills** aligned with **SC-300 (Microsoft Identity & Access Administrator)** and real-world IAM job functions.  

---

## 🎯 Objectives  
- Deploy and configure a domain controller in Microsoft Azure  
- Establish hybrid identity with Microsoft Entra Connect Sync  
- Implement scoped OU filtering for secure synchronization  
- Enable password hash sync and password writeback  
- Validate synchronization and hybrid identity functionality  
- Document the entire workflow with **step-by-step READMEs and screenshots**  

---

## 🧠 Key Concepts Reinforced  
| Concept | Description |  
|---------|-------------|  
| **Hybrid Identity** | Bridging on-prem AD DS with Microsoft Entra ID |  
| **Domain Controller** | Core authentication/authorization server for AD |  
| **OU Filtering** | Scoping synchronization to specific organizational units |  
| **Password Hash Sync** | Cloud authentication using synced password hashes |  
| **Password Writeback** | Allows password resets in Entra to flow back to AD |  
| **Conditional Access Readiness** | Foundation for enforcing MFA, device compliance, and policies |  

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
- ✅ Password hash synchronization and writeback enabled  
- ✅ Users successfully synced and validated in Entra  

---

## 💼 Business Relevance  
This lab demonstrates the **foundational building blocks** of hybrid identity, which many organizations still rely on as they transition to the cloud. By setting up a domain controller, configuring Microsoft Entra Connect, scoping synchronization with OU filtering, and enabling password hash synchronization with writeback, the project replicates the **core tasks of an IAM or cloud support role**.  

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

