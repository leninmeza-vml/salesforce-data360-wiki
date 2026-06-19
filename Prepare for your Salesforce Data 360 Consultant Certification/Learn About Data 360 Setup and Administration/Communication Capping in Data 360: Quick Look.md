# Get to Know Communication Capping

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain what Communication Capping in Data 360 is.  
    
*   Identify use cases for Communication Capping.  
    
*   Explain how to configure Communication Capping to achieve a use case.  
    
*   Explain how to activate Communication Capping rules.  
    

## What’s Communication Capping?

Communication Capping is a feature in Data 360 that lets you set caps on communications with customers, leads, and prospects. It helps you comply with regulations, avoid message fatigue, and optimize budgets across lines of business and customer segments.

In this module, you learn some use cases for Communication Capping and how to configure Communication Capping to address your use case.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Communication Capping consumes Data 360 credits. Learn more in [Data 360 Credit Cons](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look)[umption: Quick Look](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look).

## Your Dream Marketing Budget

You’re the marketing director for a financial company that sells insurance policies, mortgages, and credit cards. Your finance department just let you know that the marketing department needs to cut back on spending. As part of your new budget, you decide to set different communication budgets for insurance customers with different net worths, so you can prioritize marketing toward individuals with high net worth.

You want to set different SMS budgets for insurance customers with high net worth (HNW), medium net worth (MNW), and low net worth (LNW). After discussing this with your team and running some numbers, you decide that the sweet spot is 10 SMS messages per day for insurance customers with HNW, 7 SMS messages per day for MNW, and 3 SMS messages per day for LNW.

Sounds great! Your finance department is happy with the proposal. So, how do you implement your budget with Communication Capping?

## Define Parameters and Rules

Communication Capping works by evaluating each member of the audience based on parameters and rules. For your financial services company, first you customize the parameters that represent the company. Then, you create rules that limit SMS messages to insurance customers based on net worth. Rules place limits on a specific combination of parameter values, which constrains communications to that specific group of people. Let’s pause here to further define these terms.

### Parameters

Parameters are the dimensions on which you’re defining communication limits, such as communication channels, lines of business, and net worth categories. You define possible values for the parameters.

Think of parameters as your master data; while the values might change, the parameters themselves don’t. There are two types of parameters: Enterprise and Functional.

| **Parameter Type** | **Description** | **Example Parameters and Values** |
| --- | --- | --- |
| Enterprise Parameters | These are customizable parameters that represent your business model.<br><br>Channels is a required parameter. You can customize the possible values.<br><br>You can also create up to two user-defined parameters that you can customize based on your business and capping strategy. | *   Channels: SMS, Email, WhatsApp, Push  <br>    <br>*   Line of Business: Insurance, Mortgage, Credit Cards  <br>    <br>*   Net Worth Category: HNW, LNW, MNW |
| Functional Parameters | There are two required preset functional parameters that define details about your capping strategy: Frequency and Limit Type.<br><br>Frequency represents how often you communicate with your customers. You can select possible values for frequency.<br><br>Limit type represents the type of limit you’re applying. You can’t customize the possible values for limit type. The possible values are profile and dimension.<br><br>*   Profile limits apply rules to individual profiles. Use these to ensure compliance to regulations and prevent message fatigue. For example, limit emails to 10 per day for any individual customer.  <br>    <br><br>*   Dimension limits apply capping rules to all customers that fit certain parameter values. Use these when managing budgets across multiple parameters. For example, limit emails to 10 per day for all insurance LNW customers. | *   Frequency: Daily, Monthly  <br>    <br>*   Limit Type: Profile, Dimension |

### Rules

Rules are how you define details about a specific capping limit, such as which net-worth category it applies to and for which dates it applies. Ultimately, the rules represent the budgets and compliance regulations of your business.

For example, for your financial services company, you want to set a cap of 10 SMS messages per day in May 2025 for insurance customers with HNW. Here’s the rule you define.

| **Field** | **Description** | **Values** |
| --- | --- | --- |
| Start Date and End Date | Define the time frame when the rule is valid.<br><br>You want to try out a temporary budget in May to see its effectiveness. | 5/1/2025 – 5/30/2025 |
| Limits | Define the maximum number of messages that can be sent. | 10  |
| Parameters | Define which category of the audience the rule applies to. Parameters and possible values will vary. For our example, the parameters are line of business and net worth category. | *   Line of Business: Insurance  <br>    <br>*   Net Worth Category: HNW |
| Frequency | Define how often to apply the rule. | Daily |
| Limit Type | Define the type of limit: profile or dimension. | Dimension |
| Channel | Define the communication channel that the rule applies to. | SMS |

Watch this quick video to see how it’s done!

## Create a Communication Capping Activation Target

There’s one last step. Before you can activate your rule, you need to create a communication capping activation target and map the target to parameters. The available parameters are the enterprise parameters you defined. Choose values for the parameters based on the rule you defined. For example, for your SMS limit for insurance customers with high net-worth, set the Line of Business parameter to Insurance, the Net Worth Category parameter to HNW, and the Channel parameter to SMS.

See the steps in [Create a Communication Capping Activation Target](https://help.salesforce.com/s/articleView?id=sf.c360_a_create_communication_capping_target.htm&type=5).

## Next Steps and Results

With your parameters, rule, and activation target all set up, you’re now ready to activate your rule! Create your customer segments for your campaign and activate them using the communication capping activation target that you created. Continue your learning in [Segmentation in Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation).

With your rule activated, your campaign now excludes and includes profiles based on the rule. In Data Explorer, the CG\_Audience\_Dropped DMO shows you which customers are excluded, and the CG\_Audience\_Qualified DMO shows you which customers are included in the campaign. The CG\_Audience\_Dropped DMO also shows you which rule caused the profile to get dropped in the Reason for drop column. This is useful when you have multiple active rules.

Watch this short video to see these steps in Data 360.

Now you’re ready to implement your own budgets and monitor communication limits with Communication Capping in Data 360!

## Resources

*   [_Salesforce Help_: Capping Communications for B2C Engagements](https://help.salesforce.com/s/articleView?id=data.c360_a_communication_capping.htm&type=5)
*   [_Salesforce Help_: Map Your Capping Communication Activation Targets to Parameters](https://help.salesforce.com/s/articleView?id=sf.c360_a_map_communication_capping__targets_parameters.htm&type=5)

---

Quiz questions:

**Question 1:** What does Communication Capping in Data 360 help you do?

**Answer: A** – Set limits on communications to avoid message fatigue, comply with regulations, and optimize budgets.

This matches the opening definition directly: Communication Capping lets you set caps on communications to comply with regulations, avoid message fatigue, and optimize budgets across lines of business and customer segments.

---

**Question 2:** You want to place a 300 messages per day limit on credit card customers with low net worth. What should you select as the limit, parameters, and frequency?

**Answer: B** – 300, Credit Cards and LNW, Daily.

Breaking it down:
- **Limit = 300** (the maximum messages allowed)
- **Parameters = Credit Cards and LNW** (the line of business is Credit Cards, and the net worth category is Low Net Worth)
- **Frequency = Daily** (since the cap is "per day")

The other options are wrong because A uses Insurance/HNW, C uses Weekly instead of Daily, and D uses HNW instead of LNW.