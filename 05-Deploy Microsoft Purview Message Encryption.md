# Deploy Microsoft Purview Message Encryption 
**Learning objectives**
* Configure Microsoft Purview Message Encryption for end users
* Implement Microsoft Purview Advanced Message Encryption

## Implement Microsoft Purview Message Encryption

Administrators Must review their tenant settings for information rights management (IRM) features and OME settings before activating the encryption system for all users.

### Verify information rights management functionality
Validate configuration of information rights management - IRM

  "*Get-IRMConfiguration | fl AzureRMSLicensingEnabled*"

Validate configuration of O365 Messege Enctption - OME

  "*Set-IRMConfiguration -AzureRMSLicensingEnabled:$True*"


