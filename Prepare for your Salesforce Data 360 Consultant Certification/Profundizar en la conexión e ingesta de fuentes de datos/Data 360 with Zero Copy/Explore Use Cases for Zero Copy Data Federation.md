# Explore Use Cases for Zero Copy Data Federation

## Learning Objectives

After completing this unit, you’ll be able to:

*   Identify key use cases for data federation.  
    
*   Explain steps to set up a zero-copy connector in Data 360  
    

## Use Cases for Data Federation

Use data federation whenever you need to use external data in Salesforce. Here are some key use cases to help you brainstorm how your organization can use external data.

*   Enrich CRM data about customer purchases from Commerce Cloud with transaction data from external systems.  
    
*   Enrich unified profiles and create insights in Data 360 with transaction data stored in Google BigQuery.  
    
*   Create effective service agents in Agentforce Builder that have access to data stored in Snowflake, such as loyalty programs and transactions.  
    
*   Run targeted campaigns in Data 360 based on customer purchasing data stored in Amazon Redshift.  
    
*   Use Einstein Studio to create an AI model to predict customer churn, with customer satisfaction data stored in Databricks.  
    

Now look at an Agentforce use case more closely, featuring Northern Trail Outfitters (NTO), an outdoor apparel retailing company.

## NTO Uses Data Federation with Agentforce

Northern Trail Outfitters has 600M transactions daily across all stores and online sales. This transaction data includes which coupons a customer used. NTO needs a system to help the company use this data, in conjunction with its customer information in Salesforce, to create highly personalized coupons offerings. NTO also wants to use Agentforce to create service agents that can proactively offer these coupons to customers.

To achieve this, NTO creates a data federation connection to access these transactions from its Snowflake instance. Then NTO joins the transaction data with customer information in Data 360 and creates a calculated insight to understand household-based coupon usage. NTO also creates a prompt template that takes the calculated insight result and generates a personalized coupon.

In Agentforce Builder, NTO creates a service agent with a custom action that uses the prompt template. Now the agent can offer personalized coupons based on the customer’s history.

Learn more about configuring agents in [Agentforce Key Components: Quick Look](https://trailhead.salesforce.com/content/learn/modules/agentforce-agents-quick-look).

## Federate External Data into Data 360

To set up a data federation connection and federate external data into Data 360, follow these high-level steps. These steps assume you have access to Data 360 setup.

### Step 1: Plan Data Strategy

Define a use case that needs external data. For example, NTO needs transaction data to create personalized coupons and offer them using agents. Identify where that data is, such as Snowflake.

### Step 2: Collect Information on External System

Collect information on the external system, such as the database name, connection URL, and credentials. You need this information to create the connector in the next step.

### Step 3: Create a Data Federation Connection

In Data Cloud setup, create a connection to the external system. Depending on what the external system allows, choose a query federation or file federation connector.

### Step 4: Create a Data Stream Using the Connection

By default, Data 360 queries, or federates, external data when requested at runtime. This mode is called “live query.” Zero data is persisted.

If you select a query federation connector, you can choose to cache data in Data 360. This can lower latency when querying larger datasets, but impacts your costs. If you select a file federation connector, the data is always live-queried by Data 360.

Now you can access external data in Data 360. Put this data to action in agents, predictive models, segments, and more. Next, learn how to share data from Data 360 to external systems.

## Resources

*   [_Salesforce Help_: Zero Copy Data Federation](https://help.salesforce.com/s/articleView?language=en_US&id=data.c360_a_byol_data_federation.htm&type=5)
*   [_Salesforce Help_: Caching in Data Federation](https://help.salesforce.com/s/articleView?id=data.c360_a_accelerated_data_lake_objects.htm&type=5)
*   [_Salesforce Help_: Data Streams in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_streams.htm&type=5)
*   [_Salesforce Help_: Billing Considerations for Data Federation](https://help.salesforce.com/s/articleView?id=data.c360_a_billing_considerations_for_data_federation.htm&type=5)

## Respuestas

---

**Pregunta 1:** What's a use case for data federation?

✅ **C — To enrich unified profiles in Data 360 with external loyalty program data.**

El documento lista casos de uso concretos, entre ellos: *"Enrich unified profiles and create insights in Data 360 with transaction data stored in Google BigQuery"* y el uso de datos de programas de lealtad desde Snowflake para agentes de Agentforce. La opción C refleja exactamente este tipo de escenario.

---

**Pregunta 2:** What's the first step in setting up a zero copy connector in Data 360?

✅ **A — Define a use case that needs external data and identify where the data is.**

El documento es explícito: el **Step 1** es *"Plan Data Strategy"*, que consiste en definir el caso de uso e identificar dónde está la data. La opción D (recopilar credenciales) corresponde al **Step 2**, no al primero.

---
