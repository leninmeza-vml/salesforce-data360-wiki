# Set Up Your Policy Frameworks

## Learning Objectives

After completing this unit, you’ll be able to:

*   Compare access, masking, and record-level security (RLS) policies and decide when to use each.  
    
*   Use tags and classifications as attributes in attribute-based access control (ABAC) policies.  
    

## Build the Right Policy Mix

Once data is classified, the next step is to control how it’s accessed. This is where policies come in. Policies define who can see data, how much they can see, and under what conditions they can see it. A well-designed policy framework balances security and usability to keep data safe without slowing down business operations.

### Choose the Right Type of Policy

The model that powers policy-based governance in Data 360 is attribute-based access control (ABAC). This flexible model grants or denies access based on a combination of user attributes like department or role and data attributes like the tags and classifications you applied. This is a fundamental shift away from rigid, role-based controls, allowing you to define your business intent in a declarative way.

At Northern Trail Outfitters (NTO), the data team uses a combination of policies to protect customer data.

*   **Data access policies:** These control who can access data at the object, field, and record level. This is the primary tool for restricting data visibility. For example, granting access to objects tagged Wealth Management Data only to users in the Wealth Management department.  
    
*   **Dynamic data masking policies:** These protect sensitive information by obscuring it for unauthorized users at query time. For example, showing only the last four digits of a Social Security Number to a service agent.  
    

When creating policies, it’s crucial to understand the rule of precedence: a deny policy always overrides an allow policy.

### Use Tags and Classifications in Policies

Because NTO tagged its data, they can now use those tags as policy attributes in an ABAC policy. The tags act as conditions that determine who gets access to specific data. When a policy runs, it checks the tag values on each data object and applies the appropriate access rule.

Here’s an example.

| **Tag** | Financial Data.Account Info |
| --- | --- |
| **Access Policy Rule** | Deny access to any user who doesn’t have the Finance Team User permission. |

This approach keeps NTO’s policies flexible and scalable. If the team later tags a new field with financial or account-related data, the same tag automatically applies the policy without any extra setup. This helps NTO keep its data protected and policies consistent as the data model grows.

### Avoid Policy Overload

More policies aren't always better. Overly restrictive rules can frustrate users and lead to workarounds that defeat the purpose of governance. Strike a balance between security and usability.

NTO’s data stewards follow these best practices.

*   **Keep policies simple:** Complex conditions are harder to maintain and troubleshoot.  
    
*   **Avoid duplication:** Reuse tags, categories, and attributes where possible.  
    
*   **Test policies early:** Make sure they work with real user roles before rolling out to everyone.  
    

## Scenario: NTO Puts It into Practice

NTO applies three layers of policies for protection.

*   **ABAC policy:** Marketing users only see customers who opted in for promotions.  
    
*   **Dynamic masking policy:** Contractors in the call center see masked email addresses but still handle cases efficiently.  
    
*   **RLS policy:** Regional managers see only their own store’s data.  
    

This layered approach keeps sensitive data safe while allowing every team to work without friction.

## Resources

*   [_Salesforce Help_: Policy-Based Governance in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_policy_based_governance_dg.htm&type=5)

## Unit's quiz:

**Question 1:** A user is subject to Policy A (allows) and Policy B (denies). What is the effective permission?
**Answer: B – Denied.**
The unit states this clearly: "a deny policy always overrides an allow policy." It doesn't matter which policy was created first or what department the user belongs to — the deny wins.

**Question 2:** You want users to see the customer record but hide the Credit_Card_Number__c field value. Which policy type should you use?
**Answer: C – A dynamic data masking policy.**
This is the exact use case described in the unit: masking policies "protect sensitive information by obscuring it for unauthorized users at query time," like showing only the last four digits of a sensitive number. The record remains visible — only the field value is hidden.