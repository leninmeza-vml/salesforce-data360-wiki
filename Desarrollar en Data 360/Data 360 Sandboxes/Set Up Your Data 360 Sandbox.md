# Set Up Your Data 360 Sandbox

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain the role of a Data 360 sandbox in the Data 360 ecosystem.  
    
*   Identify the different types of sandboxes available for development and testing.  
    
*   Provision a Data 360 sandbox instance from a production environment.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you might see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Before You Start

Before you start this badge, consider completing this recommended badge. The work you do here builds on the sandbox concepts that you learn in that badge.

*   [Salesforce Sandboxes: Quick Look](https://trailhead.salesforce.com/content/learn/modules/salesforce-sandboxes-quick-look)  
    

## The Architecture of Innovation

Testing Data 360 configurations in a live environment is risky, especially when you manage millions of customer data points. A single misconfigured identity resolution rule or data stream error can disrupt the experience for your real customers.

This is true for Cloud Kicks, a custom sneaker retailer. Jamal Cooks, systems architect, set up Data 360 for Cloud Kicks. His marketing team has seen incredible success now that it’s so easy to manage millions of customer data points and unify profiles.

![Head shot of Jamal Cooks.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-360-sandboxes/set-up-your-data-360-sandbox/images/91a914de6413c49a20aec75338659170_kix.f3b7iuqk8r3y.png)

Recently, Cloud Kicks launched a hyper-personalized loyalty program that merges in-store purchase history with real-time web browsing behavior to send instant style recommendations. To handle this massive data integration, Jamal is putting in some extra hours alongside DevOps developer Vijay Lahiri.

He’s especially concerned about protecting production data integrity. Specifically, he’s wondering about testing so many new configurations, like identity resolution rules and calculated insights, directly in a live environment, where a single error can disrupt the real customer experience. Time to take it up a notch and get some advanced skills to make sure that the new program is built and tested as safely and efficiently as possible.

![Head shot of Vijay Lahiri.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-360-sandboxes/set-up-your-data-360-sandbox/images/16cc082bc8f2b1948033565920d42e3c_kix.jsxhfg1t74u7.png)

In this badge, we do our best to answer Jamal and Vijay’s questions about navigating the Data 360 sandbox lifecycle. Let’s get started!

## What Is a Data 360 Sandbox?

A Data 360 sandbox is a copy of your production Data 360 metadata. While standard Salesforce sandboxes are used to test core Salesforce platform features, Data 360 sandboxes are specifically designed to let you test data ingestion, modeling, and identity resolution without affecting live customer profiles. Using a Data 360 sandbox impacts your production org credits. To learn more, see [Billing Considerations for Data 360 Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_billing_considerations.htm&type=5) .

If you aren’t familiar with metadata, think of it as a description of your data. For example, the configuration for a calculated insight is metadata, and it is copied to the Data 360 sandbox. However, the output data from the calculated insight that exists in production isn’t copied. A Data 360 sandbox replicates data streams, data model objects, calculated insights, and segments, but they don’t contain any data.

Jamal uses Data 360 sandboxes to isolate customization and development work, test data mapping and transformation logic, provide a training environment, and batch individual changes into one deployment to production.

## Choose Your Data 360 Sandbox Type

Data 360 is supported in all standard Salesforce sandbox types. While these sandbox types differ from a core Salesforce perspective—such as varying data storage limits—Data 360 sandboxes behave exactly the same once it is provisioned, regardless of the core sandbox you choose.

Jamal evaluates the options based on Cloud Kicks’s architectural needs.

*   **Developer and Developer Pro** : Perfect for initial Data 360 setup and basic testing. These sandboxes have limited storage but are ideal for proof-of-concepts.  
    
*   **Partial Copy** : Useful for testing with a sample of the production data model.  
    
*   **Full Sandbox** : This is a mirror of the production environment. It is essential for performance testing and full-scale user acceptance testing (UAT).  
    

For his initial proof-of-concept on the new loyalty program, Jamal decides that a Developer sandbox is the perfect fit.

## Design Your Data 360 Sandbox Strategy

Before you even click **New Sandbox** , you need a plan. Advanced architects like Jamal don’t just spin up environments; they design a comprehensive Data 360 lifecycle strategy. When planning your sandbox strategy, consider these key factors.

*   **Baseline production metrics:** Record current performance in your live environment so you have a clear point of comparison before testing begins.  
    
*   **Determine data volume requirements:** Ensure the sandbox tier you choose can handle the data sample size you need for an accurate test.  
    
*   **Assess identity resolution testing needs:** Plan your timeline around the fact that unified profiles are not copied over and must be built from scratch.  
    
*   **Plan for connector validation:** Document which external connections you need to securely reauthenticate in the isolated environment.  
    
*   **Establish performance benchmarking:** Define exactly what a successful test looks like for your new configurations before promoting them to production.  
    

By mapping these out ahead of time, Jamal guarantees that his new Developer sandbox is perfectly sized for his loyalty program proof-of-concept.

## Create a Data 360 Sandbox

Now that his strategy is set, Jamal begins the creating process in the Cloud Kicks production org. Before you create a sandbox, make sure Data 360 is provisioned in your production org, and review [](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_consideration.htm&type=5)[Considerations for a Sandbox in Data 360](https://help.salesforce.com/s/articleView?language=en_US&id=data.c360_a_data_cloud_sandbox_consideration.htm&type=5) in Salesforce Help.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

In this badge, we assume you’re a developer with the proper permissions to take these actions. Don't try to follow these steps in your Trailhead Playground. Sandboxes aren’t available in the Trailhead Playground.

1.  In Production **Setup** , enter `Sandboxes Copiar` in the Quick Find box.  
    
2.  Select **New Sandbox** , enter the details, and choose your preferred tier.  
    
3.  Click **Create** .  
    

## Enable Data 360 in a Sandbox

After the sandbox is created, Jamal must initialize the infrastructure and enable Data 360.

1.  Log in to the new sandbox, go to **Setup** , and select **Data Cloud Setup** .  
    
2.  Click **Get Started** .  
    
3.  Configure your basic settings, such as Data Cloud permission sets, time zone, naming conventions for data streams, and data retention policies.  
    

This enablement process typically takes 15 to 30 minutes, depending on your sandbox size. After that, wait another 30 to 60 minutes for the basic settings to pour in from the production org.

## Secure the Connection Links

Many enterprise organizations use Data Cloud One (DC1) to extend Data 360 capabilities across multiple core orgs. If your company uses this architecture, you must secure those connection links in the sandbox.

Once the Data 360 sandbox is ready, Jamal connects the Cloud Kicks DC1 org to the sandbox org. Because the sandbox is a copy of production, it often needs clear direction on whether it should talk to the real production org or a sandbox version of it. Here is how Jamal secures the links.

1.  In Data Cloud Setup, in the Quick Find box, search for and select **Data Cloud One** .  
    
2.  Verify that your sandbox org is connected as your Companion Org.  
    
3.  Reauthenticate CRM connectors and any external storage connectors such as Amazon S3 or Microsoft Azure.  
    
4.  Use the metadata clean up process to remove any orphaned data streams or stale data mappings inherited from production that you don't need in your sandbox environment.  
    

## Ingest and Test Data

To test the new hyper-personalized loyalty program, Jamal must now validate the sandbox connectivity and recreate the customer profiles. He does this by ingesting a simple data source and running the identity resolution rules. Follow these steps to ingest and test your data.

1.  Create a local data space.  
    
2.  Ingest your data streams, starting with a simple data source to validate connectivity.  
    
3.  After data is ingested, go to the **Identity Resolution** tab and click **Run** for your rulesets. Because unified profiles aren’t copied from production, they must be built from scratch in the Data 360 sandbox.  
    

## What’s Next

You’ve successfully provisioned a Data 360 sandbox, secured your connection links, and validated data ingestion. In the next unit, you learn how Jamal and Vijay refresh and synchronize these sandboxes to prevent metadata drift.

## Resources

*   [_Salesforce Help_ : Data 360 in a Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox.htm&type=5)
*   [_Salesforce Help_ : Considerations for Data Cloud One in a Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_one_sandboxes.htm&language=en_US&type=5)
*   [_Salesforce Help_ : Considerations for Sandbox in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_consideration.htm&type=5)
*   [_Salesforce Help_ : Create a Data 360 Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_create.htm&type=5)
*   [_Trailhead_ : Salesforce Sandboxes: Quick Look](https://trailhead.salesforce.com/content/learn/modules/salesforce-sandboxes-quick-look/develop-and-test-features-using-salesforce-sandboxes)

## Preguntas

**Pregunta 1:** ¿Por qué Jamal usa un sandbox de Data 360 en lugar de probar directamente en el org de producción de Cloud Kicks?

✅ **B — To build and test configurations safely without impacting live production data**

El documento lo confirma: Jamal está especialmente preocupado por *"protecting production data integrity"* y usar el sandbox le permite probar configuraciones como reglas de identity resolution y calculated insights sin afectar la experiencia real del cliente.

---

**Pregunta 2:** ¿Dónde comienza el proceso inicial de creación de un sandbox de Data 360?

✅ **A — In the production environment's Setup menu**

El documento lo indica claramente en los pasos: *"In Production Setup, enter Sandboxes in the Quick Find box. Select New Sandbox..."* El proceso siempre inicia desde el menú de configuración del org de **producción**.