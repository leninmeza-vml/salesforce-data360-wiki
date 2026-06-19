Connect and Map Data
====================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Create connections and data streams.  
    
*   Learn about formula fields.  
    
*   Map data and build relationships.  
    
*   Review considerations.  
    

Connect Data and Create Data Streams
------------------------------------

Now that you’ve planned what data to bring into Data 360 and identified all available connectors, you're ready to connect data using data streams. As mentioned in the overview steps, before you can create data streams, your system admin needs to first connect the data source in Data Cloud Setup. The module, [Data Cloud Setup](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-for-admins) covers these steps. Once connections have been made, users with the right permission set can begin creating data streams. ‌

You can create data streams from a connection, data bundle, or data kits from the Data Streams tab. When creating a data stream, you specify the category (1) and primary key (2), and some optional steps like creating a new formula field (3). It’s important to set up these tools correctly to avoid rework later. ![New data stream options including object details: Category and Primary key. And an option to create a new formula field.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/connect-and-map-data/images/bacfc2d1742992e40a22cad4028e948d_kix.mrddtdoigl7q.png)

Before you get started connecting data, consider these factors.

*   A data model object inherits its category from the first data source object that maps to it. Once the data model object has its category set, all subsequent data source objects mapping to it must have the same category.  
    
*   There are some limitations and guidelines to follow in relation to data streams and ingestion. Review [Data 360 Limits and Guidelines](https://help.salesforce.com/s/articleView?id=data.c360_a_limits_and_guidelines.htm&type=5) to learn more.  
    
*   Make sure you connect and map fields with similar data types, such as text, number, or date. Otherwise, use the data transforms feature or formula fields to standardize formats before mapping.  
    
*   When you map a data object with the Engagement category, you must also map the Event Time Field.  
    

About Formula Fields
--------------------

When creating data streams you have the option to create formula fields before you create a data stream or you can create them after. Formula fields help you clean and adjust raw data. Connectors fetch the original shape of the data by retrieving the full source field list. Some data sources might require additional manipulation for use. For example, if the connector retrieves an age field as a raw number and you want to band the data into age groups like 18–24 years, 25–34 years, 35–44 years, 45+ years, you can achieve that by adding a new formula.

There are several formula functions you can use. They fall into four categories.

*   Text manipulation  
    *   For example: EXTRACT(), FIND(), LEFT(), SUBSTITUTE()  
        
*   Type conversions  
    *   For example: ABS(), MD5(), NUMBER(), PARSEDATE()  
        
*   Date calculations  
    *   For example: DATE(), DATEDIFF(), DAYPRECISION()  
        
*   Logical expressions  
    *   For example: IF(), AND(), OR(), NOT()  
        

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

You can also use fully qualified keys (FQK) to avoid key conflicts when data from different sources are ingested and harmonized in the Data 360 data model. Learn more in the badge, [Fully Qualified Keys in Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/fully-qualified-keys-in-data-cloud-quick-look).

Refresh Settings
----------------

In addition to settings, reviewing fields, and adding formula fields, you can also establish the data space a data stream should be associated with, along with ongoing refresh settings. Depending on the data source, data streams can operate on different refresh schedules. You can configure the scheduling details to manage how often data is refreshed. Some data streams support incremental refreshes, hourly refreshes, and weekly refreshes. You can also start a manual refresh of the data stream. Review the [data stream schedule](https://help.salesforce.com/s/articleView?id=data.c360_a_data_stream_schedule.htm&type=5) to find out how often you can refresh your data based on your use case.

Data Mapping
------------

We mentioned that once all the data streams are ingested into the system, there’s a source-to-target mapping experience that uses the Customer 360 Data Model to normalize the data sources. The Customer 360 Data Model consists of several objects covering a number of subject areas. Those subject areas include (but aren’t limited to) party, product, sales order, and email engagement. The model is extensible or customizable, as you can add custom attributes to standard objects or create all new custom objects.

To tie everything together, your data needs to be mapped to applicable fields in the standard data model. Pay special attention to attributes like names, IDs, email addresses, and phone numbers (or similar identifiers). This information helps you link an individual’s data together and ultimately build a unified profile of the customer. Let’s take a look at how mapping is done in Data 360. Search available data lake objects (1) and standard data model objects, also called DMOs or entities (2). Then within your selected DLO you can search for specific fields (3) to map.

![Data mapping screen.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/connect-and-map-data/images/a2bc0d32acd9499d0e068027454e5a76_kix.iriwsatl2m8m.jpg)

Relationships
-------------

If you use standard objects, relationships between objects are automatically populated when a key field is shared between the mapped objects in your DLO. Relationships can also be added in the DMO record’s Relationships tab (1). ![DMO Lead shown under the Data Model tab with the Relationship and Cardinality sections highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/connect-and-map-data/images/4295172a9aec474d037116e24e08b470_kix.bynkfhtj8er2.png)

Cardinality (2) or the type of relationship between two sets of data, is important to review. The relationship can be structured as a one-to-one or many-to-one relationship. One-to-one is pretty straightforward; a person can only have one birthdate. Many-to-one represents data that can have multiple values. For example, a person could have multiple email addresses or multiple credit cards. Why does this matter? Cardinality between objects has implications for segmentation and activation and can’t be changed after the relationship is created. Review [Data Model Object Relationships](https://help.salesforce.com/s/articleView?id=data.c360_a_data_model_object_relationships.htm&type=5) to dive more into this topic.

Once data is connected and mapped, your data model grows and expands! Check out the graph view (1) from the Data Model tab to see your mapped DMOs and their relationships.

![Data model graph view showing relationships between DMOs.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/connect-and-map-data/images/9ef9d718d776a9fcd52031551edb8a43_kix.2ds0kxofoedd.png)

Data Stream Information
-----------------------

Once a data stream is created, select it from the Data Stream home page to find details about processed record status (1), mapped fields (2), and refresh history (3). Use the history tab to monitor regular processing and troubleshoot errors. You can also add fields, formula field, and refresh your data stream from this page.

![Data stream home page with field information, status details, mappings, and refresh history.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-connectors-and-integrations/connect-and-map-data/images/e28d781784fcc60355fa1dc59f08546b_kix.qullkbd1fprn.png)

Get Hands-on with Data 360
--------------------------

Get started by following the steps in [Explore Data 360 Core Functionality](https://trailhead.salesforce.com/content/learn/projects/explore-data-cloud-core-functionality). By connecting, harmonizing, and then unifying any data source, businesses can achieve a comprehensive understanding of their customers, leading to amazing outcomes. Data 360 makes this possible and achievable thanks to a variety of connectors and integrations and a standardized model.

Resources
---------

*   [_Trailhead_: Data 360 Basics for Marketers](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-basics)
*   [_Salesforce Help_: Data Federation, Ingestion, and Modeling](https://help.salesforce.com/s/articleView?id=data.c360_a_data_ingestion_and_modeling.htm&type=5)
*   [_Trailhead_: Customer 360 Data Model for Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-data-model-for-customer-data-platform)
*   [_Salesforce Help_: Create a Data Stream from a Data Kit](https://help.salesforce.com/s/articleView?id=sf.c360_a_install_package_kit.htm&type=5)
*   [_Salesforce Help_: Create a Formula Field](https://help.salesforce.com/s/articleView?id=data.c360_a_formula_expression_library.htm&type=5)
*   [_Salesforce Help_: Data Mapping](https://help.salesforce.com/s/articleView?id=data.c360_a_data_mapping.htm&type=5)

Prueba
------

1 Data 360’s standard data model, Customer 360 Data Model, is extensible and customizable. What does this allow you to do?

A) Share data with anyone.
B) Add custom attributes and objects. *
C) Resolve anonymous data across segments.
D) Use AI to build your data model.

2 What type of relationship would a DMO have between a marketing email campaign with email engagement data to a loyalty program?

A) One-to-one.
B) Many-to-one. *
C) Many-to-many.
D) It’s complicated.
