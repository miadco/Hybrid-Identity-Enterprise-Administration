# Azure Hybrid Identity & Enterprise Administration Lab

This project provides a step-by-step guide to building a foundational Hybrid Identity lab in Microsoft Azure. It is designed to be a superior alternative to local virtualization (like VirtualBox), providing hands-on experience in a realistic, enterprise-grade cloud environment.

The lab is structured in progressive phases, starting with a core setup and advancing to production-grade security and troubleshooting scenarios.

📘 Powered by Prompt Engineering  
This lab was designed, built, and documented in tandem with ChatGPT-4, demonstrating not just technical proficiency in IAM and cloud identity, but also advanced prompt engineering workflows for system planning, troubleshooting, and documentation.

Every step — from idea to implementation — reflects both my engineering skill and my ability to co-create effectively with AI.


---

## 📋 Table of Contents

* [Objective](#🎯-objective)
* [Prerequisites](#🛠%ef%b8%8f-prerequisites)
* [Phase 1: Core Infrastructure Setup](#⚙%ef%b8%8f-phase-1-core-infrastructure-setup)
* [Phase 2: Add a Client Workstation (Optional)](#💝%ef%b8%8f-phase-2-add-a-client-workstation-optional)
* [Phase 3: Production-Grade Lab Enhancements](#🛡%ef%b8%8f-phase-3-production-grade-lab-enhancements)
* [Bonus: Infrastructure as Code (IaC)](#%f0%9f%93%a6-bonus-infrastructure-as-code-iac)
* [Cost Management](#%f0%9f%92%b8-cost-management)

---

## 🎯 Objective

To build a functioning Microsoft Hybrid Identity environment by:

* Deploying a Windows Server Domain Controller in Azure.
* Synchronizing an on-premises Active Directory domain (corp.local) with Microsoft Entra ID.
* Simulating enterprise administration tasks, security policy implementation, and troubleshooting.

---

## 🛠️ Prerequisites

* **Azure Account**: A Free Tier account is recommended, which includes a B1s VM and a \$200 credit for the first 30 days.
* **Basic Azure Portal Familiarity**: A general understanding of navigating the Azure portal.
* **Internet Connection**: Required for Remote Desktop (RDP) access.

---

## ⚙️ Phase 1: Core Infrastructure Setup

### Step 1: Create the Windows Server 2022 VM

1. Log in to the Azure Portal: [https://portal.azure.com](https://portal.azure.com)
2. Go to **Virtual Machines > Create > Azure virtual machine**.
3. Configure the VM:

   * **Resource group**: Create new > `HybridIdentityLab-RG`
   * **VM Name**: `HybridLab-DC`
   * **Region**: Pick your nearest (e.g., West US 3)
   * **Image**: Windows Server 2022 Datacenter: Azure Edition - Gen2
   * **Size**: Standard\_B1s (Free tier eligible) or Standard\_D2s\_v3 (if using credits).
   * **Username**: `labadmin`
   * **Password**: Create and save a strong password.
   * **Inbound Ports**: Allow RDP (3389)
   * **Disks**: Leave the default Standard SSD.
   * **Networking**: Leave the defaults to create a new VNet.
4. Click **Review + Create**, then **Create**.

### Step 2: Connect and Promote to a Domain Controller

1. In the Azure portal, navigate to the VM and click **Connect > RDP**.
2. Download the RDP file and log in.
3. Open **Server Manager > Add Roles and Features**.
4. Install **Active Directory Domain Services**.
5. After installation, promote the server to a domain controller:

   * Select **Add a new forest** and enter `corp.local`.
   * Set a DSRM password and complete the wizard.
   * The server will restart.

### Step 3: Install and Configure Microsoft Entra Connect

1. Log in after the restart.
2. Disable IE Enhanced Security in Server Manager.
3. Download and install **Microsoft Entra Connect**.
4. Use the wizard to sync with your Entra ID tenant.
5. Create test users and OUs in **Active Directory Users and Computers**.

---

## 💝️ Phase 2: Add a Client Workstation (Optional)

### Create a Client VM

1. Create a second VM in `HybridIdentityLab-RG`:

   * **Name**: `Client-PC`
   * **Image**: Windows 10/11 Pro
   * **Size**: Standard\_B1s
   * **Networking**: Use same VNet as `HybridLab-DC`

### Join Client to Domain

1. Connect via RDP.
2. Go to **System Properties > Change settings > Change...**
3. Select **Domain** and enter `corp.local`.
4. Authenticate with domain admin credentials.
5. Restart VM and verify domain login.

---

## 🛡️ Phase 3: Production-Grade Lab Enhancements

### Tier 1: Refining Synchronization & Role Assignment

* **OU Filtering**: Configure in Entra Connect wizard to sync only specific OUs.
* **Group Sync**: Create AD security groups and confirm cloud replication.
* **Role Assignments**: Assign Entra roles (e.g., User Administrator) to synced users.

### Tier 2: Implementing Security Policies (Premium Features)

* **Conditional Access**: Require MFA for admins accessing Azure Portal.
* **SSPR with Password Writeback**:

  * Enable password writeback in Entra Connect.
  * Configure SSPR and test from client.

### Tier 3: Simulating and Recovering from Failures

* **Simulate Sync Failure**:

  * Stop Azure AD Sync service.
  * Create a new on-prem user and wait.
  * Confirm user is not synced.
* **Recovery**:

  * Use **Synchronization Service Manager** to check errors.
  * Restart the service.
  * Run PowerShell: `Start-ADSyncSyncCycle -PolicyType Delta`
  * Confirm successful sync.

---

## 📆 Bonus: Infrastructure as Code (IaC)

* Navigate to `HybridIdentityLab-RG` in Azure Portal.
* Go to **Export Template** under Settings.
* Download the ARM Template (JSON).
* Optionally, convert to **Bicep** for cleaner syntax and reuse.

---

## 💸 Cost Management

* **Shut Down VMs** when not in use to avoid compute charges.
* **Set Budgets** in Azure Cost Management + Billing.
* **Delete Resource Group** when lab is complete to remove all costs.

---

This lab not only prepares you for real-world IAM and hybrid identity tasks—it demonstrates your ability to plan, build, secure, and recover enterprise systems in the cloud.

---
