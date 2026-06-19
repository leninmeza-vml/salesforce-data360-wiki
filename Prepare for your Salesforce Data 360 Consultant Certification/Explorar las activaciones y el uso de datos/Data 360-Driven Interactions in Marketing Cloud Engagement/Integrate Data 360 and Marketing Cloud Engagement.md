# Integrate Data 360 and Marketing Cloud Engagement

## Learning Objectives 

After completing this unit, you’ll be able to:

*   Understand how integrated data works across Data 360 and Marketing Cloud Engagement.  
    
*   Locate your integrated data extensions.  
    
*   Use proper consent practices for your Data 360 audiences.  
    

## Marketing Plan Case Study

![""](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-clouddriven-interactions-in-marketing-cloud/integrate-data-cloud-and-marketing-cloud/images/dce62353983dc23f8fb7e5db30c4cda7_kix.vhxz3w4s61pu.png)

Northern Trail Outfitters (NTO) is an outdoor brand that offers signature outerwear, men’s and women’s clothing, gear, and accessories. Isabelle Givens, a digital marketing manager at NTO, wants to create and send a personalized journey to established customers based on purchases they’ve already made and loyalty status. She’s working with her marketing team to reach this goal.

Isabelle wants to reach her customers in a more specific way. Instead of sending as many messages as she can, she wants to efficiently get the right message to the right users! To accomplish that, she’s built and activated segments in Data 360 to target individuals who are most likely to act on her campaign. She can use these segments in Marketing Cloud Engagement and Journey Builder to build stronger and more personalized connections with her customers. 

Data 360 is optimized for messaging using Journey Builder. Audiences can also include enriched unified individual records and new records, but we cover that in a later unit. 

Isabelle probably already knows where to find her audiences in Journey Builder. When building a journey on the canvas, she can select the audience in the Data Extension Entry Source in Journey Builder.

But since Isabelle wants a more personalized experience using her new Data 360 segment, she selects her audience from the Data Cloud Segments folder in the Shared Data Extensions folder in Marketing Cloud Engagement. 

![Selection of Data Cloud segments in Journey Builder](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-clouddriven-interactions-in-marketing-cloud/integrate-data-cloud-and-marketing-cloud/images/6bf89851ac7c64836e7a9bcf269f8943_kix.zcifv0xd0sax.png)

## Know Your Data

Journey data preserves the state of a contact’s data at the moment an entry event fires, facilitating the use of that data throughout a journey. Contact data captures the data values in the event source data extension at the time when Journey Builder evaluates it. Both are uniquely useful in journey creation.

| Journey Data | Contact Data |
| --- | --- |
| Initial data value about a customer. | Current data value about a customer. |
| Provides attributes in the state they were in when the contact entered the journey. | Provides attributes in the state they are in when evaluation occurs after the entry event has fired. |
| Comprised of event data and activity data. | Use when you want the most updated information in a longer journey. |
| Use when a contact is likely to exist in a journey more than once simultaneously. |     |
| Use for comparison when a data value is expected to change. |     |

## Know Your Data Segments

In standard segment activation, you can schedule batch or incremental refreshes to your audiences. For existing segments, Data 360 performs a full overwrite of the activated data extension and replaces all rows in the data extension.

Contacts who have fallen out of the segment since the previous segment refresh don’t re-enter the journey. Previously active members of the segment aren’t automatically ejected from the journey. They will continue through the journey until they are explicitly removed by a process you’ve defined such as exit criteria, for example.  

In rapid publish activation, though rare, Data 360 can trigger a full overwrite refresh even if you’ve selected an entry process of [evaluate new records only](https://help.salesforce.com/s/articleView?id=sf.mc_jb_manage_audience_data.htm&type=5). This option updates incrementally. Depending on your journey’s [entry settings](https://help.salesforce.com/s/articleView?id=sf.mc_jb_journey_settings.htm&type=5), this could result in a contact being inadvertently entered into the journey again, potentially resulting in “duplicate” messaging. To prevent this, select the Entry Setting **No re-entry.** 

## Consent Is Important

Isabelle wants to make sure that all of her customers are being contacted (or not contacted!) the way they’d like. These best practices make the journey much smoother for her and her customers. 

*   We recommend managing consent as you’ve always done in Marketing Cloud Engagement. For example, filtering consent criteria for entry source configurations, decision splits, or publication lists.  
    
*   If the activity appears later in the journey, we recommend using a Decision Split instead of filtering consent criteria for entry source configuration.  
    
*   To configure an email activity to use a Data 360 audience and exclude contacts who’ve opted out, assign a publication or suppression list in Marketing Cloud Engagement for more consent management options.  
    

Now that you have the basics of Data 360 and Marketing Cloud Engagement down, learn how to do even more with marketing contacts in the next unit. 

## Resources 

*   [_Salesforce Help_: Use Data 360 in Journey Builder](https://help.salesforce.com/s/articleView?language=en_US&id=sf.mc_jb_c360a_using_audiences.htm&type=5)
*   [_Salesforce Help_: Journey and Contact Data](https://help.salesforce.com/s/articleView?id=sf.mc_jb_journey_contact_data.htm&type=5)
*   [_Trailhead_: Data 360 Segmentation and Activation](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation)

## Preguntas

**Pregunta 1:** ¿En qué carpeta encontrarías tus segmentos de Data Cloud?

✅ **D — Shared Data Extensions**

El documento lo indica claramente: Isabelle selecciona su audiencia desde *"the Data Cloud Segments folder in the Shared Data Extensions folder in Marketing Cloud Engagement."*

---

**Pregunta 2:** Verdadero o falso: Es una buena práctica asignar una lista de publicación o supresión para configurar una actividad de email para una audiencia de Data 360.

✅ **A — True**

El documento lo confirma en la sección de consentimiento: *"To configure an email activity to use a Data 360 audience and exclude contacts who've opted out, assign a publication or suppression list in Marketing Cloud Engagement for more consent management options."*