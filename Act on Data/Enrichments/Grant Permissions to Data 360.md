# Grant Permissions to Data 360

## Learning Objectives

After completing this unit, you’ll be able to:

*   Provide the Data Cloud Architect access to the default Data Space.  
    
*   Assign the Data Cloud Architect permission set to yourself.  
    

Your Sales org and Data 360 are hosted in different physical infrastructures, but Salesforce ensures secure communication between the two products by strictly enforcing permissions-based access to data. To enable these permissions, you must first grant the Data Cloud Architect access to the default data space where you’ve ingested data. Then, you must grant yourself the Data Cloud Architect permission set.

## Assign the Data Cloud Architect Access to the Default Data Space

In your Sales org, let’s grant the Data Cloud Architect access to the default data space so they can view your calculated insight data. Remember, your calculated insight uses data from the default data space.

1.  In your Sales org, in **Setup**, search for and select **Permission Sets**.  
    
2.  Select the **Data Cloud Architect** permission set.  
    
3.  In **Apps**, select **Data Cloud Space Managemen**t.  
    
4.  In **Data Spaces**, click **Edit**, enable the default data space, and click **Save**.  
    

The Data Cloud Architect user can access the default data space in Data 360, where your calculated insight queries data from.

## Assign Data Cloud Architect Permission Set to Yourself

To create a copy field enrichment, you must have the Data Cloud Architect permission set.

1.  In your Sales org, in **Setup**, search for and select **Permission Sets**.  
    
2.  Select the **Data Cloud Architect** permission set.  
    
3.  Click **Manage Assignments**.  
    
4.  Click **Add Assignment**.  
    
5.  Select the user who'll create the copy field enrichment and click **Next**.  
    
6.  Click **Assign**.  
    

You've assigned yourself to the Data Cloud Architect permission set. You can now create a copy field enrichment.

## Summary

In your Sales org, you've granted yourself permission to create a copy field enrichment that uses data from Data 360's default data space. In the next unit, we cover how to create and verify a copy field enrichment.

## Resources

*   [_Salesforce Help_: Manage Access with Data 360 Permission Sets](https://help.salesforce.com/s/articleView?id=data.c360_a_setup_permission_sets.htm&type=5)

¡Aquí están las respuestas de la prueba!

---

**Pregunta 1 — Which data space does the Data Cloud Architect need permissions to access when the calculated insight queries data in the North America dataspace?**

**Respuesta: B — North America data space.**

La lógica es directa: el Data Cloud Architect necesita permisos para acceder al data space específico donde el calculated insight consulta sus datos. Si el insight usa el data space **North America**, entonces se necesitan permisos para ese data space. En el ejemplo del módulo se usa el **default** data space porque el insight fue creado ahí.

---

**Pregunta 2 — Which permission set do you need to create a copy field enrichment in your Sales Cloud org?**

**Respuesta: D — Data Cloud Architect.**

El documento indica explícitamente que para crear un copy field enrichment, el usuario debe tener asignado el permission set **Data Cloud Architect**, que también es el que se configura para acceder a los data spaces en Data 360.
