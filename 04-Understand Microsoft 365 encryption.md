# Understand Microsoft 365 encryption#
Learning objectives
* Explain how encryption mitigates the risk of unauthorized data disclosure.
* Describe Microsoft data-at-rest and data-in-transit encryption solutions.
* Explain how Microsoft 365 implements service encryption to protect customer data at the application layer.
* Understand the differences between Microsoft managed keys and customer managed keys for use with service encryption.

## Introduction to Microsoft 365 encryption

### BitLocker volume level encryption
* Disk sectors are encrypted with a Full Volume Encryption Key (FVEK)
* FVEK itself encrypted with the Volume Master Key (VMK)
* which in turn is bound to the Trusted Platform Module (TPM)

![image](https://github.com/aws-notes/SC-400/assets/78312587/3ea9cdb3-ce4f-4dab-bc4d-015e2c154b8c)

* **BitLocker-managed keys,** which are generally short-lived and tied to the lifetime of an operating system instance installed on a server or to a given disk. These keys are deleted and reset during server reinstallation or disk formatting.
* **BitLocker recovery keys,** which are managed outside of BitLocker, are used for disk decryption. BitLocker uses recovery keys for the scenario in which an operating system is reinstalled, and encrypted data disks already exist. Recovery keys are also used by Managed Availability monitoring probes in Exchange Online where a responder may need to unlock a disk.

### Service level encryption
* Exchange Online - BitLocker to encrypt all mailbox data
* Microsoft Teams
* SharePoint Online - protected by unique per-file keys
* OneDrive

Customers have two options for service level encryption key management:
* **Microsoft Managed Keys** – In the default implementation
* **Customer Keys** – This option allows customers to use their own root keys to encrypt customer data

### Understand service encryption in Microsoft Purview

![image](https://github.com/aws-notes/SC-400/assets/78312587/70b143e9-ba29-475b-8843-45fa5a8ab4fa)

The left side of diagram above outlines the key hierarchy for Exchange Online, which shows how two Microsoft Managed RSA keys and one equivalent AES-256 availability key are used to protect the Data Encryption Policy Key, which in turn protects the Mailbox Key used to encrypt mailboxes in Exchange Online. | The right side of the diagram shows the key hierarchy for SharePoint Online, OneDrive for Business, and Microsoft Teams files, which use SQL Transparent Data Encryption to protect File Chunk Encryption Keys for SQL Databases.


