<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# OsTicket-Post-Installation-Configuration
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- [OsTicket Download](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
- [Pre-Installation Checklist](https://docs.google.com/document/d/1DyjX8LeVU98LjhXO2t2K2F0aHywI2N9GD57T3taO5qo/edit?tab=t.0)

<h2>Installation Steps</h2>

### **Step 1: Create Departments**

We’re starting by setting up the core department structure for **CyberFix**.

**📍 Navigation:**  
`Admin Panel → Agents → Departments → Add New Department`

---

#### 🏢 Add the following departments:

- **Security Operations**  
  - **Type:** Top-level  
  - **Description:** Handles cybersecurity threats, monitoring, and incident response.

- **Cloud Infrastructure**  
  - **Type:** Private  
  - **Description:** Manages cloud systems, virtual machines, and backend services.

- **Customer Support**  
  - **Type:** Support  
  - **Description:** First point of contact for general support and troubleshooting.
 
---

### **Step 2: Create Roles**

Now that departments are set up, we’ll define user permissions by creating custom roles for our CyberFix helpdesk agents.

**📍 Navigation:**  
`Admin Panel → Agents → Roles → Add New Role`


#### 🔐 Add the following roles:

- **Supreme Admin**  
  - **Permissions:** ✅ Full access to everything — check every box.

- **Tier 1 Tech**  
  - **Permissions:** Can only view and respond to tickets. No access to admin-level features or settings.
  - Under the Tickets tab Check `assign, close, create, edit, link, mark as answered, post reply, and refer`
  - Under Tasks check `edit, and post reply` leave everything else unchecked


- **Intern**  
  - **Permissions:** View-only. Can see tickets but cannot respond, edit, or take actions.
  - Check `mark as answered`

---

