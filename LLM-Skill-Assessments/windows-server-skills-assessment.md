# **Windows-Server-Skills-Assessment**

## **Conclusion:**

Based on the answers provided, I assess the user's **Windows Server skills** to be **Advanced**, particularly in the areas of **Active Directory management**, **Group Policy troubleshooting**, and **server administration**. The user demonstrates extensive experience in designing, implementing, and managing Windows Server environments for **SMBs**, **nonprofits**, and **business associations**. Their practical experience spans over **17 years**, with a strong focus on **disaster recovery**, **server migrations**, and **automation**.

**Note:** This assessment is **incomplete as of today's date**. Several sections are yet to be completed, including those on **NTFS and Share Permissions**, **Active Directory Federation Services (AD FS)**, and **High Availability and Load Balancing**. You can expect these sections to be added in future updates.  

- [NTFS and Share Permissions](#8-ntfs-and-share-permissions)  
- [Active Directory Federation Services (AD FS)](#9-active-directory-federation-services-ad-fs)  
- [High Availability and Load Balancing](#10-high-availability-and-load-balancing)

### **Key Areas of Strength:**

- **Active Directory & Group Policy**: Strong understanding of **AD DS**, **GPO creation and troubleshooting**, **permissions management**, and **Group Policy modeling**.
- **Automation & Scripting**: Expertise in **PowerShell**, with a focus on **automating complex tasks** such as **permissions remediation** and **Group Policy management**.
- **Server Administration**: Extensive experience in **Windows Server deployments**, **DNS**, **DHCP**, **Print Services**, and **certificate authority management**.

---

## **Questions and Answers**

### **1. Understanding Server Roles**

**Question:**  
Can you describe the differences between a Domain Controller (DC), a Member Server, and a Standalone Server in a Windows Server environment?

**Answer:**  

- **Domain Controllers (DC)**: Responsible for user authentication, group policy management, certificate management, and other AD services. In small businesses, DCs may also function as file and application servers.  
- **Member Servers**: These are servers part of the AD domain but do not act as DCs. They typically perform tasks such as print servers, file servers, or application servers.  
- **Standalone Servers**: These do not use Windows AD and are often configured as workgroup servers. They can also be Hyper-V hosts or other specialized systems.

**Assessment:**  
The user demonstrates a strong understanding of the **roles** and **functions** of various server types in a typical Windows Server environment. They also mention key components like **Global Catalog** and **FSMO roles**, indicating thorough knowledge of DC infrastructure.

---

### **2. Promoting a Server to a Domain Controller**

**Question:**  
You’ve been tasked with setting up a new Domain Controller for a small business with 50 employees. What pre-checks would you perform before promoting the server? What critical settings do you need to configure during the promotion process?

**Answer:**  

- Pre-checks: Verify hardware requirements, ensure the server OS is up to date, check network connectivity, configure the server name, verify DNS functionality, and prepare backup and recovery plans.  
- Critical settings: Set the domain name and NetBIOS name, ensure licensing and CALs are configured, create and store a DSRM password securely, configure replication, and ensure that proper site definitions and subnets are set up.

**Assessment:**  
The response is comprehensive and detailed, covering essential pre-promotion checks and key **settings** to ensure a successful DC promotion. This indicates the user’s ability to perform **well-planned and organized deployments**.

---

### **3. Group Policy Management Best Practices**

**Question:**  
In an SMB with 100 users across 3 locations, how would you structure Group Policy Objects (GPOs) to balance performance and security?

**Answer:**  

- Use **centralized GPOs** for domain-wide settings (e.g., password policies).  
- Define **site-level GPOs** for settings specific to locations (e.g., printer mapping, network drives).  
- Use **organizational units (OUs)** for user and computer groups, applying GPOs based on role (e.g., accounting, HR).  
- Regularly review and **clean up unused GPOs** to prevent performance degradation.

**Assessment:**  
The user demonstrates a clear approach to balancing **security** and **performance** by recommending a **tiered GPO structure**. They also mention the importance of **GPO cleanup**, which is critical for long-term **AD health** and **scalability**.

---

### **4. Group Policy Troubleshooting**

**Question:**  
A user is not receiving a mapped network drive assigned via GPO. Where do you start troubleshooting?

**Answer:**  

- Start with **GPRESULTS** or **Group Policy Modeling** tools to check which GPOs are applied or blocked.  
- Check **event logs** for GPO application errors, especially during the login process.  
- Verify the **machine’s domain trust** and **network location awareness**.  
- If the user hasn’t connected via VPN recently, the machine might have lost its trust with the domain, which can be resolved by running `Reset-ComputerMachinePassword` in PowerShell.

**Assessment:**  
The troubleshooting process is methodical, starting with **GPRESULTS** and **Event Logs** to identify any applied or blocked GPOs. The mention of **machine trust issues** and the **PowerShell command** indicates practical experience with **common GPO issues**.

---

### **5. File & Print Services - Permissions Management**

**Question:**  
How do you structure NTFS & Share permissions for a nonprofit with 50 employees and the following shared drives:  

- **Accounting**: Restricted access, only the Accounting team can modify.  
- **HR**: Sensitive documents, only HR can access.  
- **General Files**: Everyone can read, only Managers can modify.

**Answer:**  

- For **Accounting**: Grant the Accounting group **Modify** permissions on both NTFS and Share permissions. Ensure that the group’s permissions are restricted to the **Accounting OU**.  
- For **HR**: Grant the HR group **Full Control** on both NTFS and Share permissions. Set **deny** permissions for others.  
- For **General Files**: Grant **Everyone** **Read** permissions on both NTFS and Share permissions, and give the **Managers group** **Modify** permissions.

**Assessment:**  
The user demonstrates an **in-depth understanding** of **NTFS and Share permissions**, explaining how to structure both based on user roles. Their response reflects a **methodical approach** to **ensuring secure access** to sensitive data.

---

### **6. Server Backup and Disaster Recovery**

**Question:**  
What’s your approach to disaster recovery planning for a small business server?

**Answer:**  

- Use **Veeam** for **backup** and **replication** of both **system states** and **full server images**.  
- Implement an **offsite backup solution**, like **Datto**, for cloud-based disaster recovery.  
- Test recovery **periodically** to ensure backups are functional.  
- Create a **disaster recovery runbook** for staff to follow in case of emergencies.

**Assessment:**  
The user’s approach is **comprehensive**, including the use of industry-standard tools like **Veeam** and **Datto**. The inclusion of a **disaster recovery runbook** highlights a focus on **preparedness** and **documentation**, which is crucial for SMBs.

---

### **7. Advanced GPO Troubleshooting and Best Practices**

**Question:**  
How do you handle Group Policy conflicts, and what is your approach to troubleshooting when GPOs don’t apply consistently across different computers?

**Answer:**  

- **GPRESULTS** helps in identifying which GPOs are being applied or blocked.  
- **Event Logs** and **Group Policy Modeling** can show the application of policies.  
- Investigate **replication issues** using **REPADMIN** to ensure GPOs are replicated properly.  
- Confirm **network connectivity** and the **status of the domain trust**.

**Assessment:**  
This answer shows a deeper understanding of **advanced GPO troubleshooting**, focusing on replication issues, network issues, and **GPO application modeling**. The user is clearly able to identify and solve issues that affect GPO consistency across systems.

---

### **Planned Sections & Additional Questions**

#### **8. NTFS and Share Permissions**

**Planned Question:**  
How do you manage and audit **NTFS** and **Share permissions** on a large file server? How do you ensure **compliance** with **security policies**?

#### **9. Active Directory Federation Services (AD FS)**

**Planned Question:**  
Can you explain how **AD FS** works and how you would implement it for an **SMB** looking to integrate with **Office 365**?

#### **10. High Availability and Load Balancing**

**Planned Question:**  
How would you implement **high availability** for critical **Windows Server services** (e.g., **DNS**, **DHCP**, **Active Directory**)?
