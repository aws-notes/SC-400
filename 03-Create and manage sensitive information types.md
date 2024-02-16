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
| Exact Data Match (EDM)-based classification	  | creates DB with custom sensitive information types for exact values, enables daily refreshes, contain up to 100 million rows of data.|large quantities of sensitive information need to be matched daily| large amounts of personal information
| Document Fingerprinting	 | Converts a standard form into a sensitive information type. |A document fingerprint can be created on a blank document template|block any outbound mail or shared documents matching that fingerprint are detected|
| Keyword dictionaries	    | Keyword dictionaries offer an easy way to manage reused keyword lists for matching company information on a large scale. They support up to 1 MB of keywords in any language.  |  help identify generic content like healthcare-related communication (ICD classification) or inappropriate language.|Keyword dictionaries are less accurate than EDM-based classification. Useful for detecting industry-specific terms before sharing with internal or external parties and enforcing company guidelines.|

| Feature        | What is it?           | When to use it?	  |Recommendation  |
| ------------- |:-------------:| -----:| -----:|
| Exact Data Match (EDM)-based classification     |  creates DB with custom sensitive information types for exact values, enables daily refreshes, contain up to 100 million rows of data. | large quantities of sensitive information need to be matched daily | large amounts of personal information |
| col 2 is      | centered      |   $12 | $1600 |
| zebra stripes | are neat      |    $1 | $1600 |

1. Start with the built-in sensitive information types for general protection against data loss of most common sensitive data.
2. Then organizations should analyze their individual needs to protect specific data by creating custom sensitive information types.
3. Then use the advanced features of custom sensitive information types, to increase accuracy and simplify management.
