# Get Started with Zero Copy Data Federation

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain what zero copy is and identify its benefits.  
    
*   Explain what zero copy data federation is.  
    
*   Identify the differences between zero copy query federation and zero copy file federation.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Before You Start

Before you start this module, consider completing this recommended content.

*   [Data 360-Powered Experiences](https://trailhead.salesforce.com/content/learn/modules/data-cloud-powered-experiences)  
    
*   [Data 360 Connectors and Integrations](https://trailhead.salesforce.com/content/learn/modules/data-cloud-connectors-and-integrations)  
    

## What Is Zero Copy?

With zero copy, you can bidirectionally connect Data 360 to external systems, such as data warehouses. It allows you to freely access data from your data source and use it in Data 360—such as in identity resolution and segmentation—without duplicating your data. Then you can share data from Data 360 back to ‌external systems.

Before zero copy, integrating data from external systems was a challenge. You had to physically copy the data into Salesforce, which was time-consuming and resource-intensive. With zero copy, you can access and activate data from external systems, anytime and anywhere.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Zero copy consumes Data 360 credits. Learn more in [Data 360](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look) [Credit](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look) [Consumption](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look)[: Quick Look](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look) and [Billing Considerations for Data Federation](https://help.salesforce.com/s/articleView?id=data.c360_a_billing_considerations_for_data_federation.htm&type=5).

## Zero Copy Capabilities

Zero copy consists of two main capabilities—zero copy data federation and zero copy data sharing. Together, they create a two-way communication between Data 360 and the external system. Data federation gives Data 360 access to external data, while data sharing gives the external system access to Data 360’s data. Data 360 and the external system mutually query each other’s data.

## Benefits of Zero Copy

Here are the key benefits of zero copy in Data 360.

*   **Total** **d****ata** **f****luidity:** With zero copy, you can overlay Data 360 on top of your existing IT architecture to create a virtual and harmonized operational layer that only accesses data as and when needed.  
    
*   **Real-****t****ime** **d****ata** **a****ccess:** No more waiting for data to sync or update. You get the latest information every time you need it.  
    
*   **Simplified** **i****ntegration:** Zero copy simplifies the integration process. You don’t need to set up complex and costly data pipelines.  
    
*   **Enhanced** **g****overnance and** **c****ompliance:** Fewer persistent copies of data means fewer vulnerabilities and security breaches.  
    

![Diagram showing the bidirectional flow of data from the external system to Data 360, using query federation, file federation, and data sharing.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-with-zero-copy/get-started-with-zero-copy-data-federation/images/62191589124c2eec0714fe3cf185cdeb_kix.wshi2224n284.png)

Next, explore one of zero copy’s key capabilities: data federation.

## Zero Copy Data Federation

Data federation gives you direct access to external data in Data 360. To federate data, use a zero-copy connector to connect Data 360 and the external system. There are two types of zero-copy connectors: query federation and file federation.

Query federation and file federation give you access to different layers of the external system.

*   **In** **q****uery** **f****ederation**, Data 360 sends a query to the external system’s compute layer, or its query engine, which queries the underlying storage layer and returns the relevant records to Data 360. External compute is involved. All external systems support query federation.  
    
*   **In** **f****ile** **f****ederation**, Data 360 directly queries the storage layer using its own compute engines. Not all external systems support file federation.  
    

These processes might sound complicated and unfamiliar, so consider the inner workings of query and file federation using a library metaphor.

In the scenarios that follow, the book borrower represents Data 360. The clerk represents the external system’s “worker,” or query engine. The library holds high-value and classified books, so it has two rooms: the clerk’s room and the book room.

### Scenario 1: Query Federation in the Compute Layer

In this scenario, you can’t access the book room on your own, so you need to request a book from the clerk.

Now look at an interaction. Pay attention to the bolded words.

1.  You **request** the book from the clerk in the **clerk’s room**. Your request must follow some **rules**. It must be in the format and language that the clerk understands, and it must be a task the clerk’s willing to do.  
    
2.  The clerk parses your request.  
    
3.  The clerk goes into the **book room**, retrieves the book, and gives the book to you.  
    

Next, look at the bolded words in technical terms.

*   The book request represents a query from Data 360 to the external system. Data 360 asks the external system for a piece of data. This act of querying is called **query federation**.  
    
*   The clerk’s room represents the **compute layer**. This is where computations, or units of work, are performed.  
    
*   The rules represent a **query language**, such as SQL. You need to formulate the query in the appropriate language for the external system to understand your request.  
    
*   The book room represents the **storage layer**. This is where data from the external system is stored. You learn more about the storage layer in Scenario 2.  
    

Here’s the interaction rephrased in technical terms, between Data 360 and the external system.

1.  You connect Data 360 and the external system using a query federation connector.  
    
2.  Data 360 queries the external system in the compute layer.  
    
3.  The external system’s query engine understands and is willing to execute the query.  
    
4.  The query engine executes our query, retrieves the data from the storage layer, and supplies the results to Data 360.  
    

With query federation, users in Data 360 can query data from the external system while staying within the external system’s capabilities.

### Scenario 2: File Federation in the Storage Layer

In this scenario, you’re a high-ranking official with specific and limited access to the library. You can borrow a book without going through the clerk and the clerk’s room if the book is within your access permissions.

Here’s how the interaction goes. Pay attention to the bolded words.

1.  In the clerk’s room, the owner of the library explicitly gives you permission to enter the **book room** and gives you a **set of rules** to follow.  
    
2.  You enter the book room.  
    
3.  You use your **knowledge** of the **book room layout** and quickly find the **book** you want. You retrieve the book and exit the room.  
    

Now look at the bolded words in technical terms.

*   The book room is the **storage layer**, where the external data files are stored.  
    
*   The **set of rules** represents your access to sections of the storage layer and how you’re allowed to search for and retrieve data.  
    
*   The book room layout is the **database table format**. This is how the files are organized in the storage layer. A common open-table format is Apache IcebergTM.  
    
*   The book is the **data file** that you retrieved.  
    

Here’s the interaction rephrased in technical terms, between Data 360 and the external system.

1.  You connect Data 360 and the external system using a file federation connector.  
    
2.  Data 360 uses its own trusted compute engines to query the storage layer and retrieve the data file.  
    

With file federation, users in Data 360 can query data from the external system without limitations.

### The Zero Copy Partner Network and External Systems

The [Zero Copy Partner Network](https://www.salesforce.com/data/zero-copy-partner-network/) is a collection of organizations that are committed to bidirectional zero-copy integrations with Data 360. These organizations support file federation, query federation, and data sharing.

Zero copy is also compatible with external systems outside the partner network.

## Query Federation vs File Federation

Now that you know what query federation and file federation are, how do you know which type of connector to use? This table lets you compare the features of each.

| **Query Federation** | **File Federation** |
| --- | --- |
| *   Reads files from the compute layer, using the external query engine.  <br>    <br>*   Higher costs due to external computation. You might pay compute fees to the external system.  <br>    <br>*   All compatible systems support query federation.  <br>    <br>*   Must enable caching to use trigger-based Data 360 features, such as data actions. | *   Reads files directly from the storage layer, using Data 360’s trusted compute engines.  <br>    <br>*   Lower costs because you don’t pay external compute fees.  <br>    <br>*   Optimized for accessing and analyzing large datasets.  <br>    <br>*   Best for companies with a lot of data in table formats such as Apache IcebergTM.  <br>    <br>*   Use trigger-based Data 360 features, such as data actions, that rely on being able to detect changes in an external system |

File federation is recommended whenever it’s supported.

Now you have knowledge about the different types of data federation. In the next unit, explore some use cases for data federation and learn how to set it up.

## Resources

*   [_Salesforce Help_: Zero Copy Data Federation](https://help.salesforce.com/s/articleView?language=en_US&id=data.c360_a_byol_data_federation.htm&type=5)
*   [_External_: Apache Iceberg](https://iceberg.apache.org/)
*   [_Salesforce News_: Salesforce Unveils Zero Copy Partner Network](https://www.salesforce.com/news/press-releases/2024/04/25/zero-copy-partner-network/)
*   [_Salesforce Help_: Data Actions in Data 360](https://help.salesforce.com/s/articleView?id=sf.c360_a_data_actions_CDP.htm&language=en_US&type=5)

## Respuestas

---

**Pregunta 1:** What does zero copy data federation do?

✅ **B — It gives you access to external data directly in Data 360 without physically copying it.**

El documento lo explica claramente: con zero copy puedes acceder y usar datos de sistemas externos en Data 360 *"without duplicating your data"*, eliminando la necesidad de copiarlos físicamente.

---

**Pregunta 2:** What are the advantages of file federation over query federation?

✅ **A — File federation is optimized for larger datasets and uses Data 360's compute engine, which lets you avoid external compute fees.**

La tabla comparativa del documento lo confirma: file federation tiene *"lower costs because you don't pay external compute fees"* y está *"optimized for accessing and analyzing large datasets"*, usando los motores de cómputo propios de Data 360 en lugar del sistema externo.

---
