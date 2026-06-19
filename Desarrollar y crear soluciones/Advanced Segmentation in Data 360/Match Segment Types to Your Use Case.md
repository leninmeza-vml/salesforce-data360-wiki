# Match Segment Types to Your Use Case

## Learning Objectives

*   Differentiate between standard, waterfall, dynamic, and real-time segments based on data refresh needs and business requirements.  
    
*   List activation target types and explain which segment types can publish to which activation targets.  
    
*   Select the appropriate segment type and activation target based on a specific business use case.  
    
*   Configure the Segment On entity to target audiences at the Unified Household or Account level.  
    

## Before You Start

Before you start this badge, make sure you complete [Segmentation in Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation) . The work you do here builds on the concepts you learn in that badge.

## Why Segment Type Matters

Meet Northern Trail Outfitters (NTO). It’s an outdoor retail company with a loyalty program and a large customer base. NTO already builds segments in Data 360 with include and exclude criteria. Now, NTO’s planning a spring campaign with three offers: 25% off, 15% off, and 10% off. NTO’s goal: Each customer receives only one offer, the best one they qualify for—no duplicates, no confusion.

But standard segments alone don’t guarantee that. A customer can qualify for multiple segments and receive multiple emails. To enforce one offer per customer, Michele Hansley, NTO’s technical marketer, needs the right segment type.

The segment type controls how a segment runs, how often it publishes, and what it can do. The activation target is where segment membership goes. Not every segment type fits every use case, and not every type can publish to every destination. Getting these choices right up front saves rework later.

This unit helps you figure out the best segment type, activation target, and Segment On to use in a given situation.

## Segment Types

### Standard

A standard segment is the default. You build it on a data model object (DMO), set a lookback period, and define include/exclude criteria. Standard segments can publish on a schedule. For example, every 12 or 24 hours, or manually. They support the full set of refinement levers and can publish to all supported activation target types.

NTO starts here. Michelle’s team builds three standard segments for the spring campaign: High-Value Customers (25% off), New Customers (15% off), and All Active Customers (10% off). But a customer can qualify for more than one of these segments and end up receiving multiple offers. Standard segments don’t enforce mutual exclusivity on their own.

### Waterfall

This is where a waterfall segment comes in. Think of it as a priority line at a concert. You give it a list of existing segments, up to 20, in priority order. Data 360 evaluates each customer from top to bottom. As soon as a customer matches, it stops. Each customer lands in exactly one bucket.

NTO puts High-Value first, New Customers second, and All Active third. A high-value new customer gets the 25% offer only. All segments in a waterfall must share the same Segment On entity and be active. You can’t include nested segments. Also, Rapid Publish isn’t available for waterfall segments.

### Dynamic

NTO’s app team has a different need. They want to include “hikers in this region” or “customers who bought this category” with the region or category changing each time. A dynamic segment handles this. It uses the same kind of filters as a standard segment but stores the filter values as parameters, which are variables. Instead of editing the segment to change “Region equals West” to “Region equals East,” an external service calls the API and passes the parameter value. The segment definition stays the same while the audience changes with each run—no persisted membership, no schedule from the UI.

### Real-Time

A real-time segment evaluates on demand and completes in milliseconds. It’s built on a real-time data graph, not a batch DMO. NTO can use one for the next-best action on its website. Real-time segments have constraints: no exclusion criteria, no nested batch segments, no segment counts, and no manual publish. Use them when the decision must happen in the moment.

### Review When to Use Which Segment

*   **Standard:** Scheduled batch audiences, full refinement, all activation targets  
    
*   **Waterfall:** Mutually exclusive priority groups from existing segments, same Segment On  
    
*   **Dynamic:** On-demand API-driven audiences, no persisted membership  
    
*   **Real-Time:** Millisecond evaluation on a real-time data graph, no batch publish  
    

With the right segment types in place, NTO’s spring campaign no longer risks sending duplicate offers. High-value customers get one email, not three, and the app team can serve personalized content without touching the segment definition every time.

## Activation Target Types

Think of an activation target as a destination, such as a home address. But having an address doesn’t mean a package automatically arrives. To get data moving, you need an activation (your delivery order) to tell Data 360 which attributes to include. Publishing is the final step, that’s when the package actually ships.

