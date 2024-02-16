# Create and manage sensitive information types 
## Compare built-in versus custom sensitive information types
### Sensitive information type parts
* **Primary pattern** - regular expression (RegEx), but it can also be achieved through a list of keywords.
* **Additional evidence** - also known as supporting or corroborative evidence. Regex that looks for keywords
* **Character proximity** - the number of characters between the primary and supporting elements.
* **Confidence level** - Confidence levels (low, medium, high) based on amount of supporting evidance
### Custom sensitive information type features
The special features of custom sensitive information types include:
* Exact Data Match (EDM)-based classification
* Document Fingerprinting
* Keyword dictionaries
  
| Feature    | What is it?	 |When to use it?	|Recommendation|
| -------- | ------- |------- |------- |
| **Exact Data Match (EDM)-based classification**	  | creates DB with custom sensitive information types for exact values, enables daily refreshes, contain up to 100 million rows of data.|large quantities of sensitive information need to be matched daily| large amounts of personal information
| **Document Fingerprinting**	 | Converts a standard form into a sensitive information type. |A document fingerprint can be created on a blank document template|block any outbound mail or shared documents matching that fingerprint are detected|
| **Keyword dictionaries**	    | Keyword dictionaries offer an easy way to manage reused keyword lists for matching company information on a large scale. They support up to 1 MB of keywords in any language.  |  help identify generic content like healthcare-related communication (ICD classification) or inappropriate language.|Keyword dictionaries are less accurate than EDM-based classification. Useful for detecting industry-specific terms before sharing with internal or external parties and enforcing company guidelines.|

1. Start with the built-in sensitive information types for general protection against data loss of most common sensitive data.
2. Then organizations should analyze their individual needs to protect specific data by creating custom sensitive information types.
3. Then use the advanced features of custom sensitive information types, to increase accuracy and simplify management.

### sensitive information types and what they're composed of
* **Regular expressions:** Patterns that match text. Microsoft 365 SITs use the Boost.RegEx 5.1.3 engine.
* **Keyword lists:** Pre-made or custom lists used in defining SITs.
* **Keyword dictionaries:** Collections of terms for SITs.
* **SIT functions:** Features that enhance SIT identification.
* **Confidence levels:** Indicators that assess the probability that identified information is sensitive based on the presence of supporting details. More supporting evidence increases the confidence level.
* **SIT limits:** Restrictions on SIT configurations.

## Create and manage custom sensitive information types
There are two ways to create a new sensitive information type:
* from scratch where you fully define all elements
* copy and modify an existing sensitive information type

| Feature    | What is it?	 |
| -------- | ------- |
|Maximum number of custom SITs created through the Microsoft Purview compliance portal|	500|
Maximum length of regular expression |	1024 characters|
Maximum length for a given term in a keyword list |	50 characters
Maximum number of terms in keyword list	| 2048
Maximum number of distinct regexes per SIT	| 20
Maximum size of a keyword dictionary (post compression)	| 1MB (~1,000,000 characters)
Maximum number of keyword dictionary based SITs in a tenant	| 50

### Fundamental parts of a sensitive information type
* **Name:** A descriptive name that identifies the sensitive information type.
* **Description**
* **Pattern:** specific characteristics or criteria that indicate the presence of sensitive information.
  * **Primary element** – regular expression, checksum validation, a keyword list, a keyword dictionary, or a function.
  * **Supporting element** – an element that acts as supporting evidence that help in increasing the confidence of the match. Regular expression with or without a checksum validation, keyword list, keyword dictionary.
  * **Confidence Level** - confidence levels (high, medium, low) reflect how much supporting evidence is detected along with the primary element.
  * **Proximity** – the number of characters between the primary and supporting elements.
 
### Create a custom sensitive information type
* **Identify your data:** Understand what unique data needs protection.
* **Access the Microsoft Purview compliance portal:** Use the Microsoft Purview compliance portal to create SITs.
* **Define your SIT:** Choose to start from scratch or modify an existing SIT. Include patterns like regular expressions and keyword lists that match your data.
* **Test your SIT:** Run simulations to ensure your SIT accurately identifies the intended data.
* **Deploy and monitor:** Implement your SIT in data loss prevention policies and monitor its efficacy.

