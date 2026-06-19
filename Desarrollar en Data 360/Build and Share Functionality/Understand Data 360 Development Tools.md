# Understand Data 360 Development Tools

## Learning Objectives

After completing this unit, you’ll be able to:

*   Locate developer resources for language-specific client libraries, such as the Python Connector.  
    
*   Find and extend functionality with Data 360 APIs.  
    
*   Explain the role of sandboxes and data kits.  
    

## Before You Start

This badge is part of the [Data 360: Develop and Build Solutions](https://trailhead.salesforce.com/content/learn/trails/data-360-develop-and-build-solutions) trail. The trail expands your skills by introducing advanced features, developer tools, and end-to-end solutions by using Data 360 (formerly Data Cloud). In this badge, learn about available developer resources and tools, select the appropriate API for your use case, and get an overview of options for creating your dev environment.

## Gather Developer Resources

To accelerate development, Data 360 offers language-specific client libraries and tools.

*   **Python Connector:** Ideal for data scientists and analysts, use Python with Data 360 data to model data in your Jupyter Notebook.  
    
*   **Java Database Connectivity (** **JDBC) Driver:** For high-volume ingestion, use the JDBC driver to let Java apps connect to Data 360.  
    
*   **Postman Collection** : Try out API calls with the Data 360 Connect API Postman collection. The collection has a preconfigured org and auth setup, along with documentation and working code examples, to make it easy to try out new methods. The Data 360 REST API collection also includes tested examples but is a subset of the total REST API.  
    

Explore the [Developer Center](https://developer.salesforce.com/developer-centers/data-cloud) to find and bookmark developer guides and other content related to Data 360

## Select the Right API

Whether you’re loading data, retrieving profiles, or running complex queries, selecting the right API depends on your specific goal. Here are the API options available to programmatically interact with Data 360.

*   **Data 360 Connect REST API:** This is the most commonly used API for Salesforce app development. Use this API for object-oriented queries and integration with the Salesforce Platform. This API lets you update and change data in Data 360.  
    
*   **Data 360 REST API:** The Data 360 REST API is most popular with integration and web developers. It’s designed for high-scale ingestion and query capabilities, but includes some additional functionality for data unification, data graph creation, and other functions.  
    *   **Ingestion API:** Use this for high-volume data loading. It supports both batch ingestion, for example daily or weekly loads, and streaming ingestions for near real-time micro-batches.  
        
    *   **Data 360 SQL Query API:** To retrieve data that use custom SQL queries, use this API to access data lake objects (DLOs), data model objects (DMOs), and calculated insights. It supports ANSI standard SQL for querying.  
        

Watch this [video](https://salesforce.vidyard.com/watch/cTet8JYsu9zd6QsqxFkkwN ) to learn how to retrieve data from Data 360 using the Data 360 Connect REST API and Postman.

## Establish a Secure Development Environment

Sandboxes are critical for testing data modeling and ingestion, without impacting production data. Cloned sandboxes include metadata, but not data, letting you test against sample data, rather than duplicating costs for a full production org. Curious about sandboxes? Check out this [white paper](https://sfdc.co/d360_sandbox) .

## Streamline Deployments with Data Kits

As a developer, moving configurations between environments (like from sandbox to production) or between data spaces requires a robust packaging strategy. In Data 360, data kits are the primary mechanism for this. A data kit is a portable, customized bundle of packageable metadata created within Data 360. It lets you wrap together Data 360 objects, metadata, relationships, and other components with a few clicks, streamlining the package creation and installation process.

## What’s Next?

Data kits are useful for standardizing data ingestion across multiple business units or implementing industry-specific data models efficiently. Data kits also help maintain consistency across different orgs allowing for the development of AppExchange solutions. To get started with data kits, continue on to the next badge in this journey, [Packaging and Data Kits](https://trailhead.salesforce.com/content/learn/modules/packaging-and-data-kits-in-salesforce-cdp) .

## Resources

*   [_Salesforce Postman_ : Salesforce Data 360 APIs](https://www.postman.com/salesforce-developers/salesforce-developers/collection/vkln4gx/salesforce-data-360-apis)
*   [_Salesforce Developers_ : Data 360 Developer Center](https://developer.salesforce.com/developer-centers/data-cloud)
*   [_Salesforce Developers_ : Data 360 Connect REST API](https://developer.salesforce.com/docs/data/connectapi/overview)
*   [_Salesforce Developers_ : Data Cloud Ingestion API](https://developer.salesforce.com/docs/data/data-cloud-int/references/data-cloud-ingestionapi-ref/c360-a-api-ingest-data.html)

## Preguntas

**Pregunta 1:** ¿Qué API es más adecuada para cargar grandes cantidades de datos en un horario diario o semanal?

✅ **C — Ingestion API**

El documento lo confirma: *"Ingestion API: Use this for high-volume data loading. It supports both batch ingestion, for example daily or weekly loads, and streaming ingestions for near real-time micro-batches."*

---

**Pregunta 2:** ¿Cuál es la función principal de un data kit en Data 360?

✅ **B — To bundle packageable metadata for streamlined installation and deployment**

El documento lo define claramente: *"A data kit is a portable, customized bundle of packageable metadata created within Data 360. It lets you wrap together Data 360 objects, metadata, relationships, and other components with a few clicks, streamlining the package creation and installation process."*