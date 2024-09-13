# Microsoft Security Solutions Labs

## Table of Contents

1. [Microsoft Defender for Endpoint](#1-microsoft-defender-for-endpoint)
2. [Microsoft Sentinel](#2-microsoft-sentinel)
3. [Azure Active Directory Identity Protection](#3-azure-active-directory-identity-protection)
4. [Microsoft Defender for Cloud](#4-microsoft-defender-for-cloud)
5. [Microsoft 365 Defender](#5-microsoft-365-defender)
6. [Azure Firewall and Network Security Groups](#6-azure-firewall-and-network-security-groups)
7. [Microsoft Cloud App Security (MCAS)](#7-microsoft-cloud-app-security-mcas)

---

## 1. Microsoft Defender for Endpoint

### Lab Objective

Set up **Microsoft Defender for Endpoint** to protect your devices from advanced threats.

### Getting Started Steps

1. **Sign Up for a Trial**

   - Visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/en-us/security/business/threat-protection/microsoft-defender-endpoint) page.
   - Click on **Free trial** and sign up using your Microsoft account.

2. **Access the Defender Portal**

   - Navigate to the Microsoft 365 Defender portal at [https://security.microsoft.com](https://security.microsoft.com).
   - Log in with your credentials.

3. **Onboard Devices**

   - Go to **Settings** > **Endpoints** > **Device management** > **Onboarding**.
   - Choose your preferred onboarding method (e.g., Local Script, Group Policy, Microsoft Endpoint Manager).
   - Follow the instructions to onboard a Windows device.

### Operational Overview

- **Dashboard Navigation**

  - Explore the **Security Operations** dashboard.
  - Review **Alerts**, **Incidents**, and **Device Inventory**.

- **Threat Analytics**

  - Access the **Threat Analytics** section to understand current threats.
  - Analyze how Defender detects and responds to threats.

---

## 2. Microsoft Sentinel

### Lab Objective

Deploy **Microsoft Sentinel** and connect data sources for centralized security monitoring.

### Getting Started Steps

1. **Create an Azure Account**

   - Sign up for a free Azure account at [https://azure.microsoft.com](https://azure.microsoft.com).

2. **Deploy Microsoft Sentinel**

   - In the Azure portal, search for **Microsoft Sentinel**.
   - Click on **Microsoft Sentinel** under **Services**.
   - Select **Add** and choose an existing Log Analytics workspace or create a new one.

3. **Connect Data Sources**

   - In the Sentinel workspace, navigate to **Configuration** > **Data connectors**.
   - Connect sources like **Azure Active Directory**, **Microsoft 365 Defender**, or custom logs.
   - Follow the on-screen instructions for each connector.

### Operational Overview

- **Analytics Rules**

  - Go to **Configuration** > **Analytics**.
  - Enable built-in analytics rules for threat detection.
  - Customize rules or create new ones as needed.

- **Incident Management**

  - Navigate to **Threat management** > **Incidents**.
  - Review how Sentinel groups alerts into incidents.
  - Practice investigating and responding to incidents.

---

## 3. Azure Active Directory Identity Protection

### Lab Objective

Configure **Azure AD Identity Protection** to detect and remediate identity risks.

### Getting Started Steps

1. **Access Azure AD Portal**

   - Log in to the [Azure Portal](https://portal.azure.com).
   - Navigate to **Azure Active Directory** > **Security** > **Identity Protection**.

2. **Enable Risk Policies**

   - Go to **Protect** > **User risk policy**.
     - Configure the policy by setting **Assignments** and **Controls**.
   - Repeat for **Sign-in risk policy**.

3. **Simulate Risk Events**

   - Use tools like [TOR browser](https://www.torproject.org/) to simulate risky sign-ins.
   - Monitor how Identity Protection detects and responds to these events.

### Operational Overview

- **Risk Reports**

  - Explore **Risky users**, **Risky sign-ins**, and **Risk detections** reports.
  - Review the details and remediation options for each risk.

- **Integration with Conditional Access**

  - Navigate to **Azure AD** > **Security** > **Conditional Access**.
  - Create a policy that requires MFA for high-risk sign-ins.
  - Test the policy to see how it enhances security.

---

## 4. Microsoft Defender for Cloud

### Lab Objective

Secure your Azure resources using **Microsoft Defender for Cloud**.

### Getting Started Steps

1. **Enable Defender for Cloud**

   - In the Azure portal, search for **Microsoft Defender for Cloud**.
   - Click on **Get started** and enable it for your subscriptions.

2. **Review Security Posture**

   - Check your **Secure Score** on the overview page.
   - Click on **Recommendations** to see suggested improvements.

3. **Implement Security Recommendations**

   - Select a recommendation and click **Remediate**.
   - Follow the guided steps to resolve security issues.

### Operational Overview

- **Continuous Export**

  - Go to **Environment settings** > **Continuous export**.
  - Set up export of security alerts to **Log Analytics** or **Event Hubs**.

- **Workflow Automation**

  - Navigate to **Automation & orchestration** > **Workflow automation**.
  - Create a **Logic App** to automate responses to specific security alerts.

---

## 5. Microsoft 365 Defender

### Lab Objective

Utilize **Microsoft 365 Defender** to protect against threats across Microsoft 365 services.

### Getting Started Steps

1. **Access Microsoft 365 Defender**

   - Go to [https://security.microsoft.com](https://security.microsoft.com).
   - Log in with your Microsoft 365 admin credentials.

2. **Configure Policies**

   - Navigate to **Policies & rules** > **Threat policies**.
   - Set up policies for **Anti-phishing**, **Anti-malware**, and **Safe Attachments**.

3. **Use Attack Simulation Training**

   - Access **Email & collaboration** > **Attack simulation training**.
   - Create a new **Simulation** to educate users on phishing.

### Operational Overview

- **Threat Analytics**

  - Go to **Threat management** > **Threat analytics**.
  - Explore current threat reports and mitigation strategies.

- **Incident Response**

  - Navigate to **Incidents & alerts** > **Incidents**.
  - Manage incidents across email, endpoint, and identity.
  - Utilize automated investigation and response features.

---

## 6. Azure Firewall and Network Security Groups

### Lab Objective

Implement network security using **Azure Firewall** and **Network Security Groups (NSGs)**.

### Getting Started Steps

1. **Create a Virtual Network**

   - In the Azure portal, click **Create a resource** > **Networking** > **Virtual network**.
   - Set up a new virtual network with desired subnets.

2. **Deploy Azure Firewall**

   - Click **Create a resource** > **Networking** > **Azure Firewall**.
   - Add Azure Firewall to your virtual network.
   - Configure **Application** and **Network** rules.

3. **Configure Network Security Groups**

   - Navigate to your virtual network.
   - Under **Settings**, select **Subnets**.
   - Associate an NSG with your subnet or network interface.
   - Define inbound and outbound security rules.

### Operational Overview

- **Traffic Monitoring**

  - Go to **Azure Firewall** > **Logs**.
  - Enable **Diagnostic settings** to send logs to **Azure Monitor**.

- **Security Policies**

  - Use **Firewall Policy** to centralize and manage firewall rules.
  - For large-scale deployments, consider **Azure Firewall Manager**.

---

## 7. Microsoft Cloud App Security (MCAS)

### Lab Objective

Discover and secure your organization's use of cloud applications with **Microsoft Cloud App Security**.

### Getting Started Steps

1. **Access MCAS Portal**

   - Navigate to the [Cloud App Security portal](https://portal.cloudappsecurity.com).
   - Log in with your admin credentials.

2. **Set Up Discovery**

   - Go to **Discover** > **Create snapshot report**.
   - Upload firewall logs or integrate with supported network appliances.
   - Analyze the discovered cloud app usage.

3. **Configure Policies**

   - Navigate to **Control** > **Policies**.
   - Create policies for **Anomaly detection** and **App compliance**.
   - Set up alerts for risky behaviors.

### Operational Overview

- **App Governance**

  - Go to **Investigate** > **OAuth apps**.
  - Assess third-party apps connected to Microsoft 365.
  - Use **Governance actions** to block or sanction apps.

- **Conditional Access App Control**

  - Navigate to **Control** > **Conditional Access App Control**.
  - Set up policies to monitor and control user sessions in real-time.

---

## Additional Resources

- [Microsoft Learn](https://docs.microsoft.com/en-us/learn/): Free online training modules for all Microsoft technologies.
- [Microsoft Security Documentation](https://docs.microsoft.com/en-us/security/): In-depth guides and best practices.

---

I apologize for the oversight earlier. The above content has been converted to GitHub Markdown format with proper headings, links, and formatting. All titles use hashes for headings, and links are formatted using square brackets and parentheses.
