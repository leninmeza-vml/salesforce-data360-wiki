# Configure Data 360 to Calculate an Account's Cases

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create a data stream for Salesforce CRM data.  
    
*   Verify data mapping.  
    
*   Use a calculated insight to create a rollup summary for objects with a lookup relationship.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

We know you'd love to try this module yourself, but if you want to get hands-on, you'll need to use your own Data 360 org. Enrichments aren't available in Trailhead Playground orgs.

## What Are Copy Field Enrichments?

With copy field enrichments, you can copy valuable Data 360 insights directly into your CRM, giving your users relevant, up-to-date analysis from all your data sources without writing code. For example, you can copy an account's total lifetime value from all your lines of business into your custom Total LifeTime Value field in Sales, giving your sales team valuable insight into your top customers.

In this module, we enrich your accounts with case information, giving your sales team relevant information they can use during their customer outreach. We start by using Data 360 to aggregate case data from all your sources. Then, we create a calculated insight to calculate the total number of cases and the total number of open cases. And, in Sales, we copy these insights to new fields on your accounts, so your sales team can quickly see which accounts need your attention and which might be open to new opportunities.

## Let Your Sales Reps Quickly See Open Cases on Their Accounts

You're a Data Cloud Architect, and you want to help sales reps learn more about their accounts' service escalations. Armed with this information, a sales rep can quickly reach out and promote alternate products or support packages. Wataru, a sales rep, wants to connect with his accounts and let them know about a promotion for a new software pack. He knows that some accounts have several open cases, but the new software pack will resolve his customer's issues.

Wataru needs to quickly see which accounts have a high number of open cases so he can share the exciting news about the promotion. To help Wataru target customers more efficiently, you create a copy field enrichment on Accounts that displays total cases and total open cases from all your company's Service orgs. Let's review the steps you can take to help Wataru.

## Create an Account and a Case Data Stream

The first step is to ingest your Account data from Sales and your Case data from Service into Data 360. From within your Data 360 account, follow these steps.

1.  From **Data Cloud**, select **Data Streams**, then click **New**.  
    
2.  Select **Salesforce CRM**, then click **Next**.  
    
3.  Select **All Objects**, search for and select **Account**, then click **Next**.  
    
4.  Accept the default selections and click **Next**.  
    
5.  Select the **Profile** category. Profile data contains general information about a person or organization, while engagement data contains time-sensitive information.  
    
6.  Accept the default data stream name and click **Deploy**.  
    
7.  Repeat the above steps for the **Case** object.  
    

Your account and case data are now available in Data 360. In the screenshot below, on the data stream page, the Data Stream Status column shows that your account data stream from Sales and your Case data stream from Service are active. The Total Records column shows that 13 account records and 26 case records are ingested into Data 360.

![The data stream page showing the Account_Home and the Case_Home data streams.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/configure-data-cloud-to-calculate-an-accounts-cases/images/dadc910e6c5385ce73c334710c68c8fd_kix.ooyyzd9borep.png)

## Map Your Data Streams

Let's add structure to your ingested Salesforce CRM data by mapping the data lake objects to standard data model objects (DMOs).

1.  In Data Cloud, select **Data Streams**, then select the **Account\_Home** data stream.  
    
2.  In the **Data Mapping** section, click **Start**.  
    
3.  In Data Model entities, click **Select Objects**, then select **Account** and click **Done**.  
    
4.  Review the default mappings to ensure that the Account ID is mapped from the data stream to the DMO. Enrichments uses account ID mapping to match an account in Sales to an account in Data 360.  
    
5.  Click **Save**.  
    

![screenshot of Data Mapping that shows the Account_Home data stream's Account ID field mapped to the Account DMO's Account ID field.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/configure-data-cloud-to-calculate-an-accounts-cases/images/69f30fd5c0a4d5f7628ea547487574ca_kix.5zghh13sblls.png)

6.  Follow the above steps to map the Case\_Home data stream to the Case DMO. If required, map the Account ID from the DLO to the Account field in the DMO.  
    

## Create a Calculated Insight

To enrich our accounts with a summary of case information, let’s follow the steps below to create a calculated insight that calculates the total number of cases and the total open cases for an account. This type of calculation is called a roll-up summary.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

You can use a calculated insight to define and calculate multidimensional metrics. To use a calculated insight in a copy field enrichment, the calculated insight must have a single dimension.

1.  In Data Cloud, select the **Calculated Insights** tab, then click **New**.  
    
2.  Leave the Data Space as **default**.  
    
3.  Click **Create with SQL Expression** and click **Next**.  
    
4.  Name your insight `Open Cases on AccountCopiar`.  
    
5.  Enter this SQL query.  
    

Select ssot\_\_Account\_\_dlm.ssot\_\_Id\_\_c as Id\_\_c, Count(\*) as total\_cases\_\_c, COUNT(CASE WHEN ssot\_\_Case\_\_dlm.ssot\_\_IsClosed\_\_c != 'true' THEN 1 END) as total\_open\_cases\_\_c from ssot\_\_Account\_\_dlm INNER JOIN ssot\_\_Case\_\_dlm on ssot\_\_Case\_\_dlm.ssot\_\_AccountId\_\_c = ssot\_\_Account\_\_dlm.ssot\_\_Id\_\_c group by ssot\_\_Account\_\_dlm.ssot\_\_Id\_\_c

