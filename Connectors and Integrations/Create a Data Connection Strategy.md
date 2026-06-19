Create a Data Connection Strategy
=================================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Define key terms related to connecting data in Data 360.  
    
*   Review your use cases and data sources to create a matrix.  
    
*   Identify the data sources that connect to Data 360.  
    

Considerations and Key Terms
----------------------------

Before we move on, let’s cover some important considerations and terms. When creating your data streams, it’s important to identify the type or category of that data correctly. Data is assigned to ‌categories that impact downstream behavior. Let’s review.

*   **Profile:** Data about a customer, for example, their loyalty club information that includes birthday and email address preferences.  
    
*   **Engagement:** Data about behavior, such as a customer’s website browsing history. If selected, you also need to include time information related to the behavior. Choose between options like created date, last modified, or last status change.  
    
*   **Other:** Other types of data, like product inventory information.  
    

Categories are important to understand right up front so you don’t have to undo any of your work. Additionally, here are some other concepts and terms to be aware of when connecting and mapping data in Data 360.

*   **Immutable:** Data that doesn’t change.  
    
*   **Normalized data:** Data that’s been organized and structured to reduce redundancy and improve data integrity. This makes it easier to create a standardized data format across a system.  
    
*   **Harmonization:** The process of taking raw data from multiple sources and normalizing it.  
    
*   **Primary key:** The field or attribute that uniquely identifies each record in a dataset. For example, in a loyalty data source, a customer ID is the unique identifier or primary key. Assigning a primary key ensures that your data is unique and retrievable.  
    
*   **Foreign key:** These ancillary keys in the source can link to the primary key of a different dataset. For example, in a sales order dataset, there’s a product ID that corresponds to the item purchased. This product ID links to a whole separate table with more details about that product, such as color or size. The instance of product ID on the sales order details dataset is the foreign key, and the instance of product ID on the product dataset is the primary key.  
    

Make a Plan
-----------

With these terms and considerations in mind, the next step is understanding all your potential data sources and what data is truly needed for your use case. This is an important step that you don’t want to skip!

### Consider Your Use Cases

First, review what use cases and measures your team needs. What data does your team want to access? What data do you want to provide access to your sellers/support reps/marketers? Consider all data options, including global sales data, web engagement, unstructured data from third-party sources, and so on.

### Document Your Data

Next, create a matrix (or more evolved, a data dictionary) for each of your data sources and associated datasets, along with special considerations for each dataset.

*   Take inventory of all possible data sources. Even if you don’t want to include all the data, list all possible data points. This includes traditional software, external databases, social media tools, CRM, customer service data, ecommerce, product information, engagement data, and so on.  
    
*   Identify all sets of data within that source. For example, marketing data might include behavioral data and profile information.  
    
*   Call out specific use cases **f**or that data. Not all data has to be connected to Data 360.  
    
*   Identify the primary key or any foreign keys in the dataset.  
    
*   Determine if the data is immutable or if the dataset needs to accommodate updates to existing records.  
    
