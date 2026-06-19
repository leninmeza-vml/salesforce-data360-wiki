# Enhance Service with Data 360 Insights

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the core functions of Salesforce Data 360.  
    
*   Explain the benefits of integrating Service Cloud with Data 360.  
    
*   List some ways you can improve service performance with Data 360.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## The Role of Data in Customer Service

Data: It’s the difference between a nervous guess and a confident decision, and the key to thriving in a competitive business environment. But for businesses focused on customer service, making the leap from generating data to gathering and acting on it can be tricky. So let’s find out how you can combine several clouds in Salesforce to make your data work for you.

Service Cloud provides the foundational tools that a business needs to provide efficient, human-centric customer service.

*   The Service Console, the home base for service agents  
    
*   Communication channels, such as voice, messaging, and email  
    
*   Agent collaboration and productivity tools, such as macros, swarming, and Knowledge  
    
*   AI tools that take the heat off of your human agents and supervisors, such as Einstein bots, service replies, knowledge creation, and work summaries  
    

And don’t forget about the other Salesforce customer service solution: Field Service, a must-have suite of tools that allow you to manage work orders, optimize your appointment schedule, track your inventory, and manage your mobile workforce.

With Field Service, you can:

*   Create records representing your mobile workers, dispatchers, and agents, and add details about their skills, location, and availability.  
    
*   Track the location and status of your inventory, warehouses, vehicles, and customer sites.  
    
*   Create maintenance plans and templates to standardize field service tasks.  
    
*   Schedule one-time or recurring service appointments for customers, with travel time and costs minimized.  
    

Many of the features available in Service Cloud and Field Service already come with data visualizations; for example, supervisors can track agent productivity in the Omni Supervisor dashboard. But what if you want to take it to the next level?

## Enter Data 360

With data scattered across various platforms, staying connected to your customers can be challenging. That’s where Data 360 comes in.

With Data 360, you can:

*   Connect all your data seamlessly to Salesforce.  
    
*   Map any piece of helpful data to the right account or contact, regardless of the source, and use it alongside regular Salesforce data.  
    
*   Ensure the consistency and accuracy of the data that support agents are using by unifying customer profiles. With all data about a customer in one place, agents don’t have to scramble to gather information during a call or chat.  
    
*   Use AI to predict behavior and streamline processes. Data 360 and AI work together to help service professionals give customers more efficient, personalized service.  
    

## Unified Data

You might notice a theme when discussing Data 360: **unif****ied data.** Using matching and resolution rules, Data 360 creates a profile that links data about a customer across all those sources. Unified profiles are a foundational processing step that informs multiple downstream data-driven workflows and outcomes, including proactive service.

Let’s watch a quick overview.

Unify web engagement data and transaction history with product information into a single 360-degree view of the customer in Profile Explorer. With all this data in one place, you get reliable, rich metrics such as customer satisfaction (CSAT) scores and customer effort scores that take all of a customer’s actions into account. And with high-quality data, service teams can deliver personalized service tailored to their customers’ unique needs. Now, imagine the immense potential you unlock by applying these capabilities to your customer service.

## Deliver Smarter Service with Data 360

Service Cloud already includes lots of data that you’re familiar with, such as cases and accounts. But your customers are generating plenty of other data that can provide valuable context to your support team. Customers aren’t just filing cases; they're browsing your website, buying and returning products, giving feedback, and clicking marketing emails. When you integrate Data 360 with Service Cloud and Field Service, you can access and analyze that extra data, creating automations and visualizations to help your agents and supervisors deliver better customer service.

Let’s explore our favorite Service Cloud and Field Service features that rely on Data 360.

| **Feature** | **Description** | **Details** |
| --- | --- | --- |
| [Conversation Transcripts in Data 360](https://help.salesforce.com/s/articleView?id=service.conversation_transcript_analyze.htm&type=5) | Get insights from your service team’s voice calls and enhanced messaging sessions by adding your transcript data to Data 360. | Includes Data 360 and Service Cloud. |
| [Proactive Asset Service](https://help.salesforce.com/s/articleView?id=xcloud.pfs_pas_intro.htm&type=5) | Move away from reactive, break-fix service to proactive field service with prebuilt Asset Health Score dashboards and related Calculated Insights (CIs). Einstein draws on asset data and repair history to calculate an Asset Health Score and trigger action for each asset, such as scheduling a proactive service appointment. For example, if a service outage causes a spike in cases impacting a subset of customers, automatically trigger a flow that creates an incident and proactively notifies all impacted customers. | Includes Data 360, CRM Analytics, and Service Cloud. |
| [Field Service Intelligence](https://help.salesforce.com/s/articleView?id=service.ifs_intro.htm&type=5) | Monitor key contact center performance metrics with prebuilt dashboards focused on assets, work orders, and service appointments. For example, understand and monitor service appointment volume across your organization by territory, status, work type, account, priority, and other attributes. | Includes Data 360, CRM Analytics, and Service Cloud. |
| [Service Intelligence](https://help.salesforce.com/s/articleView?id=service.service_intelligence_intro.htm&type=5) | Get prebuilt dashboards to track KPIs and trends related to cases, Knowledge, Omni-Channel routing, and other service features. Surface data from these dashboards, such as the Customer Effort Score, in the Service Console to guide agents during service interactions. While you can build your own apps in Data 360 without Service Intelligence, it sure is nice having someone else do the visualization work for you. | Includes Data 360, CRM Analytics, and Einstein Conversation Mining. |

## Data 360 in Action

Now, let’s zoom into a unified profile for a customer named Andy.

![Unified customer profile showing customer information, recommendations, recent purchases, customer metrics, and activity.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/service-and-data-cloud-quick-look/enhance-service-with-data-cloud-insights/images/42783f8e994b1ebae4f714ba267aebec_kix.mb05tfn1612z.png)

The left side shows Andy’s propensity to purchase and CSAT scores. The right side shows his metrics and recent Salesforce interactions, including cases, purchases, surveys, and campaigns. In the center, there are recommendations based on Andy’s history, so an agent working with Andy can make data-driven suggestions. These metrics and recommendations are calculated and assembled based on data available in Data 360.

To wrap things up: Data 360 lets you access and learn from all of your enterprise data—data that might otherwise go unused. Thanks for taking a few minutes to learn how Data 360 can help you provide high-quality, scalable customer service.

## Resources

*   [_Salesforce Help_: About Salesforce Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud.htm&type=5)
*   [_Trailhead_: Data 360 for Admins](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-for-admins?trail_id=explore-customer-360-audiences)
*   [_Trailhead_: Data 360-Powered Experiences](https://trailhead.salesforce.com/content/learn/modules/data-cloud-powered-experiences)

## Preguntas

**Pregunta 1:** ¿Cuál es un beneficio de integrar Service Cloud con Data 360?

✅ **D — A and B**

El documento respalda ambas opciones:
- **A**: Data 360 unifica perfiles de clientes en Profile Explorer, combinando datos de múltiples fuentes en una sola vista de 360 grados.
- **B**: La función *Proactive Asset Service* incluye dashboards preconfigurados de Asset Health Score.

La opción C (sudadera gratis) es obviamente incorrecta. 😄

---

**Pregunta 2:** ¿Qué función de Data 360 facilita el seguimiento de actividades de Messaging y Voice?

✅ **B — Conversation Transcripts in Data 360**

El documento lo describe claramente: *"Get insights from your service team's voice calls and enhanced messaging sessions by adding your transcript data to Data 360."* Esta función está diseñada específicamente para capturar y analizar las transcripciones de llamadas de voz y sesiones de mensajería.