Learn About Connection Steps
============================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Explain how data is brought into Data 360.  
    
*   Identify implementation steps to connect data to Data 360.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

It All Begins with Data
-----------------------

It’s amazing how much engagement and behavioral data one person can generate throughout the day. A simple shopping trip can generate customer data related to sales messages, web traffic, purchases, preferences, location, and a multitude of other sources. It can be daunting for any business to know where to begin when trying to understand the complexity of its customer data. The good news is that Data 360 is here to help. And if you are reading this, it’s likely that it’s your responsibility to make sure the data is organized and connected to Data 360 to achieve your business goals.

Getting to know your data structure, relationships between data, needed credentials, data hygiene, and storage needs can take time. But after you have a clear plan, Data 360 gives you the tools to bring all of that data into a single, useful view of your customer. To help you get started, in this module, we cover key concepts and steps to plan for, connect to, and map your data in Data 360.

Unlock Trapped Data
-------------------

Data can take many forms and can be stored in a variety of locations and can be hard to access. Data 360 provides a central location to unify, analyze, and act on any type of data. Here are some examples.

*   Chat transcripts from your service reps  
    
*   Real-time engagement data from your website  
    
*   CSV spreadsheets on your laptop  
    
*   Legacy data lakes that you don’t want to move  
    
*   PDF manuals  
    
*   Audio recordings of sales calls  
    

Additionally, we are expanding our formats for unstructured data. So if you’ve got a range of data sources and types, we’ve got you covered.

Data Flow in Data 360
---------------------

Let’s examine how data flows in and out of Data 360. Data can either be brought into Data 360 as a source, sent out to a target, or a combination of both. This is why Data 360 can refer to connections as integrations, since data flows both into and out of the platform. Connectors are used to establish connections (via data streams) between a data source and Data 360.

### Data In

Data from Salesforce connectors, connector services, or third-party connectors is ingested as either streaming or batch data. Near real-time web engagement data is an example of streaming data. When you ingest data, your raw data is added to Data 360 using a data stream. The data isn’t altered, so the original structure and data types are kept as they are. Data streams dictate how often and when ‌connections should be established. If data is stored in Data 360, the raw data is stored in our system in a data lake object (DLO).

But data doesn’t have to be ingested into Data 360. It can also be connected to an external source, through Zero Copy Data Federation. Data Federation in Data 360 allows you to set up connectivity with external data sources and connect that data without storing it in a data lake in Data 360. You create and deploy a data stream that creates an external data lake object (DLO) that stores the metadata. The DLO acts as a reference, and points to the data physically stored in an external data source.

Before any data can be used in Data 360, fields in DLOs are mapped to the standard data model, the Customer 360 Data Model, for downstream use in segmentation, insights, or activation.

### Data Out

After data is manipulated, harmonized, or segmented in Data 360, data can be sent to targets (1) such as a Secure File Transfer (SFTP) (2) or shared with external integrations, such as Snowflake using Data Shares.

![The Add Connection screen showing possible data Targets with SFTP selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/learn-about-connection-steps/images/5b3f3ba18189d1deb231477784f16a34_kix.mweyavlppdls.png)

Targets are used to activate segments to Marketing Cloud Engagement or advertising platforms, such as Meta or Google ads. Targets can be used with data actions to perform tasks in Sales or Service Cloud. Or using data shares, data can be used externally with Google BigQuery or Snowflake. In this module, we focus on data coming into Data 360 via data sources using connectors.

Overview of Steps
-----------------

Let’s cover the high-level steps involved in how to connect data sources to Data 360 (also the core implementation steps for getting started with Data 360).

1.  **Create a connection.** To get data from sources into Data 360, connections are made between the source and Data 360. A system admin or a user with the Data Cloud Architect permission set follows steps in Data Cloud Setup depending on the type of connector. They install data bundles, add configuration and authentication information about the data source, or create event definitions to establish a connection between the source and Data 360.  
    
2.  **Create a data stream.** Once an admin sets up a connection, data streams can be created for each connection. This creates data lake objects (DLOs) that store your data, metadata, or both.  
    
3.  **Transform data.** Once data streams are created, data can be altered by adding key qualifiers, with simple formulas to update names or perform row-based calculations, or by creating streaming or batch data transforms on your data. Learn about [batch data transforms](https://trailhead.salesforce.com/content/learn/modules/batch-data-transforms-in-data-cloud-quick-look) and [streaming transforms](https://trailhead.salesforce.com/en/content/learn/modules/streaming-data-transforms-quick-look) in their associated badges.  
    
4.  **Map your data.** To help harmonize and make sense of your data, it needs to be mapped to the [Customer 360 Data Model](https://trailhead.salesforce.com/content/learn/modules/customer-360-data-model-for-customer-data-platform), the standard data model for Data 360. Depending on the type of connector, some fields are premapped. If not, you ‌manually map fields to the Customer 360 Data Model. Proper mapping of data is required for data unification using identity resolution rulesets.  
    

These steps create the foundation for a variety of business use cases, whether you plan to use your data to ground an artificial intelligence (AI) prompt, to create unified, targeted marketing segments, or to analyze your data extensively in Tableau.

Now you know the foundational steps to get started in Data 360. In the next unit, we determine what data to add to Data 360.

Resources
---------

*   [_Salesforce Help_: Data Federation, Ingestion and Modeling](https://help.salesforce.com/s/articleView?id=data.c360_a_data_ingestion_and_modeling.htm&type=5)
*   [_Salesforce Help_: Unstructured Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&type=5)
*   [_Trailhead_: Customer 360 Data Model for Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-data-model-for-customer-data-platform)
*   [_Trailhead_: Streaming Data Transforms in Data 360: Quick Look](https://trailhead.salesforce.com/en/content/learn/modules/streaming-data-transforms-quick-look)
*   [_Trailhead_: Batch Data Transforms in Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/batch-data-transforms-in-data-cloud-quick-look)
*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)
*   

Prueba
------

1 What is the purpose of Data Federation?
A) Activate data through a Salesforce connector.
B) Connect metadata from an external source. *
C) Share Data 360 data with a third party.
D) Ingest and store data from an external source in Data 360.

2 What isn’t a step you need to follow when connecting and ingesting data to Data 360?

A) Connect a data source in Data Cloud Setup.
B) Transform data with formula fields.
C) Create a data stream.
D) Unify profiles. *
