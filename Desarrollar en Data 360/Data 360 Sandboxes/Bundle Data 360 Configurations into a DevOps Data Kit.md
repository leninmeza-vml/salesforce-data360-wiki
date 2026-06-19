# Bundle Data 360 Configurations into a DevOps Data Kit

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain the purpose of a data kit in the DevOps lifecycle.  
    
*   Create a DevOps data kit to bundle Data 360 components.  
    
*   Identify supported components and dependencies.  
    

## Manage Deployments Efficiently

In this unit, you learn how to package Data 360 metadata using DevOps data kits, compare data kit types, and manage the dependency hierarchy for a smooth deployment. Follow along as DevOps Developer Vijay Lahiri and Systems Architect Jamal Cooks use data kits to safely move Cloud Kicks’s new loyalty program configurations from their Developer sandbox toward production.

With the Cloud Kicks sandbox successfully synchronized, Vijay must find an efficient way to move the new loyalty program configurations to production. Instead of manually re-creating 50 different data mappings, he relies on DevOps data kits. DevOps data kits let you bundle Data 360 components into a single unit for repeatable, auditable, and safe promotion across environments.

## Package Configurations Once, Deploy Anywhere

Data kits are the containers for your Data 360 configurations. For Vijay, avoiding dependency errors during deployment is the primary goal.

For enterprise teams, data kits are not just a transport mechanism; they act as release artifacts. They bundle related configurations, ensure dependency order is respected, and create audit trails for deployments. As a best practice, Vijay follows these guidelines while creating data kits.

*   Include release naming conventions (for example, `v1.2-loyalty-enhancement Copiar` ).  
    
*   Review the publishing sequence order of the data kit components.  
    
*   If you create a new data space in the sandbox org, ensure the data space name exists in the target org.  
    
*   Tag releases tied to production deployment dates.  
    

## Compare Standard and DevOps Data Kits

Before bundling the loyalty program configurations, Vijay must choose the correct data kit type for his architecture.

| **Data Kit Type** | **Purpose** | **Audience** |
| --- | --- | --- |
| **Standard** | AgentExchange solution packages | Salesforce Partners |
| **DevOps** | Internal environment migration | Enterprise architects and DevOps |

The distinction between data kit types is crucial. A standard data kit is explicitly designed for packaging solutions to be installed by external partners, such as a Salesforce partner listing an application on the AgentExchange. This process focuses on solution delivery.

Conversely, the DevOps data kit is your enterprise-grade tool for internal metadata management. Its purpose is to facilitate the controlled, repeatable promotion of configuration changes—like new identity rules or calculated insights—between your own organizational environments (for example, from a Developer sandbox to a UAT sandbox, and finally to production). By choosing the DevOps data kit, you signal that the bundled components are part of a structured, audited deployment pipeline, not an external solution.

## Bundle Your Configurations

To safely move the new loyalty program metadata, Vijay creates a DevOps data kit. When working in a Data 360 sandbox, you can bundle several core metadata components into your data kit. The [supported components](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox.htm&type=5) include:

*   **Data streams:** The schema and source details for your ingested data.  
    
*   **Data model objects (DMOs):** The standard and custom data models you map your streams to.  
    
*   **Calculated insights:** The SQL-based logic used for tasks like loyalty scoring.  
    
*   **Identity resolution rules:** The matching and reconciliation logic for Jamal's unified profiles.  
    
*   **Segments:** The audience criteria defined for your targeted marketing efforts.  
    

Vijay follows these steps to bundle the configurations.

1.  In your sandbox org, go to **Setup** , and select **Data Cloud Setup** .  
    
2.  Under Developer Tools, select **Data Kits** .  
    
3.  Click **New** , and select **DevOps Data Kit** .  
    

![New Data Kit creation modal in Salesforce Setup.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-360-sandboxes/bundle-data-360-configurations-into-a-devops-data-kit/images/415236fa7ba5ad4c2aa4c47c664bbbb6_kix.hdccqoh05lkz.png)

4.  Select a data space.  
    
5.  Enter the data kit name.  
    
6.  Click **Save** .  
    

## Manage the Dependency Hierarchy

The dependency hierarchy is critical for deployment success. When Vijay builds his data kits, he manages the dependency hierarchy by following a strict order.

1.  From the **Data Kit** page, select your data kit and add your supported components.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Data 360 automatically includes dependencies (like data mappings) when you add a data stream. To verify exactly which components can be put into a data kit, review the [Data 360 Extensibility Readiness Matrix](https://developer.salesforce.com/docs/atlas.en-us.c360a_api.meta/c360a_api/c360a_api_isv_readiness_data.htm) in Salesforce Help.

2.  **Lay the foundation with streams:** Add your Amazon S3 or CRM data streams first. By selecting the data stream, Data 360 intelligently pulls in the associated data lake objects (DLOs).  
    
3.  **Connect the pipes with mappings:** When you add your data model objects (DMOs), always select the **Include Mappings** checkbox. This ensures that your raw ingested data knows exactly which part of the unified data model it belongs to the moment it lands in the target org.  
    
4.  **Audit the publishing sequence:** In the Data Kit page, audit the publishing sequence to prevent missing dependency errors. If a segment depends on a calculated insight, ensure the calculated insight is set to deploy _before_ the segment.  
    
5.  Once your components and dependencies are confirmed, click **Save** .  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**Tip:**  
Use semantic versioning for each data kit (for example, v1.3-loyalty-update) and store exported manifests in source control.

## What’s Next

You’ve successfully bundled your Data 360 configurations into a portable DevOps data kit. In the next unit, you learn how Jamal and Vijay choose the right multi-tool deployment strategy to move these kits into their target environments.

## Resources

*   [_Salesforce Developers_ : Package Data 360 Metadata Components](https://developer.salesforce.com/docs/atlas.en-us.pkg2_dev.meta/pkg2_dev/dev2gp_package_data_cloud.htm)
*   [_Salesforce Help_ : Create a Data 360 Sandbox](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_sandbox_create.htm&language=en_US&type=5)

## Preguntas

**Pregunta 1:** ¿Cuál es la función principal de un DevOps data kit en el ciclo de vida de implementación de Data 360?

✅ **B — To bundle multiple Data 360 configurations into a single, transportable release artifact**

El documento lo confirma: *"DevOps data kits let you bundle Data 360 components into a single unit for repeatable, auditable, and safe promotion across environments."*

---

**Pregunta 2:** ¿Cuáles son tres componentes principales de Data 360 que se pueden incluir en un DevOps data kit?

✅ **D — Data streams, calculated insights, and identity resolution rules**

El documento lista los componentes soportados explícitamente: data streams, DMOs, **calculated insights**, **identity resolution rules** y segments. La opción D contiene tres componentes que están claramente en esa lista. Las demás opciones incluyen elementos como *unified profiles*, *production user credentials* o *data spaces* que no están listados como componentes empaquetables.