# 🧩 Phase 2 – Azure AD Connect: Sync On-Prem AD with Microsoft Entra ID

📚 **Table of Contents**
- [Overview](#overview)
- [Objectives](#objectives)
- [Key Concepts Reinforced](#key-concepts-reinforced)
- [Lab Environment & Tools](#lab-environment--tools)
- [Tasks Performed](#tasks-performed)
- [Outcome Summary](#outcome-summary)
- [Business Relevance](#business-relevance)
- [Screenshots](#screenshots)
- [Acknowledgments](#acknowledgments)

---

## 📖 Overview

I decided to give a more step by step view of this phase. I took screenshots every step of the way to document how AI breaks down objectives and lab instructions. This phase establishes hybrid identity by installing Microsoft Entra Connect Sync on a Windows Server 2022 domain controller and enabling synchronization between the on-premises Active Directory and Microsoft Entra ID. It also implements scoped OU filtering and password writeback, aligning with real-world Tier 1 practices.

---

## 🎯 Objectives

- Install and configure Microsoft Entra Connect Sync
- Enable Password Hash Synchronization
- Configure OU-level sync filtering
- Enable password writeback to on-prem AD
- Validate successful synchronization
- Prepare environment for Conditional Access and Tier 2+ enhancements

---

## 🧠 Key Concepts Reinforced

| Concept                     | Description |
|----------------------------|-------------|
| Hybrid Identity            | Bridging on-prem AD with Microsoft Entra ID (formerly Azure AD) |
| Entra Connect Sync         | Tool used to sync AD objects from on-prem to Entra |
| OU Filtering               | Syncing only selected Organizational Units for tighter control |
| Password Hash Sync         | Hashes of passwords are synced to Entra for authentication |
| Password Writeback         | Enables password resets in the cloud to update on-prem AD |
| Source Anchor              | The immutable ID used to link objects between systems |

---

## 🧪 Lab Environment & Tools

- **Platform**: Microsoft Azure
- **VM**: Windows Server 2022 Datacenter (HybridLab-DC)
- **Directory**: `corp.hybridlab.local`
- **Microsoft Entra ID tenant**: `micoocopergmail.onmicrosoft.com`
- **Tools Used**:
  - Entra Admin Center (`entra.microsoft.com`)
  - Azure AD Connect Sync (Entra Connect Sync Agent)
  - PowerShell
  - Server Manager / ADUC

---

## 🔨 Tasks Performed

1. Installed Entra Connect Sync via the Entra Admin Center
2. Selected **Customize** installation
3. Enabled **Password Hash Synchronization**
4. Authenticated to Entra with Global Admin
5. Connected to on-prem forest `corp.hybridlab.local` using `labadmin`
6. Granted `labadmin` membership to **Enterprise Admins**
7. Configured **OU Filtering** to sync only specific organizational units
8. Enabled **Password Writeback**
9. Completed initial sync and confirmed success
10. Validated user presence in Entra via portal

---

## ✅ Outcome Summary

- Entra Connect Sync configured successfully
- Sync initiated and completed with zero errors
- `labadmin` user and selected OU users appeared in Microsoft Entra ID
- Password Writeback enabled for SSPR testing
- Foundation now in place for Conditional Access and Tier 2+ policy labs

---

## 🏢 Business Relevance

- Demonstrates real-world hybrid identity integration used by enterprises
- Shows ability to scope sync securely using OU filtering
- Enables password policies across cloud and on-prem environments
- Builds operational readiness for downstream IT workflows (PIM, MFA, audits)
- Reinforces knowledge aligned with SC-300 and hybrid IAM job roles

---

## 📸 Screenshots

### 01 – Network Discovery  
![Network Discovery](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/01-network-discovery.png)  
Verifying network discovery settings on the server before configuring Entra Connect.

### 02 – Server Manager Azure Arc Prompt  
![Server Manager Azure Arc Prompt](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/02-server-manager-azure-arc-prompt.png)  
Initial Azure Arc prompt in Server Manager on the domain controller.

### 03 – Download Center PDF Error  
![Download Center PDF Error](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/03-download-centre-pdf-error.png)  
Error encountered while accessing the Microsoft Download Center for Entra Connect.

### 04 – Entra Connect Deprecation Notice  
![Entra Connect Deprecation Notice](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/04-entra-connect-deprecation-notice.png)  
Notification about the deprecation of Azure AD Connect and transition to Entra Connect.

### 05 – Azure VM Overview (HybridLab-DC)  
![Azure VM Overview](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/05-azure-vm-overview-hybridlab-dc.png)  
Azure portal overview of the HybridLab-DC virtual machine.

### 06 – Microsoft Login MFA Code  
![Microsoft Login MFA](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/06-microsoft-login-mfa-code.png)  
Multi-Factor Authentication (MFA) challenge during Microsoft login.

### 07 – Entra Admin Center Dashboard  
![Entra Admin Dashboard](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/07-entra-admin-center-dashboard.png)  
Landing page of the Microsoft Entra admin center.

### 08 – Entra Connect Sync Not Installed  
![Entra Connect Not Installed](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/08-entra-connect-sync-not-installed.png)  
Confirmation that Entra Connect Sync was not yet installed.

### 09 – Entra Connect Setup Failed  
![Entra Connect Setup Failed](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/09-entra-connect-setup-failed.png)  
An installation attempt of Entra Connect that failed.

### 10 – Entra Connect Install Required Components  
![Install Required Components](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/10-entra-connect-install-required-components.png)  
Installing prerequisites and required components for Entra Connect Sync.

### 11 – Entra Connect Internet Explorer Block  
![IE Block](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/11-entra-connect-internet-explorer-block.png)  
Setup blocked due to Internet Explorer Enhanced Security Configuration.

### 12 – Server Manager Local Server Settings  
![Server Manager Local Settings](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/12-server-manager-local-server-settings.png)  
Reviewing Local Server settings in Server Manager.

### 13 – Disable IE ESC for Entra Setup  
![Disable IE ESC](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/13-disable-ie-esc-for-entra-setup.png)  
Turning off Internet Explorer Enhanced Security Configuration for setup to proceed.

### 14 – Entra Connect Sync Sign-in  
![Entra Connect Sign-in](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/14-entra-connect-sync-signin.png)  
Signing into Entra Connect with Microsoft account.

### 15 – Entra Connect Sync Add Directory  
![Add Directory](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/15-entra-connect-sync-add-directory.png)  
Adding on-premises Active Directory forest into Entra Connect.

### 16 – Enterprise Admin Error  
![Enterprise Admin Error](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/16-entra-connect-sync-enterprise-admin-error.png)  
Error indicating the provided account was not a member of the Enterprise Admins group.

### 17 – Active Directory Labadmin Properties  
![Labadmin Properties](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/17-active-directory-labadmin-properties.png)  
Labadmin account properties in Active Directory Users and Computers.

### 18 – Directory Added  
![Directory Added](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/18-entra-connect-directory-added.png)  
Successful addition of the on-premises directory in Entra Connect.

### 19 – OU Filtering  
![OU Filtering](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/19-entra-connect-ou-filtering.png)  
Configuring domain and OU filtering for synchronization.

### 20 – OU Selection  
![OU Selection](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/20-entra-connect-ou-selection.png)  
Selecting the `Users` OU for synchronization to Entra ID.

### 21 – Identify Users  
![Identify Users](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/21-entra-connect-identify-users.png)  
Defining how users are uniquely identified during synchronization.

### 22 – Filter Users  
![Filter Users](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/22-entra-connect-filter-users.png)  
Optional filtering of users and devices for synchronization.

### 23 – Ready to Configure  
![Ready to Configure](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/23-entra-connect-ready-to-configure.png)  
Final review before starting the configuration process.

### 24 – Configuration Complete  
![Configuration Complete](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/24-entra-connect-configuration-complete.png)  
Successful completion of Microsoft Entra Connect Sync setup.

### 25 – Entra Portal Labadmin Synced  
![Labadmin Synced in Entra](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/raw/main/Phase%202%20%E2%80%93%20Azure%20AD%20Connect%3A%20Sync%20On-Prem%20AD%20with%20Microsoft%20Entra%20ID/screenshots/25-entra-portal-labadmin-synced.png)  
Screenshot from the Entra admin center confirming the `labadmin` account synced successfully.

---

## 🙏 Acknowledgments

Thanks to Microsoft for the robust tools that make identity infrastructure manageable and extensible. Special acknowledgment to AI-powered tools for supporting documentation accuracy and helping streamline the verification process.

- [Microsoft Learn – Hybrid Identity with Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/hybrid/)
- [Download Microsoft Entra Connect Sync Agent](https://entra.microsoft.com)
- Hybrid Identity Lab design inspired by enterprise IT architectures and SC-300 certification prep
