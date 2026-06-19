# Refresh and Synchronize Your Data 360 Sandbox

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the process of synchronizing metadata between Data 360 production and sandbox environments.  
    
*   Configure secure data connections within a refreshed Data 360 sandbox.  
    
*   Implement a cleanup process to remove outdated metadata.  
    

## Synchronize Your Data 360 Metadata Between Orgs

In the previous unit, lead architect Jamal Cooks successfully provisioned a Data 360 Developer sandbox and ingested data to validate connectivity. Now that the environment is set up, he must keep it in sync with the production org. Metadata drifts quickly; failing to synchronize can result in misaligned identity rules, orphaned streams, and unexpected behavior. In this unit, you explore sandbox refresh strategies and advanced metadata synchronization.

## Avoid Metadata Drift

Metadata changes constantly. If your sandbox lags behind production, any testing risks being invalid. Because a refresh only copies metadata (the configuration) and not the actual data, a six-month-old sandbox is simply a snapshot of the past. Testing in this state leads to flawed results that fail in production.

Consider this scenario at Cloud Kicks: In the production org, Jamal updates an identity resolution ruleset (Rule Set 2.0). The change adds a new, stricter matching criterion to ensure high-quality unified profiles.

Six months later, DevOps Developer Vijay Lahiri is working in the Developer sandbox, which hasn't been refreshed since before Jamal's change. Vijay builds a complex segment that targets high-value customers based on the existing unified profiles. He successfully tests the segment—it returns 10,000 unified profiles—and assumes his work is ready to deploy.

The metadata drift occurs because Vijay’s sandbox contains Rule Set 1.0 metadata, which is less restrictive than the Rule Set 2.0 now live in production. When Vijay deploys his new segment to production, the segment immediately fails. Why?

*   **Dependency failure:** The segment's logic relies on the older, looser identity resolution results from Rule Set 1.0.  
    
*   **Unexpected behavior:** When the segment runs against the live production environment using the correct, newer Rule Set 2.0, it only finds 8,500 unified profiles that meet the stricter criteria. The segment suddenly excludes 1,500 target customers, breaking the hyper-personalized loyalty program's launch.  
    

The only way to avoid this kind of production failure is to ensure that the sandbox configuration you build on is a mirror of the latest production metadata. This makes a timely sandbox refresh and a post-refresh checklist critical parts of the architect's workflow.

## Prepare for a CRM Sandbox Refresh

Before initiating a refresh, Vijay maps out the environment dependencies. Because Cloud Kicks pulls its customer loyalty data from a Salesforce CRM sandbox, he must take specific actions before refreshing that CRM sandbox.

When a CRM sandbox is refreshed, its OrgId changes and its authentication permission sets are deleted. This permanently breaks the connection to Data 360. If you don't prepare, all data streams that use the CRM sandbox as a source go into an error state, and the system prevents you from simply disconnecting the org.

Follow these steps to safely prepare for a CRM sandbox refresh.

1.  Back up your CRM data stream configurations by creating a DevOps data kit.  
    
2.  Delete any data streams that use the CRM sandbox org as their source. You might also need to delete downstream dependencies, such as data mappings or segment attributes, to delete the data streams.  
    
3.  Go to **Data Cloud Setup** , select **Salesforce CRM Connector** , and disconnect the CRM sandbox org.  
    
4.  Refresh the CRM sandbox org.  
    

## Refresh Your Sandbox

With the preparations complete, Vijay is ready to refresh the Cloud Kicks Data 360 sandbox. A sandbox refresh updates the sandbox’s metadata from its source org, but not the data.

*   **Metadata sync:** A sandbox refresh copies all Data 360 configurations, including data streams, calculated insights, and segments.  
    
*   **Implications:** A refresh overwrites any existing work in the sandbox.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**Warning** :  
Always back up your sandbox metadata using a DevOps data kit before refreshing.

Follow these steps to refresh your Data 360 sandbox.

1.  Go to **S** **etup** and enter `Sandboxes Copiar` in the Quick Find box.  
    
2.  Click the **Refresh** link next to the sandbox name.  
    
3.  Review and edit the name and description.  
    
4.  Choose the sandbox license type (Developer, Developer Pro, Partial Copy, or Full).  
    
5.  Click **Create** .  
    

## Complete the Post-Refresh Checklist

Refreshing a sandbox is just the first step. Vijay must now reestablish the “plumbing” to get Cloud Kicks’s data flowing again. Follow this post-refresh checklist to restore your environment.

*   **Reestablish CRM connections:** If you refreshed a connected CRM sandbox, you must recreate the external org user permission set, reconnect the CRM sandbox org to Data 360, and recreate your object and field permissions. Finally, install your data kit to redeploy your data streams.  
    
*   **Reauthenticate connectors:** For security, connections to external systems like Marketing Cloud Engagement must be reauthorized in the sandbox.  
    
*   **Initialize identity resolution:** The refresh copies identity rules, but you must manually trigger the first run to generate unified profiles in the sandbox.  
    
*   **Manage Data Cloud One (DC1) connections:** If your enterprise uses DC1, pay close attention to your environments during a refresh. When you refresh a sandbox that acts as a DC1 companion org, the connection to the primary Data 360 org breaks. After the refresh completes, you must re-establish the DC1 connection to ensure metadata and data can sync properly across your orgs.  
    
*   **Clean up outdated metadata:** Use the **Data Cloud Setup** menu to identify and delete orphaned data streams or mapping errors that occurred during the sync.  
    

## What’s Next

You just learned how Jamal and Vijay avoid metadata drift by keeping their sandboxes synchronized and handling post-refresh connections. Next, you learn how to bundle these Data 360 configurations into DevOps data kits for safe deployment.

## Resources

*   [_Salesforce Help_ : Considerations for Sandbox in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_consideration.htm&type=5)
*   [_Salesforce Help_ : Create a Data 360 Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_create.htm&type=5)

## Preguntas

**Pregunta 1:** ¿Cuál es el resultado principal de actualizar (refresh) un sandbox de Data 360?

✅ **B — The sandbox metadata is updated to match the current state of the production org.**

El documento lo confirma: *"A sandbox refresh updates the sandbox's metadata from its source org"* y *"copies all Data 360 configurations, including data streams, calculated insights, and segments."* Es importante notar que solo se copia metadata, no los datos.

---

**Pregunta 2:** ¿Qué herramienta debe usar Vijay para eliminar metadata huérfana que ya no se necesita después de un refresh?

✅ **B — The Data 360 Setup cleanup process.**

El documento lo indica explícitamente en el post-refresh checklist: *"Clean up outdated metadata: Use the Data Cloud Setup menu to identify and delete orphaned data streams or mapping errors that occurred during the sync."*