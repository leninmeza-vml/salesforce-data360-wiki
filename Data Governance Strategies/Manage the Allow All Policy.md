# Manage the Allow All Policy

## Learning Objectives

After completing this unit, you'll be able to:

*   Explain the difference in default governance posture between new and existing Data 360 orgs.  
    
*   Describe the purpose and function of the allow all policy.  
    
*   Develop a strategic plan for managing the allow all policy to establish a secure baseline.  
    

## Understand the Default Data Governance Posture in Data 360

To avoid disrupting business, all new and existing Data 360 orgs start with a preactivated Allow All policy. This policy grants users access to all objects within their assigned data spaces, mirroring the behavior before granular governance controls were introduced. For example, an established organization that was already using Data 360 continues to operate smoothly with the Allow All policy in place while admins design more targeted access policies. A new organization setting up Data 360 for the first time also begins with the same Allow All policy, allowing users to explore and understand their data model before applying more restrictive governance rules.

## The Allow All Policy: Function and Risk

The allow all policy serves as a bridge, ensuring continuity of access while you plan your transition to a granular, policy-based model. However, its presence has critical implications.

As long as the allow all policy is active, it creates a baseline of universal access. This means that any granular allow policies you create will have no effect, because the allow all policy already grants access. Only deny policies will be enforced, as they always take precedence.

This means the primary long-term goal for an admin at NTO is to plan for the eventual deletion of the allow all policy. Only after it’s deletion will granular allow policies begin to function, enabling a true least privilege access model.

## A Strategic Approach to Deactivation

Simply deleting the allow all policy without a plan could instantly revoke all data access for every user, bringing business operations to a standstill. It’s crucial to treat this policy deletion as a strategic project.

NTO’s data team should follow this phased approach.

*   **Phase 1: Audit and Design.** Do not delete the policy yet. First, inventory all current data access patterns to understand who needs access to what. Use this information to design your new set of granular ABAC Allow policies.  
    
*   **Phase 2: Build and Test.** With the allow all policy still active, build all of your new granular Allow and Deny policies. You can build them without impacting current users.  
    
*   **Phase 3: Communicate.** Inform your users about the upcoming change in how data access is managed. Schedule a maintenance window for the transition.  
    
*   **Phase 4: Execute the Switch.** During the scheduled window, deactivate and delete the allow all policy, then immediately activate all of your new, granular ABAC policies.  
    
*   **Phase 5: Validate and Support.** After the switch, work with users to confirm they have the correct level of access and be prepared to troubleshoot as needed.  
    

## Wrap-Up

You’ve now walked through the full governance journey in Data 360: from understanding the strategic importance of governance to designing a scalable tagging framework to enforcing access with intelligent policies and, finally, to managing your org’s default security posture. You’ve explored how governance in Data 360 protects sensitive information, builds customer trust, and supports compliance—while still enabling your teams to work productively. With these concepts, you can create governance frameworks that protect sensitive data, meet compliance needs, and keep your business running smoothly.

## Resources

*   [_Salesforce Help_: Assign Data Access](https://help.salesforce.com/s/articleView?id=data.c360_a_dc_access.htm&type=5)
*   [_Salesforce Help_: Data Governance Considerations](https://help.salesforce.com/s/articleView?id=data.c360_a_before_you_begin_data_gov.htm&type=5)

## Unit's quiz:

**Question 1:** Sales users still have access to objects they shouldn't, and the new ABAC allow policy seems to have no effect. What's the most likely cause?
**Answer: C – The default allow all policy is still active.**
The unit explains this directly: while the allow all policy is active, any granular allow policies you create have no effect because universal access is already granted. Only deny policies cut through it.

**Question 2:** Why is it risky to immediately delete the allow all policy without a plan?
**Answer: C – It could instantly revoke data access for all users, disrupting business operations.**
The unit warns explicitly that deleting the allow all policy without preparation "could instantly revoke all data access for every user, bringing business operations to a standstill" — which is exactly why the phased 5-step approach is recommended.
