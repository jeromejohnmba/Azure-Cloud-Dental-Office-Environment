# Lessons Learned and Challenges

## Identity Security and MFA

- Multi-Factor Authentication (MFA) is critical for protecting sensitive patient information. MFA adds an additional layer of security by requiring users to verify their identity through an approved authentication method or device.

- Conditional Access policies should always be tested after deployment to verify they are correctly enforced on intended users and devices. Failure to validate policies can create security gaps that allow users to bypass protections.

- Conditional Access policies can easily become overapplied if not carefully scoped. IT administrators must carefully consider which users, groups, and devices should receive security restrictions to avoid accidental lockouts or administrative access issues.

---

# Intune and Endpoint Management

- Microsoft Intune provides centralized endpoint and security management for multiple users and devices. While policies may deploy quickly, many settings require synchronization and processing time before becoming fully effective.

- Policies often require manual syncing before endpoints acknowledge and apply the latest configurations. Delays in synchronization can temporarily prevent policies from taking effect.

- Many endpoint security controls such as Secure Boot, password requirements, and MFA are platform-independent concepts that can apply across Windows, Linux, and macOS environments.

- Security settings vary depending on organizational requirements. Some environments prioritize MFA and device trust, while others may emphasize BitLocker encryption for mobile device protection. IT administrators must evaluate business requirements and recommend appropriate security controls.

---

# Exchange Online and Collaboration

- When configuring shared mailboxes in Exchange Online, it is important to understand the difference between "Full Access" and "Send As" permissions:
  
  - Full Access allows users to open, read, organize, delete, and manage mailbox content.
  - Send As allows users to send messages that appear to originate directly from the shared mailbox.

- In some cases, "Send As" permissions may be sufficient without granting complete mailbox management access.

---

# Azure Infrastructure and Deployment

- Azure Resource Groups simplify cloud administration by organizing related resources into centralized containers. This allows policies, permissions, and management tasks to be handled more efficiently across groups of resources.

- Virtual Machines (VMs) block remote traffic by default. Remote Desktop Protocol (RDP) access must be enabled through Azure networking and firewall rules using port 3389 before remote administration can occur.

- Monitoring infrastructure immediately after deployment can help validate that systems are operating correctly. For example, abnormally high CPU usage may indicate unfinished tasks, pending installations, or resource issues.

- Azure monitoring and alerting provide proactive visibility into infrastructure health and performance, allowing administrators to identify problems before users are impacted.

---

# Azure Storage and Cost Management

- Azure Storage permissions can be structured based on user roles and access requirements. Uploading files to Azure Blob Storage does not automatically make them accessible to all users.

- Storage and infrastructure sizing should be carefully planned. Overprovisioning storage or resources can significantly increase monthly cloud costs over time. Administrators should balance scalability with budget-conscious resource allocation.

---

# Backup and Disaster Recovery

- Backups are critical for both infrastructure recovery and patient data protection. Healthcare organizations often require backup and recovery solutions to support operational continuity and regulatory compliance.

- Configuring Azure VM backups through Recovery Services Vaults provides protection against outages, corruption, accidental deletion, and disaster scenarios.

- Backup solutions should always prioritize recoverability and retention planning to ensure business continuity requirements can be met.
