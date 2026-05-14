The Azure Dental Office Environment project began by adding hypothetical users to Azure database (licensing for Entra ID added later).

![Added Users](../screenshots/added-users.png)

The next step was to organize users into Microsoft Entra ID security and Microsoft 365 groups based on department and role. This allowed permissions, Conditional Access policies, Intune assignments, and administrative access to be managed more efficiently through group-based access control.

![Created Groups](../screenshots/created-groups.png)

Once the users were created, business 365 licensing had to be added to each user to allow setup of Entra ID, Intune, and Exchange online etc.

![Business License](../screenshots/business-license.png)

Upon assigning licensing, a compliance security policy was created for Windows 10/11 machines.

![Intune Compliance Policy](../screenshots/intune-compliance-policy.png)

The basic requirements for the compliance policy were BitLocker, Secure Boot, Code Integrity, Firewall, Anti-virus, anti-malware, and antispyware. This was to ensure patient records were encrypted, no malicious drivers/software could be loaded onto the workstation, and the communication of records would be transmitted securely by blocking specific traffic.

![Intune Compliance Policy 2](../screenshots/intune-compliance-policy2.png)

More requirements for the compliance policy.

![Intune Compliance Policy 3](../screenshots/intune-compliance-policy3.png)

The compliance policy was applied to the Clinical group as they would be interacting directly with patients. They needed the most secure environment since they typically are the most regulated user groups due to existing laws. This policy checks if the workstation is secure enough for Clinical users prior to the installation of the tools.

![Intune Compliance Policy 4](../screenshots/intune-compliance-policy4.png)

Then a configuration profile was created using the endpoint template. The configuration policy was intended to apply, activate, and enable the Firewall, BitLocker, and Windows Defender from the compliance policy.

![Configuration Profile 1](../screenshots/configuration-profile-1.png)

It was named Clinical Endpoint Protection Policy and it was designed to enforce the compliance policy checks.

![Configuration Profile 2](../screenshots/configuration-profile-2.png)

Basic windows firewall was enabled (advanced configurations can come later).

![Configuration Profile 3](../screenshots/configuration-profile-3.png)

Encrypting devices activates BitLocker on the workstation.

![Configuration Profile 4](../screenshots/configuration-profile-4.png)

Tamper protection enabled for the Microsoft Windows Defender Security Center to disable and block unauthorized programs.

![Configuration Profile 5](../screenshots/configuration-profile-5.png)

Any administrative actions will now require administrator.

![Configuration Profile 6](../screenshots/configuration-profile-6.png)

The configuration profile was assigned to the clinical group as well to apply the security settings to the clinical users workstations (on top of the compliance policy check).

![Configuration Profile 7](../screenshots/configuration-profile-7.png)

A finally review before creating the configuration profile.

![Configuration Profile 8](../screenshots/configuration-profile-8.png)

This setting enables automatic Intune enrollment for Entra ID joined Windows devices.

![Intune Automatic Enrollment Devices Entra ID](../screenshots/intune-automatic-enrollment-devices-entraid.png)

A sample workstation was added to devices to test policy implementation (a M365 account had to be added to my own windows as well).

![Intune Device Enrollment](../screenshots/intune-device-enrollment.png)

As another security layer, MFA was added for clinical users via conditional access as part of Entra ID. This means any workstation that clinical users log into will require MFA.

![Entra ID Require MFA](../screenshots/entra-id-require-mfa.png)

A resource group was created to organize the VM, storage, backups etc.

![VM Resource Group](../screenshots/vm-resource-group.png)

A virtual machine was created to mimic a real dental practice's infrastructure - usually a centralized location with a patient database, PMS etc.

![Azure VM 2](../screenshots/azure-vm2.png)

Enabled RDP to allow remote access to the newly deployed VM.

![Azure VM Connect](../screenshots/azure-vm-4-connect.png)

Added file server to the newly deployed VM to mimic a shared file server environment similar to a dental office with patient documents, x-rays etc.

![Azure VM File Server](../screenshots/azure-vm-5-file-server.png)

Shared patient records folder to simulate how information is shared across a network at a dental practice.

![Azure VM Shared Folders](../screenshots/azure-vm-6-shared-folders.png)

Backups and patient management data were intended to replicate a real business environmental - a backup for the server data, and patient management for hypothetical PMS application files.

![Azure VM Shared Folders 2](../screenshots/azure-vm-8-shared-folders.png)

Created a second MFA conditional access policy only for the admin account to protect admin access since it has the most privileges.

![MFA Admins](../screenshots/mfa-admins.png)

Create a storage account to host patient intake forms in a simulated dental practice. This allows access from different workstations and office locations in case it is a multi-location practice.

![Blob Storage](../screenshots/blob-storage.png)

Added a container and uploaded patient documentation for dental users.

![Blob Storage 3](../screenshots/blob-storage3.png)

An alert rule was created to track CPU usage over 80%. This was a reliable indicator to track server performance to see if it was being overloaded and could be used by a real dental practice to see if their PMS is running optimally. This alert in particular was set to email notification but other options were available.

![Alert Rule 2](../screenshots/alert-rule2.png)

The alert was set to level 2 - warning: meaning if the CPU went over 80% usage it wasn't critical but still nevertheless important for IT staff to review. Alerts can set across multiple levels in case more urgent responses are needed such as critical infrastructure going down during an outage.

![Alert Rule 3](../screenshots/alert-rule4.png)

A backup of the server VM was created and added to the backup vault to store it. Vaults are containers that store the backup itself and any retention policies, restore points etc.

![Backup 1](../screenshots/backup-1.png)

Here the admin mailbox was converted to a shared mailbox on Exchange admin center. This was set to allow multiple office staff and the dentist to use it simultaneously. In a real world scenario, a dental practice could use it to view all appointments in one location, respond to patient emails etc.

![Exchange Shared Mailbox 3](../screenshots/exchange-shared-mailbox.png)

Once the shared mailbox is created, individual members have to be added to it for access from their email system. Read and manage allowed users to read emails but also edit and send them as needed.

![Exchange Shared Mailbox 3](../screenshots/exchange-shared-mailbox-3.png)

To create a distribution list, a provider group was created so all office staff could send one email to go out to all members of a group. At a real dental practice, this can be used for schedule changes, meeting reminders etc. to cut back on single emails.

![Exchange Distribution List](../screenshots/exchange-distribution-list.png)

Ashley Carter was assigned as the owner of the distribution list to manage it such as adding new providers, new staff, changing settings etc.

![Exchange Distribution List Owner](../screenshots/exchange-distribution-list-owner.png)

The members included both since it allows them both to receive emails but more users could be added later if needed.

![Exchange Distribution Members](../screenshots/exchange-distribution-members.png)

Allstaff was used as the group email address that would be used to distribute emails to members.

![Exchange Distribution List Group Email](../screenshots/exchange-distribution-list-groupemail.png)

Finally, the Dental Providers email group was created so users could send emails through any email client, such as Outlook, to all distribution group members at once.

![Exchange Distribution List Created 2](../screenshots/exchange-distribution-list-created-2.png)