6.  To check whether your SQL expression is valid, click **Check Syntax**. If it isn’t valid, you won’t be able to continue.  
    

Ignore the warnings. Because we're bringing in data from only one CRM, we don't need to add a key qualifier.

7.  Click **Activate**.  
    
8.  From the Schedule dropdown, select a **1-hour schedule**.  
    
9.  Click **Enable**.  
    

Your calculated insight has been created.

## Understand and Verify Your Calculated Insight

Calculated insights use SQL to create metrics (also called measures) and dimensions. In Sales, when you create a copy field enrichment from a calculated insight, you choose which metrics to map to your Sales fields. Then, you use the dimension to identify which account or individual the metrics apply to.

Our calculated insight creates a total cases metric, a total open cases metric, and an account ID dimension.

| **SQL Clause** | **Field Type** | **Field Name** |
| --- | --- | --- |
| `ssot__Account__dlm.ssot__Id__c AS Id__c, COUNT(*) AS total_cases__cCopiar` | metric | `total_cases__cCopiar` |
| `COUNT(CASE WHEN ssot__Case__dlm.ssot__IsClosed__c != &#39;true&#39; THEN 1 END) AS total_open_cases__cCopiar` | metric | `total_open_cases__cCopiar` |
| `GROUP BY Id__cCopiar` | dimension | n/a |

Later, when we create our copy field enrichment, we’ll map each of these metrics to a new field on accounts. When the copy field enrichment runs, it uses the account's ID (the `Id_cCopiar` dimension) to make sure it copies the right number of cases to the right account.

Let’s verify your calculated insight.

1.  From **Calculated Insights**, select the **Open Cases on Account** calculated insight.  
    
2.  Ensure the status is **Active**, the **Last Run Time** has a value, and the **Last Run Status** shows Success.  
    
3.  Click **Output** to see the calculated metrics and the dimension.  
    

![The Output tab of the Calculated insight. Output tab shows the fields ID, total_open_cases, lastModifiedDate, and total_cases. The Id field is a dimension and the fields are metrics.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/configure-data-cloud-to-calculate-an-accounts-cases/images/105f82bad022648d325a59804edd35bd_kix.6t5b3nnv60th.png)

To verify the calculated insight's calculated data, run a report.

1.  From Calculated Insights, select your **Open Cases on Account** calculated insight.  
    
2.  Select the down arrow icon ( ![“”](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/configure-data-cloud-to-calculate-an-accounts-cases/images/e6707033ee963d5641a09210e8585550_kix.sq11rev3uznd.png)), then select **Create Report**.  
    
3.  Ensure the total cases and total open cases for your reports are calculated correctly.  
    

For example, in the screenshot below, an account with ID 0016P000008D9DwQAK has 7 total cases, with 2 cases open.

![The New OpenCase report: Each row shows the account ID, the total number of cases, and the total open cases.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/configure-data-cloud-to-calculate-an-accounts-cases/images/e7f7d68e479a3f1c28eb02dfad37f227_kix.p8lmisviy7tw.png)

## Summary

Now you know how to ingest Salesforce CRM data and create a calculated insight that you can map to a field on a Salesforce CRM object. In the next unit, we cover how to give your CRM users permissions to access information in Data 360.

## Resources

*   [_Trailhead_: Data 360 Insights Using SQL](https://trailhead.salesforce.com/content/learn/modules/customer-data-platform-insights-using-sql)
*   [_Salesforce Developers_: Join Records from Different Objects to Get a Rich Result Set](https://developer.salesforce.com/docs/data/data-cloud-query-guide/guide/query-joins.html)
*   [_Salesforce Help_: Use SQL Statements to Create Insights](https://help.salesforce.com/s/articleView?id=data.c360_a_create_a_calculated_insights_sql_function.htm&type=5)
*   [_Salesforce Help_: Calculated Insights](https://help.salesforce.com/s/articleView?id=data.c360_a_calculated_insights.htm&type=5)
*   [_Salesforce Help_: SQL Rules for Insights](https://help.salesforce.com/s/articleView?id=data.c360_a_calculated_insights_general_sql_rules.htm&type=5)

Respuestas de la prueba:

---

**Pregunta 1 — What category should they use when setting up the data stream for general information about a person or organization?**

**Respuesta: C — Profile.**

El documento especifica que la categoría **Profile** contiene información general sobre una persona u organización, mientras que la categoría Engagement contiene información sensible al tiempo.

---

**Pregunta 2 — How many dimensions must the calculated insight have to power a copy field enrichment?**

**Respuesta: B — One.**

El documento indica explícitamente que para usar un calculated insight en un copy field enrichment, el calculated insight debe tener **una sola dimensión**. En el ejemplo, esa dimensión es el Account ID (`Id__c`) que se usa para identificar a qué cuenta corresponden las métricas calculadas.
