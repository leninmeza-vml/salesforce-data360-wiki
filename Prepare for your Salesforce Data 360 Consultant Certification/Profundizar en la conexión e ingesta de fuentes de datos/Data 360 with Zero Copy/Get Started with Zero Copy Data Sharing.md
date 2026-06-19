# Get Started with Zero Copy Data Sharing

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain what zero-copy data sharing is in Data 360.  
    
*   Describe when to use a data share.  
    
*   List the requirements to get started with a data share.  
    
*   Describe how to access data from an external system.  
    

## What Is Data Sharing?

You establish connections from external systems to Data 360 with data federation. With data sharing, you communicate in the opposite direction—sharing selected data objects in Data 360 with external systems. This means that with a simple point-and-click you can assemble the data objects into a data share and share it with an external system.

## How Does Zero Copy Data Sharing Work?

With zero-copy data sharing, you can directly share data from Data 360 to an external system without loading the data into the external system. The zero-copy approach ensures near real-time access to the current data while maintaining standards of security and governance.

The objects assembled in a data share are made available to the external system by linking a data share to a data share target.

Here are some of the Data 360 objects you can share via data shares.

*   **Data lake object (DLO):** Data ingested into the Data 360 gets stored in a DLO. The data stored in a DLO is cleansed, transformed, and prepped for computation and analysis.  
    
*   **Data model object (DMO):** A DMO is a grouping of data (made up of attributes) created from data streams, insights, and DLOs. Data is harmonized from different sources into a uniform data model. Data 360 supports standard and custom DMOs.  
    
*   **Calculated insight object (CIO):** Calculated insights help build cube-style metrics with measures and dimensions on Data 360 data. A CIO is a DMO created after a calculated insight is processed.  
    

## Use Cases for Data Sharing

Data shares let businesses break down data silos across clouds. Businesses can view data, perform cross-cloud analytics, and build machine learning (ML) models. Data 360 ingests data from diverse data sources. Low-latency access to this cross-functional data provides a deep understanding of the customer backed by data-driven awareness.

*   Enrich your Snowflake marketing data with unified customer profiles from Data 360, activating it through existing channels for hyper-personalized campaigns and enhanced lifetime value.  
    
*   Share real-time, unified inventory insights from Data 360 with your Databricks Lakehouse, empowering logistics partners to optimize your supply chain, reduce stockouts, and improve delivery efficiency.  
    
*   Provide enhanced financial risk insights from Data 360 to your enterprise data warehouse, enriching compliance analytics for improved fraud detection, higher risk modeling accuracy, and streamlined regulatory reporting.  
    
*   Stream unified IoT sensor insights and enriched customer context from Data 360 back to your data lake, accelerating product innovation, proactively identifying performance issues, and enabling predictive maintenance for Research and Development teams.  
    

## Access Data 360 Data from an External System

To make the most ofData 360’s data-sharing capability, follow these simple steps to unlock the value of secure and compliant data sharing.

### Step 1: Plan Data Strategy

Identify the Data 360 objects you want to access. For example, if you’re a data scientist interested in building propensity and dynamic pricing models, you can access DMOs with profile information and engagement data like Contact and Individual DMOs. You can further choose to include DLOs like OrderDetails and MobileAppBehavioralEvents to analyze purchasing patterns. With such data objects assembled in a data share, you have access to the live and latest Salesforce data.

### Step 2: Set Up Your Credentials

Next, work with your Data Cloud architect and admins of your external systems to create the necessary users, and obtain the credentials needed to set up access to your Data 360 data.

### Step 3: Build Your Data Shares

Create a data share and assemble the Data 360 objects. Give the data share a unique name, and select the applicable data space. A data space is a logical categorization of your data in Data 360, and lets you see and work on only the data that is relevant to you. Once you save your data share it gets successfully created and moves into an active status.

### Step 4: Create Data Share Target and Link Data Share

To make this data share accessible in an external system, you need to create a data share target. A data share target establishes a connection between Data 360 and the external system.

Then link your data share target with the data share you created. Make sure that the data share is active before linking it to the data share target.

Once you link the data share to a data share target, the selected data objects are available in your external system’s account. You can now use Salesforce data directly in the external system.

## Wrap It Up

Now you know all about zero copy, a powerful tool for implementing bidirectional integrations between Data 360 and external systems. You understand how to use zero copy data federation to access external data directly within Data 360, without the need for time-consuming and resource-intensive data duplication. You also understand the differences between query federation and file federation. And you have the scoop on zero copy data sharing, which enables you to share selected Data 360 objects back to external systems.

Zero copy offers bidirectional communication and breaks down data silos. With this knowledge, you’re equipped to create more fluid, real-time, and simplified data integrations.

## Resources

*   [_Salesforce Help_: Act on Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_act_on_data.htm&type=5)
*   [_Salesforce Help_: Data Shares](https://help.salesforce.com/s/articleView?id=data.c360_a_data_shares.htm&type=5)
*   [_Trailhead_: Explore Data 360](https://trailhead.salesforce.com/content/learn/trails/explore-customer-360-audiences)
*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)
*   [_Salesforce Help_: Data Model Concepts](https://help.salesforce.com/s/articleView?id=data.c360_a_understanding_and_using_the_data_model.htm&type=5)

Respuestas:

---

**Pregunta 1:** Which of these is true of a Data 360 data share?

✅ **B — A data share target can be granted or revoked access to a data share by linking or delinking it.**

El documento indica en el Step 4 que para hacer accesible un data share en un sistema externo se debe *"link your data share target with the data share"*, lo que implica que también se puede desvincular para revocar el acceso. Las otras opciones son incorrectas porque: zero copy evita cargar datos (no A), no se menciona restricción por edición (no C), y los DLOs también pueden compartirse (no D).

---

**Pregunta 2:** What state must a data share be in to connect with a data share target?

✅ **B — Active**

El documento es explícito en el Step 4: *"Make sure that the data share is active before linking it to the data share target."*

---
