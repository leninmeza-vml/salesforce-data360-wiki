# Build Your Data Foundation

## Learning Objectives

After completing this unit, you’ll be able to:

*   Establish data foundation requirements for Marketing Cloud Engagement.  
    
*   Create core activations in Data 360 and link them to Marketing Cloud Engagement.  
    
*   Create related attribute relationships for your customers.  
    
*   Use data from Data 360 throughout Marketing Cloud Engagement.  
    

## A Strong Foundation

You and Isabelle have learned the basics of how to use Data 360 audiences in Marketing Cloud Engagement, but did you know that you can build an even stronger and more personalized data foundation to connect with your customers? 

**Model Your Data Foundation in Marketing Cloud Engagement**

When you use Data 360 to power customer engagement (and we hope you do), think about intentionally structuring your data foundation instead of activating the same data repeatedly. 

First, determine the best model for your data foundation. Then initialize your data foundation by using Data 360 to activate core audiences to Marketing Cloud Engagement. Finally, establish your data foundation by connecting the resulting data extensions to the appropriate Marketing Cloud Engagement Contact Model.

**Core Audience Model**

Using the core audience model, you create two activations in Data 360—one activation at the Individual level, and one at the Unified Individual level. Each activation contains your organization’s full active audience and all your required content personalization and decisioning attributes chosen by your organization.

**Collective Core Audience Model**

Your marketing team chooses 2–15 groupings to organize the commonly shared attributes. For example, Identity & Consent or Demographics & Psychographics.

When choosing a model, there are a few things to take into consideration.

*   Consider your use case and include the audience and all of the attributes that you want to capture for personalization and decisioning. For example, contacts who purchased running shoes during a specific sale and spent at least $100.  
    
*   Use a core audience model for attributes that you'll use repeatedly.  
    
*   Use a collective core audience model when the core model might be too complex and it’s better to segment it for more specific use cases.  
    

Here are some other factors to consider when choosing the best model for your organization. 

| Organizational Factors | Core Audience Model | Collective Core Audience Model |
| --- | --- | --- |
| Total Audience Size | 0–8 million | 8 million or more |
| Number of Shared Personalization and Decisioning Attributes | 1–100 | 100+ |
| Team Experience with Marketing Cloud Engagement | None–Low | Moderate–Advanced |
| Desired Journey Length and Sophistication | None–Low | Moderate–Advanced |

Isabelle chose the collective core audience model for her audiences. This model gives her the power to specify her audience and messaging more succinctly based on their interests and actions. 

She creates three activations:

1.  Unified demographic information  
    
2.  Individual purchase data  
    
3.  Loyalty status  
    

For more details about these audience models and how to activate them, see [Create Your Core Activations in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_mcdf_core.htm&type=5).

## Activate the Core

Once you choose the model for your foundation, you need to create core activations in Data 360. 

