# Design Your Governance Strategy

## Learning Objectives

After completing this unit, you’ll be able to:

*   Decide which data should be tagged and classified by sensitivity.  
    
*   Plan taxonomies and hierarchies for scalable, consistent classification.  
    
*   Explain when to use AI-driven tagging and propagation to streamline operations.  
    

## Build a Strong Data Governance Foundation

The first step in data governance is deciding what data needs special treatment. Since not all data is equally sensitive, it’s important to identify and label the information that matters most. This is where tagging and classification come in. When data is tagged correctly, your policies can work more effectively—protecting sensitive data and streamlining compliance so teams focus on trustworthy data.

### Tag and Classify Data by Sensitivity

At Northern Trail Outfitters (NTO), the data team starts by reviewing data from their three main sources.

*   **Online orders:** Includes names, emails, shipping addresses, and payment methods  
    
*   **Retail POS systems:** Includes loyalty program numbers, purchase history, and receipts  
    
*   **Loyalty sign-ups:** Includes customer preferences, birthdates, and consent flags  
    

The team prioritizes tagging for personally identifiable information (PII) like names, phone numbers, and payment details. They also identify transactional data (like purchase history) that needs protection for competitive reasons.

Focus on data that impacts privacy, compliance, or critical decision-making first. Tagging everything is tempting but can add unnecessary overhead.

### Plan a Taxonomy and Hierarchy

Once data is identified, NTO creates a taxonomy—the complete, hierarchical classification of all the tags used in the organization. This master blueprint organizes tags and ensures they are applied consistently everywhere.

Data 360 supports a parent-child tag hierarchy, which structures tags in a logical, multilevel system.

For example:

*   Personal Information (Parent Tag)  
    

*   Email Address (Child Tag)  
    
*   Phone Number (Child Tag)  
    

This structure enables policy inheritance. If you assign a child tag like Email Address to a field, Data 360 automatically applies the parent tag of Personal Information. This ensures that any policies linked to the parent tag are automatically enforced on the field. A clear taxonomy also helps when writing policies—you can apply rules to entire categories rather than tagging fields one at a time.

### Automate Tagging with AI

Manual tagging is feasible for smaller orgs with only a few Data 360 objects, but it doesn’t scale. It’s time-consuming, prone to human error, and even a single misclassification can cause security or compliance issues. As data volumes grow, manual tagging quickly becomes inefficient. Consider using AI tagging to handle repetitive classification at scale, and reserve manual tagging for when you’re just getting started or want to tag a few objects to understand how tags work.

To speed up the process, NTO uses AI-powered tagging and propagation.

*   **AI-driven tagging:** An AI feature called Suggest Tags uses a large language model (LLM) to analyze the metadata of your objects and fields—such as their names and descriptions—and recommends relevant tags. Crucially, this feature does not scan or analyze the actual data in the fields, ensuring customer data remains private. The administrator must still review and approve these suggestions.  
    
*   **Propagation:** This mechanism automatically extends tags from a source data object to its related, downstream objects, like a Unified Individual Profile. It ensures consistency across data sources and prevents governance gaps where sensitive data could otherwise slip through.  
    

This blended approach helps NTO classify data faster without losing control over accuracy.

## Scenario: NTO Puts It into Practice

NTO’s data team uses AI tagging on loyalty data to automatically identify fields like birthdate and email. They confirm the results, then propagate those tags to all related objects across their POS and online order systems.

When they spot an incorrectly tagged field—in this case, a nonsensitive internal code marked as PII—they adjust the tag manually. This blended approach helps them classify faster without losing control over accuracy.

## Resources

*   [_Salesforce Help_: Data Tagging and Classification in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_using_tagging_and_classification_dg.htm&type=5)

## Here are the answers for this unit's quiz:

**Question 1:** What happens if you apply a child tag named Credit Card Number (with parent tag Financial Data) to a field?
**Answer: B – Both the Credit Card Number tag and the Financial Data tag are applied.**
The unit explains that policy inheritance means assigning a child tag automatically applies the parent tag as well, ensuring parent-level policies are enforced.

**Question 2:** The Suggest Tags AI feature analyzes which of the following?
**Answer: B – Object and field metadata, such as names and descriptions.**
The unit is explicit about this: Suggest Tags analyzes metadata like names and descriptions — and importantly, it does *not* scan the actual data in the fields, preserving customer privacy.
