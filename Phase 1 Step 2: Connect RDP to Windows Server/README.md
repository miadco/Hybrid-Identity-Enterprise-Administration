# 🎩 Phase 1 – Step 2: Connect RDP to Windows Server (on Linux)

## 📚 Table of Contents

* [📌 Overview](#-overview)
* [🎯 Objectives](#-objectives)
* [🧠 Key Concepts Reinforced](#-key-concepts-reinforced)
* [🧰 Lab Environment & Tools](#-lab-environment--tools)
* [🔧 Tasks Performed](#-tasks-performed)
* [📈 Outcome Summary](#-outcome-summary)
* [🏢 Business Relevance](#-business-relevance)
* [🖼️ Screenshots](#-screenshots)
* [🙏 Acknowledgments](#-acknowledgments)

---

## 📌 Overview

In this step, I connected to my Azure-hosted Windows Server 2022 VM using RDP from my Linux system. I used Remmina as my RDP client to establish the connection, which allowed me to begin configuring the machine directly via its graphical interface. This connection is essential to access tools like PowerShell, install the AD DS role, and promote the server to a domain controller — critical steps in any hybrid identity deployment.

---

## 🎯 Objectives

* Successfully connect to my Windows Server 2022 VM using Remmina (GUI) on Linux
* Ensure inbound RDP access is permitted by configuring the NSG in Azure
* Validate remote login and address any connectivity or memory-related issues
* Prepare the system for Active Directory Domain Services installation

---

## 🧠 Key Concepts Reinforced

| Concept                       | Description                                                                                   |
| ----------------------------- | --------------------------------------------------------------------------------------------- |
| Remote Desktop Protocol (RDP) | A protocol that allows users to connect to a Windows computer over the network using a GUI.   |
| Network Security Group (NSG)  | A virtual firewall in Azure that controls inbound and outbound traffic to network interfaces. |
| Inbound Port Rule             | A rule that permits traffic through specific ports (e.g., 3389 for RDP).                      |
| Remmina                       | An open-source Linux RDP client used for GUI-based remote sessions.                           |
| VM Resizing in Azure          | The process of allocating more resources (vCPU/RAM) to a VM to avoid performance issues.      |

---

## 🧰 Lab Environment & Tools

* Azure Portal
* Windows Server 2022 (Standard\_D2s\_v3 after resizing)
* Remmina (Linux RDP client)
* NSG with inbound rule for TCP port 3389
* Public IP for HybridLab-DC VM

---

## 🔧 Tasks Performed

1. Installed Remmina on my Linux system using `sudo apt install remmina`.
2. Launched Remmina and created a new connection with:

   * Protocol: RDP
   * Server: Public IP of my HybridLab-DC VM
   * Username: `labadmin`
   * Password: `jUl{57J8.`
3. Clicked Save and Connect, then accepted the certificate warning.
4. Encountered an initial connection failure due to missing NSG configuration.
5. Opened the Azure Portal and navigated to the VM’s Networking blade.
6. Created and attached a new NSG (`HybridLab-DC-NSG`) to the VM’s NIC.
7. Added an inbound rule allowing TCP traffic on port 3389 (priority 1000).
8. Retried the connection and successfully reached the Windows desktop.
9. Noted GUI issues and memory errors due to the initial Standard\_B1s VM size.
10. Resized the VM to `Standard_D2s_v3` (2 vCPUs, 8 GiB RAM) for better performance.
11. Reconnected and confirmed stability. Ready for AD DS role installation.

---

## 📈 Outcome Summary

After configuring the NSG and resizing the VM for better performance, I was able to remotely access my Windows Server through Remmina. This confirmed that RDP was working as expected, and the environment was now stable and ready for domain controller promotion.

---

## 🏢 Business Relevance

Remote connectivity is a cornerstone of enterprise infrastructure, especially in hybrid environments. By mastering RDP access, NSG configuration, and resource management in Azure, I built the foundation for secure administrative control. These skills translate directly to real-world scenarios in system administration, identity management, and hybrid cloud operations.

---

## 🖼️ Screenshots

| Description                                    | Image                                                                                            | Filename                        |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------- |
| Certificate Warning – Accept RDP Connection    | ![Certificate Warning](https://github.com/your-repo/images/rdp-certificate-warning.png?raw=true) | `(rdp-certificate-warning.png)` |
| Successful RDP Login – Windows Desktop Visible | ![Windows Desktop](https://github.com/your-repo/images/windows-login-success.png?raw=true)       | `(windows-login-success.png)`   |
| Session Logoff – DWVM Crash Notification       | ![DWVM Crash Error](https://github.com/your-repo/images/dwvm-crash-logoff.png?raw=true)          | `(dwvm-crash-logoff.png)`       |
| Azure VM Size Configuration – D2s\_v3 Selected | ![Azure VM Size](https://github.com/your-repo/images/azure-vm-size-d2sv3.png?raw=true)           | `(azure-vm-size-d2sv3.png)`     |

---

## 🙏 Acknowledgments

Thanks to Microsoft for providing the Azure platform that powers these hybrid identity labs. I also used AI assistance to help structure, troubleshoot, and document this process efficiently. Special shoutout to the open-source Remmina project for making cross-platform RDP access seamless on Linux.