## Describe custom sensitive information types with exact data match
Fingerprinting - Exact data match (EDM) allows you to create a sensitive information type (SIT) that uses exact data values for identifying and protecting sensitive information. With EDM, you can ensure your SIT
* **Is easily** updated: Quickly adapt to changes in your sensitive data.
* **Reduces false positives:** Accurately identify the correct information, minimizing mistakes.
* **Fits structured data:** Works well with organized data sets.
* **Ensures privacy:** Keeps sensitive data secure and private, even from Microsoft.
* **Integrates across services:** Functions with a range of Microsoft cloud services for better data governance.

create custom sensitive types that match exact values from a database, which can hold up to 100 million rows of data.
refreshed daily 
can have DLP policy for Microsoft Purview Data Loss Prevention policies or Microsoft Cloud App Security file policies.

## What's different in an EDM SIT
### **Schema**
* The name of the schema, later referred to as the DataStore.
* The field names that your sensitive information source table contains. Each schema field corresponds directly to a column in your table.
* Which fields are searchable.
* A configurable match, which is an adjustable parameter for refining your search, like ignoring case sensitivity or punctuation in the data you're searching for.

### **Sensitive information source table**
The sensitive information source table contains the values that the EDM SIT looks for. It contains:
* Column headers represent the field names.
* Rows correspond to individual records.
* Each cell holds the specific value for its record and field.

### **Rule package**
Every SIT has a rule package. You use the rule package in an EDM SIT to define:
* **Matches** specify the field used as the primary element for exact lookups. It can be a regular expression with or without a checksum validation, a keyword list, a keyword dictionary, or a function.
* **Classification** determines the specific sensitive information type match criteria that triggers a search using EDM.
* **Supporting elements** are extra pieces of data that, when found near the primary data, can be a regular expression with or without a checksum validation, keyword list, or a keyword dictionary
* **Confidence** high to low, based on the amount of supporting evidence found with the primary element.
* **Proximity** refers to the distance, in characters, between the primary and supporting elements.

### **You supply your own schema and data**
 You encrypt them via a hash function that includes a randomly generated or self-supplied salt value. Only the hashed values are uploaded to the service, so your sensitive data is never in the open.

### **Primary and secondary support elements - EDM SITs**
* **Primary** - specific information you're looking to identify - email, name, DOB
* **secondary** - Secondary elements reinforce the identification of the primary element as sensitive. keywords, keyword lists

### **How matching works**
comparison is done by comparing one-way cryptographic hashes against the sensitive information source table

### Create an EDM-based SIT
* **Simplified workflow:** The creation of schemas and SITs is now a unified process, reducing steps and providing clear directions for mapping data elements to the system’s predefined SITs. This integrated approach also automatically sets the appropriate confidence levels for the detection rules, making the setup faster and more user-friendly.
* **Automated schema and SIT creation:** By uploading a non-sensitive sample data file, the system can auto-generate a schema, then suggest the best SITs to link with your primary data fields. This automation eliminates the need to manually input schema details and helps ensure that the SITs are correctly matched, leading to more accurate data protection.
* **Additional guardrails to ensure better performance:** The new system alerts you when a primary field is connected to a SIT that's too broad. This measure helps avoid potentially irrelevant matches that could slow down the process. These proactive notifications are designed to help maintain optimal system performance by steering you away from configurations that might lead to inefficiencies or errors in data matching.

 ![image](https://github.com/aws-notes/SC-400/assets/78312587/77e48d20-a0b9-43fe-9a5e-af39d54d4428)

### The classic EDM experience

* **Multiple SITs per schema:** The classic experience allows for multiple SITs to be mapped to a single schema, which isn't possible in the new experience.
* **Managing more than 10 SITs:** If you need to create or manage more than 10 SITs, you need to use the classic experience. Because you can map multiple EDM SITs to the same schema, you can have more than 10 EDM SITs. * Attempting to create an eleventh schema with the new experience generates an error.
* **Custom schema names:** The classic experience lets you specify custom names for your EDM schemas, unlike the new experience that auto-generates schema names.
* **Editing existing schemas:** If you need to edit schemas created in the classic experience or uploaded via PowerShell, you must use the classic experience, as the new experience doesn't support this functionality.

![image](https://github.com/aws-notes/SC-400/assets/78312587/bf77d071-7175-473e-bdf6-b33a2f31bb8e)

![image](https://github.com/aws-notes/SC-400/assets/78312587/e24de564-61ae-4202-9f3d-cf039830f2ad)