1.  [Create a segment in Data 360](https://help.salesforce.com/s/articleView?id=sf.c360_a_create_a_segment.htm&language=en_US&type=5).  
    
2.  [Create one or more Data 360 activations](https://help.salesforce.com/s/articleView?id=sf.c360_a_create_marketing_cloud_activation_target.htm&language=en_US&type=5).  
    
3.  Select channels and contact points for your activations.  
    
4.  Organize and include commonly shared attributes for each activation.  
    

## It’s All Relative

While you’re activating your core, you can personalize Marketing Cloud Engagement communications using direct and related attributes from Data 360. This practice helps you control the volume and variety of data that can be used in marketing segments. 

*   **Direct attributes (1:1):** Attributes that have a direct relationship in a data model object, meaning a user has only one value, for example, postal code or first name.  
    
*   **Related attributes (1:N):** Attributes that have a one-to-many (1:N) relationship, meaning they could have many values per attribute for a specific user, for example, purchases or email events.  
    

Here’s an example of adding some related attributes to an SMS campaign in a Marketing Cloud Engagement activation. 

![Data 360 add additional attributes modal](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-clouddriven-interactions-in-marketing-cloud/build-your-data-foundation/images/dd337e1ae1eca4f2dcf756286889b9da_kix.ujxy6yvp4045.png)

Find all the info you need about related attributes in our [Related Attributes in Activation Solution Kit](https://help.salesforce.com/s/articleView?id=sf.related_attributes.htm&type=5). 

## Link Them Up

Now it’s time to link your core activations to the Marketing Cloud Engagement Contact Model. You might want to enlist the help of your data specialist for these steps. 

1.  [Create attribute groups](https://help.salesforce.com/s/articleView?id=sf.mc_cab_create_attribute_group.htm&language=en_US&type=5) in Marketing Cloud Engagement Contact Builder.  
    
2.  For each attribute group, data specialists link the data extensions that marketers activated in Data 360.  
    
3.  In Marketing Cloud Engagement, create a Contact Model attribute group.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

To prevent data sprawl and performance impacts, turn on the data deletion feature only for the ad hoc data extensions so that their stored data is deleted after the journey is complete. It’s also best practice to routinely check and delete old data extensions from the Contact Model.

## Use This Foundation Throughout Marketing Cloud Engagement

You’re ready to start using the foundation you’ve built! We’ve got a few recommendations to help you to maximize system performance. (Note: Your foundation is refreshed according to the schedule you’ve set in Data 360.) 

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

When activating audiences from Data 360, related attributes can’t be used for journey decisioning. Instead, use the commonly shared attributes that have been established as part of the data foundation for the journey’s decisions and exit activities.

First, use static [journey data](https://help.salesforce.com/s/articleView?id=sf.mc_jb_journey_contact_data.htm&language=en_US&type=5) for content personalization for both [audience-based journeys](https://help.salesforce.com/s/articleView?id=sf.c360_a_create_marketing_cloud_activation.htm&language=en_US&type=5) that use data extensions and event-triggered journeys that use data actions or API for journey entry.

And when activating audiences from Data 360, we recommend including all attributes that are required to personalize the content throughout the targeted journey.

*   If you use [AMPScript personalization strings](https://trailhead.salesforce.com/content/learn/modules/marketing-cloud-programmatic-languages/explore-ampscript), these strings reference [journey data](https://help.salesforce.com/s/articleView?id=sf.mc_jb_journey_contact_data.htm&language=en_US&type=5) in the data foundation you already created.  
    
*   AMPScript functions and data extensions lookups pull the most up-to-date information about your audiences.  
    

You can find more tips and tricks in [Use Data 360 Data Throughout Marketing Cloud Engagement](https://help.salesforce.com/s/articleView?id=data.c360_a_mcdf_usedata.htm&type=5).

Now that you’ve built your awesome foundation, check out how to use this foundation to create omnichannel journeys. 

## Resources

*   [_Salesforce Help_: Data Foundation Solution Kit](https://help.salesforce.com/s/articleView?id=sf.cdpmarketingclouddatafoundation.htm&type=5)
*   [_Salesforce Help_: Related Attributes Solution Kit](https://help.salesforce.com/s/articleView?id=sf.related_attributes.htm&type=5)
*   [_Trailhead_: Data and Identity in Data 360](https://trailhead.salesforce.com/content/learn/modules/data-and-identity-in-salesforce-cdp)
*   [_Trailhead_: Explore Synchronized Data Sources](https://trailhead.salesforce.com/content/learn/modules/marketing-cloud-contact-management/explore-synchronized-data-sources)

## Preguntas

**Pregunta 1:** Verdadero o falso: Si tu audiencia es mayor a 8 millones, el modelo que mejor funciona es el Collective Core Audience model.

✅ **A — True**

El documento lo confirma en la tabla de factores organizacionales: para un *Total Audience Size* de **8 millones o más**, el modelo recomendado es el **Collective Core Audience Model**.

---

**Pregunta 2:** ¿A qué tipo de usuario deben pedir ayuda los marketers para vincular las activaciones principales al Marketing Cloud Engagement Contact Model?

✅ **B — A data specialist**

El documento lo indica explícitamente: *"You might want to enlist the help of your data specialist for these steps."* Son los data specialists quienes vinculan las data extensions activadas en Data 360 con el Contact Model.