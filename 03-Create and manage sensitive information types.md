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

## sensitive information types and what they're composed of
* **Regular expressions:** Patterns that match text. Microsoft 365 SITs use the Boost.RegEx 5.1.3 engine.
* **Keyword lists:** Pre-made or custom lists used in defining SITs.
* **Keyword dictionaries:** Collections of terms for SITs.
* **SIT functions:** Features that enhance SIT identification.
* **Confidence levels:** Indicators that assess the probability that identified information is sensitive based on the presence of supporting details. More supporting evidence increases the confidence level.
* **SIT limits:** Restrictions on SIT configurations.

### Create and manage custom sensitive information types
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
