Get Started with Data Cloud One
===============================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Identify different possible Data Cloud One org architectures.  
    
*   Understand the first steps to setting up Data Cloud One.  
    

Plan Data 360 Architecture Strategy
-----------------------------------

As you review Data Cloud One, start by walking through some considerations and scenarios. Depending on what your current org architecture is, you might have a different set up process. To reduce any downstream issues, first identify your home org and companion org before setting up Data Cloud One.

Here are three possible scenarios your company might be working with. All three cases assume that you don’t have data residency concerns to work around, or that all orgs are already provisioned in the same geographical region.

#### Scenario 1: Multiple Orgs Without Data 360

If your company doesn’t have Data 360 on any org yet, you can choose whichever org you’d like to be the Data 360 home org and whichever org(s) you’d like to be the companion org(s).

#### Scenario 2: Multiple Orgs but Only One Org with Data 360

If you have Data 360 provisioned on one org, then that org can serve as the home org. Orgs without Data 360 can be connected as companion orgs.

For example, Northern Trail Outfitter’s Sales org has Data 360, while its Marketing and Customer Service orgs don’t. NTO designates the Sales org with Data 360 to be the home org and designates the orgs without Data 360 to be companion orgs.

#### Scenario 3: Multiple Orgs with Data 360

If you have multiple orgs with Data 360, you can choose one org to become the home org, and designate the rest as companion orgs. You can keep Data 360 on your designated home org, and [convert the other orgs to companion orgs](https://help.salesforce.com/s/articleView?id=data.c360_a_prepare_home_org_for_dcone.htm&type=5) by deprovisioning Data 360.

For example, NTO’s Operations, Materials Research, and Sporting Goods Retail orgs all have Data 360 on them, but NTO only wants one Data 360 home org. NTO chooses one of its orgs, the Operations org, to be its Data 360 home org. That org maintains its Data 360 license. For the rest of its orgs, NTO can deprovision Data 360 so that those orgs can become companion orgs.

Because deprovisioning requires the org data and metadata to be deleted, NTO moves the data into its Data 360 home org and use a data kit to move the metadata as well. NTO also carefully evaluates any features that are dependent on that Data 360 instance, and works to connect those features to its new home org instead.

Best Practices and Considerations
---------------------------------

Keep these best practices in mind when considering Data Cloud One.

*   **Data Residency:** Consult your legal department before connecting orgs across different regions. All data in companion orgs becomes resident in the region of the home org, which could create data residency issues.  
    
*   **Growth:** Confirm that your long-term growth objectives support the decision to implement a single Data 360 instance.  
    
*   **Architecture:** Assess whether all orgs require complete control over their data and Data 360 configurations. If so, creating multiple Data 360 orgs is advisable. However, if you want to centralize control across orgs and minimize data silos, connect multiple orgs to a single Data 360.  
    
*   **Companion Connections:** Every home org has a maximum number of free companion-connected orgs it can have**.** If they reach the maximum, you might want to add Additional Connection licenses to the home org to extend their maximum.  
    
*   **Deprovisioning:** Deprovisioning Data 360, or converting a Data 360 home org to a companion org, can take months, and can lead to data loss or service disruption. Contact Salesforce Customer Support for timeline information. For more information, see [Convert a Data 360 Home Org to a Data Cloud One Companion Org](https://help.salesforce.com/s/articleView?id=data.c360_a_prepare_home_org_for_dcone.htm&type=5) in Salesforce Help.  
    

Set Up Data Cloud One
---------------------

Now that you thought about your Data 360 architecture strategy and identified a home org and companion orgs, you’re ready to set up Data Cloud One.

![Corresponding flowchart of information showing the steps to setting up Data Cloud One.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-one-quick-look/get-started-with-data-cloud-one/images/3ec4ba5e804d41ab616a27bde020f687_kix.jzncfj7q12kq.png)

Here are the steps needed to set up Data Cloud One.

1.  Add the free Data Cloud One Companion Org SKU to each of the companion orgs.  
    
2.  Connect the companion orgs to the home org.  
    
3.  From the home org, share data spaces to the companion orgs.  
    
4.  In the companion org, grant users access to Data Cloud One based on data compliance and governance needs.  
    

The Data Cloud One app appears in NTO’s companion orgs as soon as the companion connection is active and the initial metadata sync is completed. Users in companion orgs can now access data from the Data 360 home org and build insights, segments, and prompts with ease.

How It All Works Together
-------------------------

Now, see how all these parts work together with NTO.

Before using Data Cloud One, NTO has one org with Data 360, its single source of truth. NTO connects its Data 360 org to all of its other Salesforce orgs, including its Customer Service org and Sporting Goods Retail org, through standard Salesforce CRM connections.

When NTO decides to adopt Data Cloud One, NTO sets up companion connections from the Data 360 home org to its other Salesforce orgs, which makes these orgs companion orgs. On the home org, system admins or users with the Data 360 architect permission set, can partition its data into data spaces and choose which data spaces to share with each of the companion orgs. Now, users of the companion orgs can use the Data Cloud One app to work in their own data spaces, creating their own segments, insights, and activations, and still access cross-org insights. All with only one Data 360.

Now that NTO’s users can access data from a shared source of truth, it’s so much easier to manage all of its different orgs. NTO’s salespeople can create insights and segments about their leads without messing with the data from Customer Service. And Marketing and Sporting Goods Retail can access cross-org analytics about the same unified customer profiles while creating their own data actions and agent prompts. NTO can even use Agentforce features like Audit Trail and Feedback Logging in its companion orgs.

Just like NTO, with Data Cloud One, you can save time, money, and headaches by optimizing performance and data usage across your orgs.

Resources
---------

*   [_Salesforce Help_: Salesforce CRM Orgs to Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_connect_salesforce_orgs.htm&type=5)
*   ​[_Salesforce Help_: Data 360 Architecture Strategy](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_architecture_strategy.htm&type=5)
*   [_Salesforce Help_: Data Cloud One Companion Connections](https://help.salesforce.com/s/articleView?id=data.c360_a_companion_connections.htm&type=5)
*   ​​[_Salesforce Help_: Set Up a Data Cloud One Companion Connection](https://help.salesforce.com/s/articleView?id=data.c360_a_companion_connection_setup.htm&type=5)

Prueba
------

Para completar esta unidad, debe responder correctamente todas las preguntas de la prueba.

1 When do you have to deprovision Data 360 for Data Cloud One?
A) When you have no Data 360 orgs and want to spin one up
B) When you have one org with Data 360 and one org without Data 360
C) When you have no Salesforce orgs
D) When you want to convert orgs with Data 360 to companion orgs *

2 What step must happen before you can share data spaces from the home org to companion orgs?
A) Add the Data Cloud One Companion Org SKU to each of the companion orgs. *
B) Create segments of customer data.
C) Access Data Cloud One on the companion org.
D) Build calculated insights.
