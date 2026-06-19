# Author and Validate Code Extension Locally

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the importance of Salesforce CLI (command line interface) setup.  
    
*   Identify the main script location and how local validation works.  
    
*   Describe best practices for writing a Python transform script locally.  
    

## Importance of Salesforce CLI Setup

You can develop and test Code Extension scripts on your machine, then deploy them to Data 360. To do that, you need a local environment that can talk to your sandbox org. Your machine must run macOS, Linux, or Windows, and have Python 3.11 and OpenJDK 17.

Salesforce CLI with the Code Extension plugin and the Data Custom Code Python SDK work together as your local toolchain for Code Extension. This toolchain provides:

*   **CLI** to configure the connection to the sandbox, initialize a project, run the script locally, update config from your script, and deploy.  
    
*   **Libraries** that your script uses at runtime so the same code runs locally and in Data 360.  
    
*   **Workflows** such as a standard project layout (payload/, entrypoint.py, config.json), connection to sandbox for local runs, and packaging so what you run locally is what gets deployed. These workflows let your local runs read from Data 360 and validate behavior before you deploy.  
    

Use the CLI to initialize a script package, which creates the expected layout (including a payload/folder and entrypoint.py) so your script and config are in the right place for local runs and for packaging when you deploy.

## The Authoring Environment

Code Extension supports a standard Python virtual environment for authoring and testing scripts. Use this environment for quick prototyping and simple development. You create and activate a virtual environment, build your logic, and save the final code in payload/entrypoint.py for deployment.

## Write and Validate Your Transform Logic Locally

Use your preferred IDE, such as Visual Studio Code or Jupyter Notebook, to write and change your transform logic. Your main script lives in payload/entrypoint.py. Local development lets you iterate quickly and catch issues before you deploy. When you write scripts, use the exact API names for Data 360 object fields—they usually follow the FieldName\_\_c pattern.

Your sandbox must contain the data lake objects (DLOs) or data model objects (DMOs) that your script reads from or writes to.

Here are some best practices to follow while writing custom logic.

*   A script must use one object type for both read and write operations: Either DLO to DLO, or DMO to DMO. This keeps the data model consistent and matches how Data 360 runs the job.  
    
*   List any extra dependencies in requirements.txt so they’re installed and packaged correctly.  
    

When you run your script locally, it runs on your machine, reads data from your Data 360 sandbox, applies your transform logic, and shows the result in your local terminal. That way you can confirm the transformation before deploying it to Data 360.

## Supported Write Modes

Code Extension supports different ways of writing results to the target object.

*   **Append:** Adds new records to the target object without affecting existing data.  
    
*   **Overwrite:** Replaces all existing data in the target object with new data.  
    
*   **Merge:** Updates existing records and adds new records based on key fields.  
    

Next, deploy and run your script.

## Resources

*   [_Salesforce Help_ : Write and Validate Custom Scripts](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/author-custom-script.html)
*   [_Salesforce Help_ : Use Custom Scripts in Data 360](https://developer.salesforce.com/docs/data/data-cloud-code-ext/guide/use-custom-script.html)

## Preguntas

**Pregunta 1:** ¿Por qué se recomienda la validación local antes de implementar código en un sandbox?

✅ **B — It allows you to catch issues early and refine logic for production readiness.**

El documento lo confirma: *"Local development lets you iterate quickly and catch issues before you deploy."* Además, cuando ejecutas el script localmente, puedes *"confirm the transformation before deploying it to Data 360."*

---

**Pregunta 2:** En un paquete de Code Extension, ¿qué define el archivo de script principal que se ejecuta para una transformación de datos por lotes?

✅ **C — The entrypoint value in config.json**

El documento lo indica al describir el diseño estándar del proyecto: *"payload/, entrypoint.py, config.json"*, y menciona que el CLI inicializa un paquete de script que crea el layout esperado *"including a payload/folder and entrypoint.py"*. El archivo principal del script es `payload/entrypoint.py`, referenciado por el valor `entrypoint` en `config.json`.
