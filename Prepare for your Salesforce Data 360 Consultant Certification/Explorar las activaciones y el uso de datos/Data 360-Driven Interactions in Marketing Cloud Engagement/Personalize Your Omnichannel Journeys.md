# Personalize Your Omnichannel Journeys

## Learning Objectives

After completing this unit, you’ll be able to:

*   Stage data in Data 360.  
    
*   Create an omnichannel audience in Data 360.  
    
*   Configure and personalize omnichannel journeys in Marketing Cloud Engagement using email, SMS, and MobilePush.  
    

## It’s Personal

Now that you’ve built a strong foundation, you can create seamless customer experiences by orchestrating and personalizing one journey with all Email, SMS, and MobilePush activities together. 

An omnichannel contact is a person represented by one SubscriberKey in Marketing Cloud Engagement. This SubscriberKey has an associated address for each channel: Email, SMS, and MobilePush. Omnichannel contacts can execute each channel within an omnichannel journey.

If you’ve implemented single-channel contacts in Marketing Cloud Engagement and want to create omnichannel journeys, this is the solution for you. If your Marketing Cloud Engagement Contacts are already configured as omnichannel contacts, congrats! Your Marketing Cloud Engagement SubscriberKeys can natively execute each channel within an omnichannel journey. However, we recommend using Data 360 to further personalize your messaging and points of contact. 

## Consent Is Key

We talked about consent in the first unit, but did you know that email, SMS, and push notification channels have unique consent needs?

**SMS** 

*   Consent is stored at the phone number level (and keyword) and not at the SubscriberKey level.  
    
*   If you configure the SMS activity to Subscribe all contacts to a keyword, native consent is overridden and the contact is opted in.  
    

**Email Only**

*   For each Email activity in the journey, associate a suppression list that prevents sends to the given email address. We recommend this option only for journeys or lists with fewer than 200,000 members.  
    
*   For each Email Activity in the journey, associate a publication list. Before sending an email, Journey Builder checks the publication status associated with the contact to see if they’re subscribed.  
    

**SMS, Email, and Push Combined**

*   Use exit criteria in your journeys to monitor attributes from the contact model that you know are current to represent the person’s consent or preferences.  
    
*   Before using the activated data extension for journey entry, run an automation in Automation Studio to validate the consent or preference status of each contact or contact point against a separate data extension. Invalid contacts are removed before they enter the journey.  
    
*   As part of your journey entry source, configure filter criteria to exclude invalid contacts from entering the journey.  
    

## Hit the Stage

You’re ready to stage your data in Data 360. To build an omnichannel journey, use Data 360 and build a Unified Individual that represents a single person consisting of separate Marketing Cloud Engagement channel-specific SubscriberKeys (Individuals) and contact points. 

A Unified Individual is a grouping of separate Individual profiles that relate to a single Unified Individual profile. These relationships are based on your [Identity Resolution and Reconciliation Rules](https://help.salesforce.com/s/articleView?id=sf.c360_a_reconciliation_rules.htm&language=en_US&type=5). To include attributes from multiple Individuals into a single data extension row, segment and activate audiences at the Unified Individual level.

**Define Match Rules for Identity Resolution and Relate Separate Individuals**

Relate your separate Individuals to a Unified Individual using [Identity Resolution](https://help.salesforce.com/s/articleView?id=sf.c360_a_identity_resolution.htm&language=en_US&type=5). This example assumes that you can externally collect FirstName, LastName, EmailAddress, and/or PhoneNumber for each channel SubscriberKey. You then import the external data from three different systems, one for each channel, and [map it accordingly](https://help.salesforce.com/s/articleView?id=sf.c360_a_identity_resolution_data_modeling_requirements.htm&language=en_US&type=5). The imported SubscriberKey is linked to the Individual ID in Data 360. Using these match rules, Identity Resolution relates the separate Individuals, representing a person’s various Marketing Cloud Engagement SubscriberKeys, to a single Unified Individual.

**Define Reconciliation Rules to Prioritize Values for the Unified Individual**

Reconciliation rules specify how to select the best value for a Unified field when that field can store only one value, such as a person’s first name.

![Edit Default Reconciliation Rule for Individual modal in Data 360.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-clouddriven-interactions-in-marketing-cloud/personalize-your-omnichannel-journeys/images/a968ff383b5379570dd871c87178e745_kix.vfgg9e2d70w1.png)

**Create a Calculated Insight to Select a SubscriberKey**

Data 360 has numerous controls to select and activate a channel contact point. However, for some scenarios, you must create a Calculated Insight to filter or select a specific channel contact point. 

The Calculated Insight output includes the attribute MobilePush Key, which you can add as a direct attribute when you activate the Unified Individual. This action ensures that the activated data extension in Marketing Cloud Engagement has the contact point values for the Email, SMS, and MobilePush channels. Journey Builder can use these contact points to orchestrate omnichannel journeys.

Start by creating your audience. 

1.  Create a segment to qualify the correct Unified Individuals.  
    
2.  Activate the audience with applicable contact points and attributes.  
    

Next, set your journey connections.

1.  Update the send relationship on the activated data extension.  
    
2.  Configure journey entry to use the activated data extension audience.  
    
3.  Configure journey settings to use the desired send address.  
    
4.  Add consent or preference filters as needed.  
    

Now you know how Data 360 and Marketing Cloud Engagement work together to tailor your communications with your customers and create a great marketing experience. 

## Resources

*   [_Salesforce Help_: Omnichannel Journey Solution Kit](https://help.salesforce.com/s/articleView?id=sf.create_omnichannel_journeys_with_cdp.htm&type=5)
*   [_Salesforce Help_: Omnichannel Considerations and Best Practices](https://help.salesforce.com/s/articleView?id=data.c360_a_omni_best_practices.htm&type=5)

## Preguntas

**Pregunta 1:** Verdadero o falso: El consentimiento de SMS se almacena a nivel de SubscriberKey.

✅ **B — False**

El documento lo aclara explícitamente: *"Consent is stored at the phone number level (and keyword) and not at the SubscriberKey level."*

---

**Pregunta 2:** Verdadero o falso: Un Unified Individual es una agrupación de perfiles de Individuals separados que se relacionan con un único perfil de Unified Individual.

✅ **A — True**

El documento lo confirma directamente: *"A Unified Individual is a grouping of separate Individual profiles that relate to a single Unified Individual profile."*