NTO is ready to put this into practice. NTO plans to use Marketing Cloud Engagement (MCE) for email journeys and Amazon S3 for analytics.

Data 360 supports these target types.

*   Data 360 (Audience DMO)  
    
*   MCE  
    
*   B2C Commerce  
    
*   Cloud file storage such as Amazon S3, SFTP, Google Cloud Storage, and Microsoft Azure  
    
*   Marketing Cloud Personalization  
    
*   External activation platform such as Google Ads, Meta, or AgentExchange partners  
    
*   Data 360 Loyalty  
    

![Data 360 Segmentation workflow.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/advanced-segmentation-in-data-360/match-segment-types-to-your-use-case/images/1b61c8b8719f09de8c93abcaba7ba3b6_kix.cv5xoo1pbqk8.png)

Standard segments can publish to all target types. Rapid Publish (1-hour or 4-hour) supports only MCE and cloud file storage. Waterfall segments use Standard Publish only but support all target types. Dynamic segments run via API. Evaluation of real-time segments occurs on demand in the real-time data graph.

## Segment On: Choose the Right Base Object

Segment On is the DMO your segment is built on. It controls which attributes appear and what level your segment operates at.

*   **Unified Individual:** Use when you have Identity Resolution and want one person across sources. NTO uses this for the spring campaign.  
    
*   **Individual:** Use without Identity Resolution, which can lead to duplicate or skipped entities.  
    
*   **Unified Household:** Use this to group Unified Individuals into households. NTO is planning a Family Adventure promotion targeting households. The NTO team uses this Segment On when they build it.  
    
*   **Account:** Use for B2B, and to target accounts by revenue, industry, or related data.  
    
*   **Unified Account:** Use for B2B with Identity Resolution, when there is one account across sources—the same logic as Unified Individual, but at the account level.  
    
*   **Other Profile and Engagement DMOs:** Depending on your data model, you can segment on other objects marked as Profile or Engagement type.  
    

Get these three choices right—segment type, activation target, and Segment On—and the rest of the segment builds on a solid base.

## What Comes Next

NTO has its plan in place.

*   Three standard segments for the spring campaign offers (25% off, 15% off, 10% off)  
    
*   A waterfall segment for mutual exclusivity so each customer gets only one offer  
    
*   A dynamic segment for the app team’s parameterized audiences  
    
*   MCE and S3 as activation targets for email and analytics  
    
*   Unified Individual as the Segment On  
    

In addition to the Family Adventure promotion, Michele wants to plan a Surprise and Delight gift program for NTO’s most engaged customers. But 50,000 people qualify for the spring campaign, and NTO can only send Surprise and Delight gifts to 2,000. How does NTO narrow that down? That is covered in the next unit.

## Resources

*   [_Salesforce Help_ : Create Segments in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_segments.htm&type=5)
*   [_Salesforce Help_ : Activation and Activation Targets](https://help.salesforce.com/s/articleView?id=data.c360_a_activation.htm&type=5)

## Respuestas

**Pregunta 1:** Una plataforma asigna un incentivo por usuario: upgrade para premium, descuento para nuevos, extensión de prueba para el resto. ¿Qué tipo de segmento garantiza uno por usuario?

✅ **D — Waterfall**

El documento lo explica claramente: el segmento waterfall evalúa a cada cliente de arriba hacia abajo en orden de prioridad y se detiene en cuanto encuentra una coincidencia, garantizando que cada cliente caiga en exactamente un grupo. Es precisamente el caso de uso descrito con NTO y sus tres ofertas.

---

**Pregunta 2:** Una marca de viajes envía un correo por hogar. Criterio: gasto combinado mayor a $2,000 y al menos una reserva de vacaciones familiar en el último año. ¿Cuál es el Segment On más adecuado?

✅ **B — Unified Household**

El documento lo confirma: *"Unified Household: Use this to group Unified Individuals into households."* Este Segment On es ideal cuando se quiere operar a nivel del hogar en lugar del individuo, exactamente como en este caso donde se envía un solo correo por familia.
