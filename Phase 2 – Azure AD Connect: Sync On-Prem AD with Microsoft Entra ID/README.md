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

## 🖼️ Screenshots

| Screenshot | Description |
|-----------|-------------|
| `entra-connect-not-installed.png` | Starting from Entra Admin Center before install |
| `download-connect-sync-agent.png` | Downloading the proper agent from the portal |
| `customize-install.png` | Choosing advanced configuration instead of Express setup |
| `ou-filtering.png` | Scoping sync to specific Organizational Units |
| `sync-complete.png` | Final successful configuration summary |
| `entra-user-labadmin.png` | Confirmed synced user from on-prem AD in Entra ID |

> _[Insert raw GitHub image links or embed screenshots from your `/screenshots/` folder here in the actual repo]_

---

## 🙏 Acknowledgments

Thanks to Microsoft for the robust tools that make identity infrastructure manageable and extensible. Special acknowledgment to AI-powered tools for supporting documentation accuracy and helping streamline the verification process.

- [Microsoft Learn – Hybrid Identity with Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/hybrid/)
- [Download Microsoft Entra Connect Sync Agent](https://entra.microsoft.com)
- Hybrid Identity Lab design inspired by enterprise IT architectures and SC-300 certification prep
