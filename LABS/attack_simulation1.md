**Designing a Practical Demonstration of Microsoft's Security Solutions**

This demonstration will guide you through setting up a simulated attack environment and using Microsoft security tools to detect and respond to the attack. The Microsoft security tools covered include:

- **Microsoft Defender for Endpoint**
- **Microsoft Defender for Cloud Apps**
- **Microsoft Defender for Cloud (Azure)**
- **Azure Entra Information Protection**
- **Honeytoken Users**

---

### **Overview**

We will:

1. **Set up a lab environment** with Azure Virtual Machines (VMs) and Azure Active Directory (Azure AD).
2. **Deploy and configure Microsoft security tools** in the environment.
3. **Simulate cyber attacks** such as malware infections, data exfiltration, and unauthorized access.
4. **Detect and respond to attacks** using Microsoft security solutions.

---

### **Prerequisites**

- An active **Azure subscription**.
- Appropriate **Microsoft 365 licenses** (e.g., Microsoft 365 E5) for access to security tools.
- Basic knowledge of Azure and Microsoft 365 administration.

---

## **Step-by-Step Procedures**

### **1. Set Up the Lab Environment**

#### **1.1 Create an Azure AD Tenant**

- **Sign in** to the [Azure portal](https://portal.azure.com).
- Navigate to **Azure Active Directory**.
- If needed, create a new tenant for testing purposes.

#### **1.2 Set Up Virtual Machines**

- **Create three VMs**:

  - **VM1 (Victim Machine)**: Windows 10 or Windows Server.
  - **VM2 (Attacker Machine)**: Kali Linux or another penetration testing OS.
  - **VM3 (Admin Machine)**: Windows Server for monitoring.

- Ensure all VMs are in the same **Virtual Network** for communication.

#### **1.3 Configure Networking**

- Set up **Network Security Groups (NSGs)** to allow necessary traffic (RDP, SSH).
- Configure **Public IPs** if remote access is needed.

---

### **2. Deploy and Configure Microsoft Defender for Endpoint**

#### **2.1 Enable Defender for Endpoint**

- Access the **Microsoft 365 Defender portal**: [security.microsoft.com](https://security.microsoft.com).
- Navigate to **Settings > Endpoints > Onboarding**.

#### **2.2 Onboard Devices**

- Choose an onboarding method (e.g., **Local Script**, **Group Policy**, or **Microsoft Endpoint Manager**).
- **Download the onboarding package**.

- **On VM1 and VM3**:

  - Run the onboarding script as an administrator.
  - Verify that the devices appear in the **Device Inventory** in the portal.

#### **2.3 Configure Security Settings**

- In the portal, go to **Settings > Endpoints > Device Configuration**.
- Enable features like **Attack Surface Reduction (ASR)** rules, **Endpoint Detection and Response (EDR)**, and **Automatic Investigation and Remediation**.

---

### **3. Deploy and Configure Microsoft Defender for Cloud Apps**

#### **3.1 Access Defender for Cloud Apps**

- Navigate to the **Defender for Cloud Apps portal**: [portal.cloudappsecurity.com](https://portal.cloudappsecurity.com).

#### **3.2 Connect Apps and Services**

- Go to **Settings > App connectors**.
- Connect relevant apps (e.g., **Office 365**, **Azure**, **Salesforce**).

#### **3.3 Configure Policies**

- Create **Activity Policies** to monitor and alert on suspicious activities.
  - Example: **Mass download by a single user**, **Impossible travel**, **Anomalous file sharing**.

---

### **4. Configure Microsoft Defender for Cloud (Azure)**

#### **4.1 Enable Defender for Cloud**

- In the Azure portal, select **Microsoft Defender for Cloud**.
- Enable **Defender plans** for:

  - **Servers**
  - **App Service**
  - **Storage Accounts**
  - **SQL Databases**

#### **4.2 Set Security Policies**

- Go to **Environment Settings**.
- Select your subscription and configure **Security Policy**.
- Enable recommendations and standards (e.g., **Azure Security Benchmark**).

---

### **5. Implement Azure Entra Information Protection**

#### **5.1 Access Azure Information Protection**

- In the Azure portal, search for **Azure Information Protection**.
- Activate the service if not already enabled.

#### **5.2 Create Sensitivity Labels**

- In the **Microsoft 365 compliance center**: [compliance.microsoft.com](https://compliance.microsoft.com).
- Navigate to **Classification > Sensitivity labels**.
- Create labels like **Confidential**, **Highly Confidential**.

#### **5.3 Publish Labels**

- Create a **Label Policy** to publish labels to users.
- Assign the policy to users on **VM1**.

#### **5.4 Install AIP Client**

- On **VM1**, download and install the **Azure Information Protection Unified Labeling Client**.
- Verify that labels are available in Office applications.

---

### **6. Create Honeytoken Users**

#### **6.1 Create a Honeytoken User Account**

- In **Azure AD**, create a user account named **HoneyUser**.
- Do not assign any roles or licenses to **HoneyUser**.
- Set a strong, non-expiring password.

#### **6.2 Set Up Monitoring**

- In the **Azure AD portal**, enable **Sign-in logs** and **Audit logs**.
- Create an **Azure Monitor Alert** for any activity involving **HoneyUser**.

---

### **7. Simulate Attacks**

#### **7.1 Simulate Malware Infection**

- On **VM2 (Attacker Machine)**:

  - Create a harmless test file that mimics malware (e.g., **EICAR test file**).
  - Attempt to transfer the file to **VM1** via email or file share.

#### **7.2 Simulate Data Exfiltration**

- On **VM1**:

  - Open sensitive documents labeled with **Confidential**.
  - Attempt to upload these documents to an unauthorized cloud service (e.g., personal Dropbox).

#### **7.3 Attempt Unauthorized Access**

- From **VM2**:

  - Attempt to RDP into **VM1** using common usernames (e.g., **admin**, **user**).
  - Try to log in using the **HoneyUser** account.

#### **7.4 Simulate Phishing Attack**

- Send a phishing email from **VM2** to **VM1** with a link to a fake login page.
- Attempt to capture credentials.

---

### **8. Detect and Respond Using Microsoft Security Tools**

#### **8.1 Microsoft Defender for Endpoint**

- **Detection**:

  - In the **Microsoft 365 Defender portal**, check **Incidents & Alerts**.
  - Locate alerts related to the malware simulation.
  - View the **Alert Storyline** for detailed information.

- **Response**:

  - Use **Automated Investigation** to analyze and remediate threats.
  - **Isolate VM1** from the network if necessary.
  - Perform a **Full Scan** on VM1.

#### **8.2 Microsoft Defender for Cloud Apps**

- **Detection**:

  - In the **Defender for Cloud Apps portal**, go to **Alerts**.
  - Find alerts related to **Mass download/upload** or **Unusual file sharing**.

- **Response**:

  - **Quarantine** or **Revoke access** to shared files.
  - Adjust **Activity Policies** to prevent future occurrences.

#### **8.3 Microsoft Defender for Cloud (Azure)**

- **Detection**:

  - In the Azure portal, navigate to **Microsoft Defender for Cloud > Security Alerts**.
  - Identify alerts like **Brute-force attack** or **Unusual VM activity**.

- **Response**:

  - Implement **Just-In-Time VM Access** to limit RDP/SSH exposure.
  - Apply **NSG rules** to restrict access.

#### **8.4 Azure Entra Information Protection**

- **Detection**:

  - In the **Microsoft 365 compliance center**, check **Activity Explorer**.
  - Monitor for actions like **Label downgrade** or **Unauthorized sharing**.

- **Response**:

  - **Revoke access** to documents.
  - Enforce **Conditional Access Policies** requiring **Multi-Factor Authentication (MFA)** for sensitive actions.

#### **8.5 Honeytoken User Monitoring**

- **Detection**:

  - In **Azure AD Sign-in logs**, look for any sign-in attempts by **HoneyUser**.
  - Check **Risky Sign-ins** under **Azure AD Identity Protection**.

- **Response**:

  - **Investigate** the source IP and user agent.
  - **Block** the IP address if malicious.
  - Increase monitoring on accounts and assets.

---

### **9. Reporting and Analysis**

- **Generate Reports**:

  - In each portal, use built-in reporting tools to export data on detections and responses.
  - Compile a comprehensive report covering all incidents.

- **Analyze Attack Vectors**:

  - Identify how the attacks were executed.
  - Assess the effectiveness of each security tool.

- **Review and Improve**:

  - Adjust security policies based on findings.
  - Plan for additional training or security measures if needed.

---

### **10. Clean Up the Environment**

- **Terminate VMs** if they are no longer needed to avoid unnecessary costs.
- **Remove test accounts** like **HoneyUser**.
- **Reset configurations** back to default if this was done in a production environment.


