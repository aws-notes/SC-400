# Protect information in Microsoft Purview
Learning objectives
* Discuss the information protection solution and its benefits.
* List the customer scenarios the information protection solution addresses.
* Describe the information protection configuration process.
* Explain what users will experience when the solution is implemented.
* Articulate deployment and adoption best practices.

## Configure sensitivity labels
Here are the steps involved in sensitivity label configuration:
* Name and description
* Encryption
* Content marking
* Site and group settings (if preview enabled)
* Auto-labeling for Office apps
* Review your settings

<img width="768" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/797d88a2-0690-41f6-a10a-c1359efd418f">

### Step 1: Name & Description
* Name
* Tooltip
* Description

### Step 2: Encryption
Encryption uses the Azure Rights Management Service (Azure RMS) from Azure Information Protection.

<img width="526" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/08f36b00-a995-49d9-b839-5381dc716681">

* **None** - no encryption
* **Remove** - remove encryption
* **Apply**  
  * **Assign permissions now** - Enforced when the label is applied to email and Office files. Selecting this option results in the additional configuration listed.
    
    * **User access to content expires** 
       * Never
       * On a specific date
       * Number of days after the label is applied.
    * **Allow offline access** -
       * Never
       * On a specific date
       * number of days.
    * **Assign permissions to specific users and groups** - You can choose from existing permissions (such as Co-Owner, Co-Author, and Reviewer) or customize them to meet your needs

<img width="517" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/44305139-c9ba-410a-8d52-40845215b4f6">

  * **Let users assign permissions** - Actions vary based on if the label is applied in Outlook or if it's applied in Word, PowerPoint, and Excel. Selecting this option results in additional configuration choices presented in the next list. You must choose at least one option.
   * **Outlook** The restrictions enforced are equivalent to the Don't Forward option.
   * **Word, PowerPoint, Excel.** The user is prompted to specify permissions.

<img width="367" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/504afad1-784a-4729-9e51-714a91f3d134">

### Step 3: Content marking
* Watermark (documents only)
* Header
* Footer

<img width="238" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/4b3608b0-7aa2-42cf-ab0b-162e094889dd">

### Step 4: Site and group settings (preview)
* Microsoft 365 groups
* SharePoint sites
* Microsoft Teams

**Privacy of Microsoft 365 group-connected team sites**
Determine who can access a Microsoft 365 group or SharePoint site.
* None - Let user choose who can access the site. Default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.
* Public - Anyone in the organization can access the site.
* Private - Only members can access the site.

<img width="547" alt="image" src="https://github.com/aws-notes/SC-400/assets/78312587/dc5e23c9-38de-42fd-99d7-caee460454e5">

### Step 5: Auto-labeling for Office apps
Client-side auto-labeling - Azure Information Protection unified labeling client
Service-side labeling - Content already saved (in SharePoint Online or OneDrive)

### Step 6: Review your settings

## Configure sensitivity label policies
* Step 1: Choose labels to publish
  * must be existing label
* Step 2: Publish to users and groups
  * Consider publishing the label to a test group with a few members first
* Step 3: Policy settings
  * Default label
  * Justification for removal
  * Require label
  * Custom help
* Step 4: Name and description
* Step 5: Review your settings

## Configure auto-labeling policies
Services rather than applications apply this labeling

Liceancing needed 
* Microsoft 365 E5
* Microsoft 365 E5 Compliance
* Microsoft 365 E5 Information Protection and Governance

### Step 1: Info to label
* Start with a policy template or create a custom policy
### Step 2: Name
### Step 3: Choose locations
Select which locations and users or groups
* Exchange
* SharePoint
* OneDrive
### Step 4: Policy rules
* Define policy settings "Find content that contains"
  * For Content contains sensitive info types, you can select both built-in and custom sensitive information types.
  *For the Content is shared option, you can choose only with people inside my organization or with people outside my organization.
* Advanced settings
  * Sender IP address is
  * Recipient domain is
  * Recipient is
  * Attachment's file extension is
  * Attachment is password protected
  * Document property is
  * Any email attachment's content couldn't be scanned
  * Any email attachment's content didn't complete scanning
### Step 5: Label
 * Choose a label to auto-apply
### Step 6: Policy mode
* Run policy in simulation mode now
* * Run policy in simulation mode later
* Leave policy turned off
### Step 7: Finish
* Allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.

### Simulation mode
Policy Simulator is designed to:
Help you understand the impact of the policy and tune it for accuracy and scalability.
Provide insights on the estimated length of time required to deploy a policy at scale.
Prevent deployment of ineffective or bad policies and help minimize incident management costs.



https://learn.microsoft.com/en-us/training/modules/m365-compliance-information-protect-information/configure-auto-labeling-policies

------

data stuertship

https://learn.microsoft.com/en-us/purview/concept-insights




