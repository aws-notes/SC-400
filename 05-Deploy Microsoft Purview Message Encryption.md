# Deploy Microsoft Purview Message Encryption 
**Learning objectives**
* Configure Microsoft Purview Message Encryption for end users
* Implement Microsoft Purview Advanced Message Encryption

## Implement Microsoft Purview Message Encryption

Administrators Must review their tenant settings for information rights management (IRM) features and OME settings before activating the encryption system for all users.

### Verify information rights management functionality
Validate configuration of information rights management - IRM

    "*Get-IRMConfiguration | fl AzureRMSLicensingEnabled*"

Validate configuration of Office Messege Enctption - OME

    "*Set-IRMConfiguration -AzureRMSLicensingEnabled:$True*"

### Implement custom Office Message Encryption settings

The default template for all users is named "OME Configuration"
* **Microsoft Purview Message Encryption**  -  allows only a single template,
* **Microsoft Purview Advanced Message Encryption** - provides more flexibility with multiple branding templates for different purposes.

### OME branding templates
Customized company branding templates control the look of an organization's email messages and the encryption portal.
* Introductory text
* Disclaimer text (TEST123)
* URL for Your organization's privacy statement
* Text in the encrypted message portal
* Logo that appears in the email message and encrypted message portal, or whether to use a logo at all
* Background color in the email message and encrypted message portal

<img width="591" alt="Screen Shot 2024-02-18 at 9 08 06 PM" src="https://github.com/aws-notes/SC-400/assets/78312587/7128ac79-2cd5-4d68-95d0-f4a8ebe5b463">



