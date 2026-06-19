# Deploy, Run, Monitor, and Migrate Code Extension

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe why you deploy and invoke code extension and how it connects to batch data transforms.  
    
*   Explain how to run your code extension in Data 360.  
    
*   Identify how to monitor code executions (Run History and execution logs).  
    
*   Describe how you migrate Code Extension from sandbox to production using a DevOps Data Kit.  
    

## Deploy and Invoke Code Extension

Once your script is validated locally, deploy it to Data 360. Deployment uploads your script, its dependencies, and configuration to a sandbox so your code is available in Data 360.

## Choose the Right Compute for Deployment

When you deploy custom code, you choose a compute size that defines how much CPU and memory Data 360 allocates when your script runs. The choice affects both performance and cost.

Larger sizes provide more vCPUs and memory, so your transform can handle bigger datasets, more complex logic, or heavier dependencies (for example, large pandas operations or many libraries). With each size increase, the number of CPU cores and memory doubles. Larger compute sizes consume more credits per hour of execution.

To choose the right compute size for your deployment, start with the smallest size that fits your expected data volume and script complexity. Use local runs and sandbox runs to gauge memory and CPU needs. If you see timeouts, out-of-memory errors, or slow runs, move to the next size. For production, factor in peak data volume and growth so you don’t under-provision. If cost is a concern, optimize the script first (for example, incremental processing or filtering early) before moving to a larger size.

## Run Code Extension

Run your code extension by running the batch data transform that uses your deployed code extension in Data 360. You can run it immediately by clicking Run Now on the Data Transforms tab, or run it automatically by creating a schedule for the batch transform. For each run, Data 360 executes your code, reads from and writes to the transform’s DLOs or DMOs, and records run history details such as status, rows read and written, and duration.

## Monitor Code Executions

After your code runs as part of a batch data transform, you monitor it so you can confirm it succeeded, see how much data it processed, and troubleshoot if something failed. Data 360 gives you two ways to do that: Run History in the Code Extension UI, and execution logs.

Run History lives on each custom code deployment. It lists each execution with when it ran, what started it (for example, the batch data transform), the run status (Running, Success, or Failure), and how many rows were read and written. You open a run to see details such as runtime and completion time. That way you can spot failures, check volume, and see which feature used the code.

Execution logs from your custom code are stored in the data lake object DataCustomCodeLogs\_\_dll. You query them in Query Editor or view them in Data Explorer when you need to dig into a specific run or audit behavior. Logs usually appear within a few minutes after execution. You can filter by transform name, execution ID, or message content to troubleshoot or verify what your code did.

## Migrate Code Extension from Sandbox to Production Using a DevOps Data Kit

You create a DevOps data kit in the sandbox and add the components you want to promote: your validated batch data transform and, if needed, the custom code deployment. When you add a batch data transform, the kit automatically includes the custom code it uses. You also add any DLOs or DMOs that the code reads from or writes to and that do not yet exist in production.

The kit uses a set order for deployment—data objects first, then custom code, then batch transforms—so dependencies land in the right sequence. You publish the kit, add it to a package, and deploy that package to the production org.

## Wrap It Up

Code Extension lets you run custom Python logic in Data 360 for complex data transformations. Understanding when and where to use it helps you extend native capabilities and turn raw data into structured data for segments and action.

## Resources

*   [_Salesforce Help_ : Deploy a Custom Script to Data 360 Sandbox](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/deploy-custom-script.html)
*   [_Salesforce Help_ : Run Custom Code by Running a Batch Data Transform](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/invoke.html)
*   [_Salesforce Help_ : Monitor Custom Script Deployments and Execution](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/view-deployment-details.html)

## Preguntas

**Pregunta 1:** ¿Cómo se invoca una Code Extension implementada usando la interfaz de Data 360?

✅ **B — By creating a Batch Data Transform and selecting your deployed code extension**

El documento lo confirma: *"Run your code extension by running the batch data transform that uses your deployed code extension in Data 360. You can run it immediately by clicking Run Now on the Data Transforms tab."*

---

**Pregunta 2:** Cuando agregas un Batch Data Transform a un DevOps Data Kit, ¿qué sucede con el código personalizado que usa?

✅ **B — The custom code it references is included in the kit automatically.**

El documento lo indica explícitamente: *"When you add a batch data transform, the kit automatically includes the custom code it uses."* No es necesario agregarlo manualmente por separado.