*   Determine if there are any transformations needed. For example, is date and time data in various formats across your sources? Identify where you ‌want to improve the dataset with any additional [formula fields](https://help.salesforce.com/s/articleView?id=data.c360_a_formula_expression_library.htm&type=5).  
    
*   Review the attributes, or fields, coming from each data source. If the same field is tracked across multiple sources, decide which data source is most reliable or trusted. You can set an ordered preference for sources later on.  
    
*   Make sure you have the authentication details handy to access each dataset.  
    
*   Take note of how often the data gets updated.  
    

This document can take many shapes and can look different for every business. Here's an example of how to organize this information.

**Source**

**Dataset (DLO)**

**General Information**

**Specific Information**

**Our website**

Ecommerce clicks

*   **Type:** Structured  
    
*   **Category:** Engagement  
    
*   **Immutable:** No  
    
*   **Primary key:** Order ID  
    
*   **Updated regularly:** Y, real-time  
    

*   **Data source owner:** Joe, web support  
    
*   **Credentials****:** Info provided using LastPass.  
    

*   **Use case:** Identify a customer’s engagement on the website.  
    
*   **Formula Field needed:** N  
    
*   **Transformations:** N  
    

**Store location CSV**

Store location info

*   **Type:** Structured  
    
*   **Category:** Other  
    
*   **Immutable**: Yes  
    
*   **Primary key:** Store ID  
    
*   **Updated Regularly**: N  
    

*   **Use case:** Identify a customer’s nearby store.  
    
*   **Formula Field needed:** N  
    
*   **Transformations:** N  
    

**Loyalty****database**

Loyalty levels by customer

*   **Type:** Structured  
    
*   **Category****:** Profile  
    
*   **Immutable****:** No  
    
*   **Primary key:** Customer ID  
    
*   **Updated Regularly****:** Y, daily additions  
    

*   **Data source owner:** Jane, director of success  
    
*   **Credentials:** Provided  
    
*   **Use case:** Unify customer data with loyalty data.  
    
*   **Formula Field needed****:** Yes. Customers need to be over 18.  
    
*   **Transformations:** N  
    

Whatever format you use for this information, keep it handy as you connect each dataset required for your use case.

Available Data Sources and Connectors
-------------------------------------

Now that you know the steps and you have a plan, let’s review how you bring those sources into Data 360. Data 360 connects and ingests data from various built-in and external data sources through connectors and data streams. Connectors establish the connection between data sources, so your data can be easily accessed. Data 360 supports over 200+ connectors. These include Salesforce connectors, connector services, and other third-party connectors and integrations. Let’s review these options.

### Salesforce Connectors

Salesforce data from CRM sources (such as Sales, Service, or Industries), B2C Commerce, and Marketing Cloud Engagement, offer flexible connectors that allow you to choose between prebuilt solutions or custom implementations.

Starter data bundles are available for those who want to use premapped fields and relationships. By using data bundles, data lake objects (DLOs) are automatically mapped to the associated data model objects (DMOs). You can also create data streams manually by selecting from a list of available objects and manually mapping your data to DMOs. Or you can create data streams by using a data kit. Custom data kits streamline the creation of data streams and mappings.

### Connector Services

You can also connect data to Data 360 via the Ingestion API, MuleSoft, SDKs, and the Web and Mobile App connector. The Ingestion API connector provides a RESTful interface that supports streaming and bulk interaction patterns for programmatically loading data into Data 360. Built on the Ingestion API, the MuleSoft [Anypoint Connector for Salesforce Data Cloud](https://docs.mulesoft.com/salesforce-data-cloud-connector/latest/) supports bulk and streaming ingestion patterns to automate data ingestion from third-party systems and business applications.

To track and connect web behavior data to Data 360, use the Salesforce Interactions SDK or connect web and mobile data directly through event capture. Data 360 offers predefined data mappings for web and mobile instances to facilitate ingestion, which you can then query and activate across mobile and email. Learn more about the web and mobile connectors in the badge, [Web Engagement Data in Data 360.](https://trailhead.salesforce.com/en/content/learn/modules/web-engagement-data-in-data-cloud)

[](https://trailhead.salesforce.com/en/content/learn/modules/web-engagement-data-in-data-cloud)

### Third-Party Integrations

There are hundreds of available connectors and integrations—too many to list here. We have connectors for cloud storage, data lakes, streaming content, and advertising sources. Each type of connector has different steps to set up, so review the documentation to know what information is needed to start the connection. Whether they are generally available or in beta, Data 360 keeps adding new connectors for a wide range of companies from Adobe to Zendesk. Bookmark and visit the [Data 360 Integrations](https://developer.salesforce.com/docs/data/data-cloud-int/guide/c360-a-data-cloud-integrations.html) content guide for the latest information about all of our third-party integrations and partners.

Connect and Map Data
--------------------

Now that we have a plan and know about all the various connectors. In the next unit, let’s connect and map data to Data 360.

Resources
---------

*   [_Salesforce Help_: Data Sources in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_connectors.htm&type=5)
*   [_Salesforce Help_: Connectors and Integrations](https://help.salesforce.com/s/articleView?id=data.c360_a_sources_targets.htm&type=5)
*   [_Salesforce Developer_: Model Data in Data 360](https://developer.salesforce.com/docs/data/data-cloud-ref/guide/c360dm-model-data.htm)

Prueba
------

1 Which statement best describes a primary key?
A) An attribute that can have multiple values
B) A field that uniquely identifies a record in a dataset *
C) An optional field in a dataset
D) A field that stores historical data across DMOs

2 What is ‌good practice before starting to work with Data 360?
A) Integrate all your data ‌at once.
B) Create a matrix of data sources and details.
C) Discuss use cases with your team.
D) A and B
E) B and C *
