# Run Queries and Personalize Engagement with Segmentation

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain how to run queries in Data 360 to filter, join, and explore harmonized datasets.  
    
*   Describe how insights transform raw data into metrics that guide smarter decisions and power personalization.  
    
*   Explain the purpose of segmentation in Data 360 for targeted engagement.  
    
*   Define data graphs and explain their role in organizing and querying complex data relationships within Data 360.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Before You Start

This badge is part of the [Data 360: Explore Setup to Activation](https://trailhead.salesforce.com/content/learn/trails/data-cloud-explore-setup-to-activation) trail. The trail is designed to give you hands-on experience with the core functionalities of Data 360.

In this badge, you learn how to use the full potential of your business data within Data 360. Begin by exploring how you can query, create insights, then delve into the specifics of how segmentation enables targeted customer engagement. And finally, reveal the critical role of data graphs in organizing and making your data actionable.

## Query Data in Data 360

Queries are how you ask questions about your data in Data 360. Once your customer information is unified into data model objects (DMOs) and data lake objects (DLOs), you can run queries to filter, join, and explore that data. Want to know which customers made more than two purchases in the past 3 months? Or what’s the average amount your loyalty members spent in New York? Queries give you those answers and more. They’re also the building blocks for creating insights, defining audience segments, and powering real-time personalization.

You’ve got a few options for running queries, depending on your use case.

*   **Integrated Apps:** Explore and query data using a visual interface: no coding required. You can work with apps like Query Editor and DBeaver.  
    
*   **Object-Specific APIs:** Use the Data 360 Connect REST API or the Data 360 REST API for object-oriented queries.  
    
*   **Language-Specific Client Libraries:** Choose from JDBC, Python, or the Connect API for Apex to connect your apps directly to Data 360.  
    
*   **SQL Query APIs:** Run custom SQL queries through REST API calls with the Data 360 Connect API (REST API or Apex).  
    

## How Northern Trail Outfitters Uses Queries to Drive Engagement

Northern Trail Outfitters (NTO), an outdoor gear retailer, wants to understand which of its loyalty members are most engaged. The marketing team runs a query in Data 360 to identify customers who purchased more than two items in the past 3 months and also redeemed loyalty points during that period.

With this query, they discover that repeat buyers in urban areas are actively using their loyalty rewards. The team then builds an audience segment from this query to launch a personalized email campaign that promotes new hiking gear and offers bonus points for online purchases.

By running a query on unified customer data in Data 360, NTO quickly identifies high-value customers and delivers tailored engagement that drives sales and strengthens loyalty.

## Data 360 Insights

When raw information is transformed into metrics, it’s easier to understand and act on.Instead of working only with basic attributes like age or location, you can calculate meaningful measures such as customer lifetime value or engagement level. These insights help you uncover hidden trends, guide smarter decision-making, and personalize customer experiences effectively.

There are several types of insights you can work with.

*   **Calculated insights** use rules and formulas to transform existing data into meaningful values, such as total spend or average order size.  
    
*   **Streaming insights** keep an eye on live events, like a website visit or app click, and process that activity as it happens.  
    
*   **Real-time insights**, powered by real-time data graphs, update in milliseconds as new data flows into Data 360, so you're always working with the latest information.  
    

## Insights Builder and SQL

You can create insights in Insights Builder or with SQL. If you prefer a guided experience, Insights Builder is the way to go. It is a no-code tool that walks you through the process of defining an insight. You can select your data sources, apply filters, and define calculations through an easy-to-use interface. For example, you can create a calculated insight to track average order value by setting up a formula that divides total spend by the number of purchases.

For more advanced scenarios, turn to SQL Insights. This option lets technical users write SQL queries directly against harmonized data. It’s especially useful when you need to join multiple datasets, apply complex logic, or create highly customized metrics. For instance, you can write a query that finds customers who spent more than $500 in the past 90 days and engaged with support chat more than twice.

## Use Cases for Insights

Companies use insights in many ways, from identifying high-value customers to predicting churn or tailoring offers that boost engagement. Streaming insights can even trigger immediate responses, like sending a follow-up offer when a cart is abandoned. By turning raw data into business-ready metrics, insights create the foundation for stronger customer relationships and more precise decision-making.

Insights also power more effective segmentation in Data 360. While basic profile attributes can group customers into broad categories, insights make those segments far more meaningful. Instead of simply targeting loyal customers, you can segment loyal customers with high engagement scores in the past 30 days, or customers who recently viewed a product but did not complete a purchase. By using calculated and real-time insights, your segments become smarter and more precise. That means you can reach the right people at the right time with messages that feel relevant, personal, and timely.

### Segmentation

Segmentation in Data 360 is the process of creating, filtering, and audience segments to define precise audience groups for various campaigns and engagements. Its primary goal is to harmonize fragmented data from different sources into a single, comprehensive customer profile, enabling personalized experiences and better engagement across all channels.

Data 360’s capability to unify all your data for smarter data sharing and activation means your data model significantly impacts segmentation, allowing for targeted segmentation through identifiable filtering options. Combine segmentation with insights to define audiences that are not only accurate, but also dynamic so your campaigns resonate with the right people at the right time.

To see this in action, consider a few examples. A company might reengage customers by creating a container for email engagement that groups customers who opened more than five emails (use count is at least six) to send an email with the subject line “Winter Clearance.”

A retailer in New York or San Francisco might reward high spenders by building one container with filters for both sales order (a purchase over $1,000 in September) and the right location (city name is New York, NYC, San Francisco, SF).

To invite engaged SMS subscribers to a running club, a fitness brand could create a segment with conditions like use count is at least 1 and EngagementChannelAction equals opt in, engagement date and time is within the past 30 days, and keyword equals RunClubContest.

### Data Graphs

To further support sophisticated segmentation and real-time experiences, Data 360 uses data graphs, which are a flexible way to model relationships between datasets. These graphs are optimized for fast access to interconnected data and streamline how organizations query and analyze complex interrelationships within large datasets.

By organizing data like customer details and past purchase history in a structured format, data graphs enable systems to pull information for real-time personalized product recommendations, such as during a WhatsApp campaign. This intelligent linking ensures that data required for precise segmentation and personalized outreach is readily available. Choose between standard data graphs, which are scheduled updates, or real-time data graphs, which are instant, millisecond updates that are essential for powering real-time insights, managed through a data graph editor page.

## What’s Next

In this unit, you learned how querying data in Data 360 forms the foundation for uncovering insights, creating targeted segments, and modeling complex relationships with data graphs. You explored how queries can filter and combine harmonized datasets, how insights transform raw data into actionable metrics, how segmentation enables personalized engagement, and how data graphs organize relationships for real-time personalization.

To continue building your skills, explore the [Data 360 Insights](https://trailhead.salesforce.com/content/learn/modules/customer-data-platform-insights?trail_id=enhance-data-in-customer-data-platform) module on Trailhead. This module covers how to create calculated and real-time insights, helping you better understand and apply data within Data 360 for more informed decision-making.

## Resources

*   [_Salesforce Help_: Query Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_query_data_in_dc.htm&type=5)
*   [_Developer Guide_: Query Data in Data 360](https://developer.salesforce.com/docs/data/data-cloud-query-guide/guide/query-guide-get-started.html)
*   [_Salesforce Developers Blog_: Boost Data Cloud Integrations with the New Query Connect API](https://developer.salesforce.com/blogs/2025/08/boost-data-cloud-integrations-with-the-new-query-connect-api)
*   [_Developer Guide_: Best Practices](https://developer.salesforce.com/docs/data/data-cloud-query-guide/references/data-cloud-query-api-reference/c360a-api-queryservices-overview.html#best-practices)
*   [_Salesforce Blogger_: Data Cloud Segmentation Best Practices](https://www.salesforceblogger.com/2023/11/15/data-cloud-segmentation-best-practices/)
*   [_Salesforce Help_: Segmentation Filter Examples](https://help.salesforce.com/s/articleView?id=data.c360_a_segments.htm&type=5)

¡Aquí están las respuestas de la prueba!

---

**Pregunta 1 — Why are queries important in Data 360?**

**Respuesta: B — They allow you to filter, join, and explore data, and provide the foundation for insights and segments.**

El documento explica que las queries son la base para crear insights, definir segmentos de audiencia y potenciar la personalización en tiempo real, al permitir filtrar, unir y explorar datos unificados en los DMOs y DLOs.

---

**Pregunta 2 — What is the primary goal of segmentation in Data 360?**

**Respuesta: C — To define precise audiences for campaigns for personalized engagement across channels.**

El documento indica que el objetivo principal de la segmentación es crear grupos de audiencia precisos para diversas campañas, habilitando experiencias personalizadas y mejor engagement en todos los canales.