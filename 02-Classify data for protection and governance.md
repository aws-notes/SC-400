## Data classification overview
* **Overview. Provides** snapshots of how sensitive information types and labels are being used.
* **Content explorer** Explore the email and documents in your organization that contain sensitive information or have labels applied.
* **Activity explorer** Review activity related to content containing sensitive info or has labels applied, such as what labels were changed, files were modified, and more.
* **Sensitive info types(SITs)** Manage the built-in and custom sensitive information types available to classify data.
* **Trainable classifiers** Manage the classifiers used to identify content based on what the item is, not by the elements in the item.
## Classify data using sensitive information types
# Built-in sensitive information types
*  social security numbers
*  credit card numbers
*  email addresses
# Named entity sensitive information types
*  person names
*  physical addresses
*  Medical Info
# Custom sensitive information types
* Custom
# Exact data match sensitive information types
* Exact data match (EDM)-based SITs are built from scratch. EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.
# Fundamental parts of a sensitive information type
Every sensitive information type consists of:
* **Name:** A descriptive name that identifies the sensitive information type.
* **Description**
* **Pattern:** specific characteristics or criteria that indicate the presence of sensitive information.
  * **Primary element** – regular expression, checksum validation, a keyword list, a keyword dictionary, or a function.
  * **Supporting element** – an element that acts as supporting evidence that help in increasing the confidence of the match. Regular expression with or without a checksum validation, keyword list, keyword dictionary.
  * **Confidence Level** - confidence levels (high, medium, low) reflect how much supporting evidence is detected along with the primary element.
  * **Proximity** – the number of characters between the primary and supporting elements.
# Creating custom sensitive information types
* Use the UI
* The EDM -  Exact Data Match (EDM)-based classification.
* Powershell
* # Classify data using trainable classifiers
Types of classifiers
* **Pre-Trained Classifiers:** Microsoft provides pretrained classifiers that are ready to use without training. These classifiers appear with the status of Ready to use.
* **Custom Trainable Classifiers:** If the pretrained classifiers don't cover your needs, you can create and train your own.
**1 Seed:** Prepare your sample data and create the trainable classifier.
* Prepare sample data - You need at least 50 and as many as 500 samples
* Create trainable classifier - Within 24 hours, the trainable classifier processes the seed data and builds a prediction model.(in progress white processing)
**2 Test:** Prepare test data, test the predictive model, and evaluate the results.
* Prepare test data - least 200 items, with a maximum limit of 10,000. manually review the results
* Test predictive model: - Add data, can take up to a hour. done when "Ready to review" is available
* Evaluate predictions - Review items to improve the classifier accuracy step's status is Ready to review when it's ready for you to conduct the evaluation.
* Not available - "Not available" because not enough test content has been evaluated yet.
* Once you have reviewed enough items and accuracy reaches at least 70%, you can publish the trainable classifier
**3 Publish:** Make the trainable classifier available for use in your compliance solutions.
* The status for a published trainable classifier is Ready to use.



