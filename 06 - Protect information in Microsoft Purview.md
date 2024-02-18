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







------

data stuertship

https://learn.microsoft.com/en-us/purview/concept-insights




