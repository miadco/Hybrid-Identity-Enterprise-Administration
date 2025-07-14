# 🎩 Hybrid Identity Lab – Phase 1: Deploy Domain Controller in Azure (Windows Server 2022)

---

## 📚 Table of Contents

* [Overview](#overview)
* [Objectives](#objectives)
* [Key Concepts Reinforced](#key-concepts-reinforced)
* [Lab Environment & Tools](#lab-environment--tools)
* [Tasks Performed](#tasks-performed)
* [Outcome Summary](#outcome-summary)
* [Business Relevance](#business-relevance)
* [Screenshots](#screenshots)
* [Acknowledgments](#acknowledgments)

---

## 📌 Overview

In this phase, I deploy a Windows Server 2022 virtual machine in Microsoft Azure, which will serve as on-premises domain controller. This is the foundational step toward establishing a hybrid identity environment using Microsoft Entra ID. The VM will later be configured with Active Directory Domain Services (AD DS) and synced with the cloud using Azure AD Connect.

---

## 🎯 Objectives

* Provision a Windows Server 2022 VM using the Azure Portal
* Configure networking to allow secure RDP access
* Prepare the environment for domain promotion and AD Connect setup

---

## 🧠 Key Concepts Reinforced

| Concept                | Description                                                               |
| ---------------------- | ------------------------------------------------------------------------- |
| Microsoft Entra ID     | Cloud-based identity platform replacing Azure Active Directory (Azure AD) |
| Hybrid Identity        | Identity model bridging on-prem AD with Microsoft Entra ID                |
| Domain Controller (DC) | Central server managing Active Directory user accounts and authentication |
| RDP                    | Remote Desktop Protocol used to connect to the VM                         |
| Azure Portal           | GUI interface to manage and deploy Azure resources                        |

---

## 🧰 Lab Environment & Tools

* **Azure Portal** ([https://portal.azure.com](https://portal.azure.com))
* **Windows Server 2022 Datacenter – Azure Edition (Gen2)**
* **Remote Desktop Connection (RDP)**
* **Resource Group:** `HybridIdentityLab-RG`
* **Virtual Machine:** `HybridLab-DC`

---

## 🔧 Tasks Performed

1. Logged into the [Azure Portal](https://portal.azure.com)
2. Created a new VM using:

   * Windows Server 2022 Datacenter Gen2 image
   * Standard\_B1s size (upgraded to D2s\_v3)
   * Enabled RDP (port 3389) for remote access
3. Configured default networking and disk options
4. Deployed VM into new resource group: `HybridIdentityLab-RG`
5. Prepared VM for Active Directory Domain Services installation in the next phase

---

## 📈 Outcome Summary

A secure and accessible Windows Server 2022 VM named `HybridLab-DC` was successfully deployed in Azure. This VM will serve as the domain controller for the hybrid identity lab and is ready for domain configuration and role installation.

---

## 🏢 Business Relevance

Deploying a domain controller in Azure reflects real-world hybrid environments where organizations maintain legacy on-prem identity systems while extending control and visibility to cloud identity services. This setup is essential for:

* Transitioning from legacy IT infrastructure to modern cloud identity
* Supporting hybrid workforces with secure access to cloud and on-prem apps
* Ensuring seamless SSO and conditional access policies via Entra ID
* Enabling password writeback, group synchronization, and identity governance

---

## 🖼️ Screenshots

| Step Description                                                          | Screenshot                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🌐 Network Interface Details  <br>*(`network-interface-details.png`)*     | ![NIC Details](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/blob/main/Phase%201%20Step%201:%20Create%20the%20Windows%20Server%202022%20VM%20\(Domain%20Controller\)/screenshots/network-interface-details.png?raw=true)           |
| ➕ Add Custom NSG Rule (Port 8080)  <br>*(`nsg-add-custom-rule-8080.png`)* | ![NSG Rule 8080](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/blob/main/Phase%201%20Step%201:%20Create%20the%20Windows%20Server%202022%20VM%20\(Domain%20Controller\)/screenshots/nsg-add-custom-rule-8080.png?raw=true)          |
| 📜 Default NSG Inbound Rules  <br>*(`nsg-inbound-rules-default.png`)*     | ![Default Inbound Rules](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/blob/main/Phase%201%20Step%201:%20Create%20the%20Windows%20Server%202022%20VM%20\(Domain%20Controller\)/screenshots/nsg-inbound-rules-default.png?raw=true) |
| ❌ NSG Without Port Rules  <br>*(`nsg-no-port-rules.png`)*                 | ![No Port Rules](https://github.com/miadco/Hybrid-Identity-Enterprise-Administration/blob/main/Phase%201%20Step%201:%20Create%20the%20Windows%20Server%202022%20VM%20\(Domain%20Controller\)/screenshots/nsg-no-port-rules.png?raw=true)                 |

---

## 🙏 Acknowledgments

This is a lab was created using AI to simulate a real world hybrid identity scenario
