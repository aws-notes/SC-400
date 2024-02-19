# Apply and manage sensitivity labels
Learning objectives
After completing this module, you will be able to:

* Apply sensitivity labels to Microsoft Teams, Microsoft 365 groups, and SharePoint sites.
* Monitor label usage using label analytics.
* Configure on-premises labeling.
* Manage protection settings and marking for applied sensitivity labels.
* Apply protections and restrictions to email.
* Apply protections and restrictions to files.

## Apply sensitivity labels to Microsoft Teams, Microsoft 365 groups, and SharePoint sites

Containers where labels can be published include:
* Microsoft 365 Groups
* Microsoft Teams
* Yammer Communities
* SharePoint Sites

Possible restrictions to configure via sensitivity labels:
* Privacy option (Public/Private/None)
* External User Access (Allowed/Forbidden)
* Control external sharing from labeled SharePoint Sites (Anyone/New and existing guests/Existing guests/Only people of organization)
* Access from unmanaged devices (Allow full access/Allow limited, web-only access/Block access)

### Options for applying a sensitivity label to groups and SharePoint sites
There are many ways to apply a label to a Group and SharePoint site.
* Creation wizard of a Group or SharePoint Site
* SharePoint Admin Center for existing ones
* Microsoft Teams Admin Center for existing ones
* Azure portal
* PowerShell

## Plan on-premises labeling
Adding on-premises files to an information protection solution is important in a hybrid scenario and when migrating into the cloud configurations.

### Requirements and best practices for the unified labeling scanner
The Azure Information Protection unified labeling scanner scans and protects files in on-premises environments like NAS storages, file shares, and local SharePoint servers.
<img width="476" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/088d12a4-bac5-45a4-8032-4d5fed0fed90">

The table below lists locations where it's possible to scan with the Unified Labeling Scanner:

<img width="875" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/3afaaa5c-1442-430c-a3bb-07c96ca31688">

### Requirements for the unified labeling scanner
The following requirements must be fulfilled before installing the Unified Labeling Scanner:
* SQL Server database installed (SQL Express for Example)
* The SQL server database stores the labeling information and all information about the scanning process and the files, which are scanned.
* The Unified Labeling Client executable including the Scanner.
* One of the following roles: Compliance administrator or Compliance data administrator or Security administrator permissions or Global administrator.
* A configured Microsoft Entra token.
* Any Windows Server 2016 to Windows Server 2019 with UI.

### Service accounts needed
<img width="876" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/fec43feb-4450-4138-bd32-dc21163291b2">

## Configure on-premises labeling for the Unified Labeling Scanner
The installation and configuration of the Unified Labeling Scanner is done from the AIPService PowerShell module on a server that will act as the Unified Labeling Scanner in an environment.

### Installation of the unified labeling scanner
After fulfilling the requirements like service accounts and a SQL Server instance, it´s possible to install the Unified Labeling Scanner in the following steps:

* Install and sign into a Windows Server computer or VM.
* Install the Unified Labeling Client on the machine.
* Run the Windows PowerShell as local administrator in an elevated command shell.
* Run the cmdlet from the AIPService PowerShell module to install the AIP Scanner:

      Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
* Verify that the service is now installed by using Administrative Tools > Services. The installed service is named Azure Information Protection Scanner and is configured to run by using the scanner service account that you created.
* You can control the installation and operation in the Task Manager of the Windows Server, which is the host for the scanner.

### Operational scenarios for the unified labeling scanner

<img width="889" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/3c76ec82-6969-4cbf-8284-b1a21dd234d4">

## Apply protections and restrictions to email and files

When you label an email message that has attachments, the attachments don't inherit the label with one exception. When the label you apply to the email message applies encryption.

### Applying protections to files
When a file is protected with a sensitivity label, the protection is sensitive at the file level. Even if the file's storage location changes or is shared via email or other sharing tools; the file remains protected.

**IMPORTANT!** Encryption of a file and access restrictions are connected. Without encryption it´s not possible to restrict access.

## Monitor label performance using label analytics
Applying a label to a file, an email, a SharePoint Site, or a Microsoft Team is a great option to control access and sharing options.

### Pulling a report
The Organizational data of this dashboard provides an overview of the DLP matches that occurred in SharePoint, OneDrive, Exchange Online, or Microsoft Teams.

The reports in the Reports area are based on the organizational level information. For reports in detail and on a user level, please choose Microsoft Defender for Apps or the Data classification area with the Content explorer and the Activity explorer.

### Planning log analytics
To start log analytics, you must create a Log Analytics workspace

### Roles required for log analytics
* To create your Log Analytics workspace or to create custom queries, you need one of the following roles:
  * Azure Information Protection administrator
  * Security administrator
  * Compliance administrator
  * Compliance data administrator
  * Global administrator
* After the workspace has been created, you can then use the following roles with lower permissions to view the data collected:
  * Security reader
  * Global reader
* To create the workspace or to create custom queries, you need one of the following:
  * Log Analytics Contributor
  * Contributor
  * Owner
* After the workspace has been created, you can then use one of the following roles with lower permissions to view the data collected:
  * Log Analytics Reader
  * Reader










