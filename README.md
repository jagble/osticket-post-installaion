<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# OsTicket-Post-Installation-Configuration
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

A full video walkthrough will be added here soon!  
> 🔗 [Watch the Video Tutorial (Coming Soon)](#)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- Windows 10 (running on Azure VM)
- HeidiSQL
- MySQL 5.5.62
- PHP 7.3.8


<h2>List of Prerequisites</h2>

- [OsTicket Download](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
- [Microsoft Azure Account](https://portal.azure.com/)
- Remote Desktop Client (RDP)

<h2>Installation Steps</h2>

### **Step 1: Create Departments**

We’re starting by setting up the core department structure for **CyberFix**.

**📍 Navigation:**  
`Admin Panel → Agents → Departments → Add New Department`

---

#### 🏢 Add the following departments:


##### 🧠 SysAdmins
- Handles core system configurations and escalated technical issues
- Ideal for senior technical personnel and administrators

##### ☁️ Cloud Infrastructure
- Manages virtual machines, Azure resources, and any cloud-related operations
- Useful for agents specializing in virtual systems and deployments

#### 🗑️ Delete Maintenance department
---

> 📝 **Note:** The **Support** department is created by default in osTicket — no need to create it manually.

---


### **Step 2 – Create Roles**

Now we’ll define the access levels for our agents by creating roles.

1. Navigate to **Admin Panel** → **Agents** → **Roles**
2. Click **"Add New Role"**
3. Create the following roles:


#### 👑 **Supreme Admin**
- **Description:** Has full access to everything in the helpdesk.
- **Permissions:**
  - All permissions checked


#### 🛠️ **Tier 1 Tech**
- **Description:** Can view, manage, and reply to tickets, but has limited configuration access.
- **Permissions:**
  - everything checked but `delete` `merge` and `premade`


#### 📘 **Intern**
- **Description:** Read-only access to observe tickets without the ability to respond or modify.
- **Permissions:**
  - Mark as Answered


#### ☁️ **Cloud Security Engineer**
- **Description:** Handles technical issues related to cloud infrastructure and security.
- **Permissions:**
  - check everything but delete


🗑️ **Delete Default Roles**

1. Navigate to the **Admin Panel** → **Agents** → **Roles**.
2. Delete the following default roles:
   - Expanded Access
   - Limited Access
   - View Only


---

### **Step 3 – Set Up Teams and Agents**

Now that the departments and roles are in place, we’ll set up teams and assign agents accordingly.


#### 🔹 Create Teams
Navigate to **Admin Panel** → **Agents** → **Teams** and create the following team:


- **Security Ops**  
  Focuses on cybersecurity threats, breach response, and incident escalation.

- Leave default team **Level 1 Support** 

  Handles general support issues like password resets, computer problems, and basic troubleshooting.
---

#### 🔹 Create Agents

Go to **Admin Panel** → **Agents** → **Add New Agent** and create the following:

- **Anthony Edwards**  
  - **Role:** Supreme Admin  
  - **Department:** SysAdmins  
  - **Team:** Security Ops  
  - **Permissions:** Full access to the system

- **Tyrese Haliburton**  
  - **Role:** Tier 1 Tech  
  - **Department:** Support  
  - **Team:** Level 1 Support  
  - **Permissions:** View and respond to tickets

- **Moses Moody**  
  - **Role:** Intern  
  - **Department:** Support   
  - **Permissions:** View-only (can see ticket statuses)

- **Klay Thompson**  
  - **Role:** Cloud Security Engineer  
  - **Department:** Cloud Infrastructure  
  - **Team:** Security Ops  
  - **Permissions:** Custom (relevant to cloud and security tasks)

---

### **Step 4 – Create Users (Customers)**

In this step, we’ll create two users (also known as customers or end-users) who will simulate people submitting support tickets.

---

#### 🔹 Navigate to:
**Agent Panel** → **Users** → **Add New User**

---

#### 🔹 Create the Following Users:

- **Name:** Jordan  
  **Email:** jordan@cyberfix.com

- **Name:** Taylor  
  **Email:** taylor@cyberfix.com

---

> 💡 **Tip:** You can name your users anything you'd like — just keep the email domain consistent (e.g., `@cyberfix.com`) for a cleaner and more professional-looking environment.

These users will help simulate real-world interactions when we start the ticketing simulation in the final part of the lab.

---

### **Step 5 – Configure SLA Plans**

SLA (Service Level Agreement) Plans define how quickly a ticket should be addressed based on its priority or category. For CyberFix, we’ll set up three SLA tiers using common severity naming conventions: **Sev-A**, **Sev-B**, and **Sev-C**.

---

#### 🔹 Navigate to:
**Admin Panel** → **Manage** → **SLA Plans** → **Add New SLA Plan**

---

#### 🔹 Create the Following SLA Plans:

1. **Sev-A**
   - Grace Period: **1 Hour**
   - Schedule: **24/7**

2. **Sev-B**
   - Grace Period: **4 Hours**
   - Schedule: **24/7**

3. **Sev-C**
   - Grace Period: **8 Hours**
   - Schedule: **Business Hours (8 AM – 5 PM)**

---

### **Step 6 – Configure Help Topics**

Help Topics help categorize incoming tickets and streamline ticket routing. For CyberFix, we’ll create Help Topics that align with common IT and cybersecurity support requests.

---

#### 🔹 Navigate to:
**Admin Panel** → **Manage** → **Help Topics** → **Add New Help Topic**

---

#### 🔹 Create the Following Help Topics:

1. **Business-Critical Outage**  
   For company-wide issues or outages affecting multiple users or systems.

2. **Password Reset**  
   For users who need their credentials reset or are locked out.

3. **Personal Computer Issue**  
   For general laptop/desktop issues (slow performance, software errors, etc.).

4. **Equipment Request**  
   For requests like keyboards, laptops, webcams, or replacement gear.

5. **Other**  
   For anything that doesn’t fit neatly into the categories above.

---

