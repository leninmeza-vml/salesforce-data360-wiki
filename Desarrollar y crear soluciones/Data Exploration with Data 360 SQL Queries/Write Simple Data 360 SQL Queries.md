# Write Simple Data 360 SQL Queries

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the structure of a basic Data 360 SQL query.  
    
*   Select specific fields from data model objects (DMOs) and data lake objects (DLOs).  
    
*   Explain the role of the key qualifier (KQ\_Id\_\_c) in Data 360 records.  
    
*   Apply basic comments to your SQL code for improved readability.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you might see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Sign Up for a Custom Playground with Data 360

To complete this badge, you need a special, limited-time custom playground that contains Data 360 and our sample data.

1.  Click Create Playground.  
    
2.  Your new org is automatically attached to your Trailhead account!  
    
3.  Make note of your org’s expiration date and complete this badge before then.  
    

## Connect Your Data

Connections in Data 360 are started by setting up data streams, which are data sources either connected or ingested into Data 360. The data from those data sources are stored in data lake objects (DLOs), which are storage containers for data stream data. If data needs manipulation, formula fields can be created to normalize your data or to create basic calculations.

## Create a Data Stream

Data is ingested into Data 360 through data sources. Data sources can be other Salesforce orgs, Marketing Cloud Engagement business units, external platforms, and CSV files. For this badge, we’ve already connected a Sales Cloud and Service Cloud org to your Developer org. Now that these data source connections are already established, you can add data streams to Data 360. 

1.  Once you’re logged in, search for and select Data Cloud from the App Launcher.  
    

![App launcher icon with Data Cloud in the Apps.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-exploration-with-data-360-sql-queries/write-simple-data-360-sql-queries/images/5cbf6791d6380bc327474a5f4f4c1985_kix.70gk146iqgzs.png)

2.  In   Data Cloud, go to the   Data Streams tab and click **New** .  
    
3.  Click **Salesforce CRM**  under Connected Sources **,** and click **Next** .  
    
4.  Note the Salesforce Org is preselected. From View Bundles, choose the **Sales** data bundle and click **Next** .  
    

![New Data Stream screen with the Sales Data Bundle selected.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-exploration-with-data-360-sql-queries/write-simple-data-360-sql-queries/images/7627ffeb476708cf1b255261fc562501_kix.ze4jggemp6yc.jpg)

5.  View the associated fields and click **Next** . It can take a few minutes for the fields to appear.  
    
6.  Notice that the default Data Space is preselected and all the fields included in the bundle are listed. Leave the selections as is, and click **Deploy** .  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Deployment can take a few minutes. If you run into any issues, wait a few minutes and then retry the deployment again. 

Six new data streams are now created. Next, add some additional data streams to connect Service Cloud case data to Data 360.

## Add Data Streams

1.  From the Data Streams window, click **New** .  
    
2.  Select **Salesforce CRM** and click **Next** .  
    
3.  Select **View Objects** (1) and search for `Case Copiar` (2).  
    
4.  Select both **Case** and **Case History** and click **Next** .  
    

![New Data Stream window with Case and Case History selected.](https://res.cloudinary.com/hy4kyit2a/f_auto/fl_lossy/q_70/learn/modules/data-exploration-with-data-360-sql-queries/write-simple-data-360-sql-queries/images/f6dc4d841ee212986340f4b0054dd304_kix.rkib0vi54nz6.jpg)

5.  Under Objects starting with Case, keep the name the same (Case\_Home) and select **Engagement** from the Object Category dropdown.  
    
6.  Then select **Created Date** from the dropdown for Event Time Field.  
    
7.  Click **CaseHistory2** . Keep the same name (CaseHistory2\_Home), and select **Other** for the Object Category.  
    
8.  Click **Next** .  
    
9.  Check that the default data space is selected and click **Deploy** .  
    

## Create Your Query Workspace

Set up your environment for analysis.

1.  In Data Cloud go to the Query Editor tab and click **New** .  
    
2.  For the **Workspace Name** , enter `Customer Data Quality Copiar` .  
    
3.  Leave the **Data Space** as Default.  
    
4.  Click **Save** .  
    

By creating this workspace, your queries operate within the correct security and access protocols, and you can find the right objects for your analysis.

## Write Your First Query

Every journey into data begins with asking a question. In Data 360 SQL, you ask your question by writing a query. A basic query has two required clauses: SELECT and FROM.

*   The SELECT clause specifies which columns (fields) you want to retrieve.  
    
*   The FROM clause specifies the source of the data, which is always a data model object (DMO), data lake object (DLO), or calculated insight object (CIO).  
    

Let’s see this in action. You can retrieve every field from the DMO by using the asterisk (\*) wildcard in the SELECT clause to get a quick list of all individual records in Data 360.

SELECT \* FROM ssot\_\_Individual\_\_dlm

While SELECT \* is fast for writing a query, it’s rarely a best practice because it can return a very large amount of data and slow down your query.

## Select Specific Fields

A much more efficient approach is to list only the specific fields you need. This makes your query run faster and returns a result set that is focused on the data required for the analysis.

For an initial report, you only need the first name and ID.

SELECT ssot\_\_FirstName\_\_c, ssot\_\_Id\_\_c FROM ssot\_\_Individual\_\_dlm

## Understand the Key Qualifier Field

When working with Data 360 records, you'll frequently see a field called KQ\_Id\_\_c, or key qualifier ID. Understanding this field is critical for ensuring data accuracy when joining data later in this module.

The KQ\_Id\_\_c is an internal identifier that helps track the source and uniqueness of a record within the Data 360 system.

*   Every record in a DMO has a unique combination of its primary ID (like ssot\_\_Id\_\_c) and the KQ\_Id\_\_c.  
    
*   This identifier is often used in Data 360 to ensure that when you are combining data from multiple objects, you are correctly linking the specific version of a record you intend to use.  
    

It’s easiest to remember that the primary ID identifies the individual entity and the KQ\_Id\_\_c helps you identify the specific source record for that entity.

## Add Comments as a Best Practice

As your queries become more complex, especially when collaborating on a team, readability is critical. You can add comments to your SQL statements to explain logic, note assumptions, or temporarily disable parts of your code. Comments are ignored when the query executes.

You can use two types of comments:

*   Single-line comments: Use two hyphens (--) at the beginning of a line or to comment out the rest of a line.  
    
*   Multi-line comments: Enclose the text in /\* and \*/ for comments that span multiple lines.  
    

Create and execute the following query to practice what you learned in this unit.

## Write and Run Your Query

In the Customer Data Quality workspace, execute your SQL statement.

*   In the main editor window, paste this query to view individual records:  
    

/\* This query retrieves all essential individual records for Cara Ng's initial customer report. The field list is explicit for performance optimization. \*/ SELECT ssot\_\_FirstName\_\_c, ssot\_\_LastName\_\_c, ssot\_\_Id\_\_c, -- Individual ID is critical for matching with other systems KQ\_Id\_\_c FROM ssot\_\_Individual\_\_dlm LIMIT 10

*   Click **Run Query** in the top left of the editor.  
    
*   Review your results in the **Query Result** panel at the bottom of the screen.  
    

## Save Your Query

After confirming your results are correct, click the **Save** button in the top right corner of the workspace.

Now that you know the structure and best practices for simple queries, check that you set up your first workspace and query correctly by clicking the Check Challenge for 500 points.

## Resources

*   [_Data 360 Query Guide_ : Get Started with Data 360 SQL](https://developer.salesforce.com/docs/data/data-cloud-query-guide/guide/dc-query-section.html)
*   [_Data 360 Query Guide_ : Data 360 SQL Reference](https://developer.salesforce.com/docs/data/data-cloud-query-guide/references/dc-sql-reference/data-cloud-sql-context.html)
*   [_Data 360 Query Guide_ : SELECT](https://developer.salesforce.com/docs/data/data-cloud-query-guide/references/dc-sql-reference/select.html)

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Write Simple Data 360 SQL Queries

If you haven’t already, complete the steps in the unit above, then click Check Challenge to Earn 500 Points.

### Esta insignia requiere un nuevo Playground de Data 360 personalizado.

Tiene tiempo limitado para completar esta insignia y cualquier otra insignia que requiera un Playground Data 360. Si se queda sin tiempo, perderá el acceso a este Playground y tendrá que empezar desde el principio con la insignia.

Aquí tienes la guía paso a paso para completar el reto:

---

## Paso 1: Abrir Data Cloud desde el App Launcher

1. En tu org (la pantalla que ya tienes abierta), haz clic en el ícono de cuadrícula (**App Launcher**) en la esquina superior izquierda.
2. En el buscador escribe **Data Cloud** y selecciónalo.

---

## Paso 2: Crear el Data Stream (Sales Bundle)

1. Ve a la pestaña **Data Streams** y haz clic en **New**.
2. Selecciona **Salesforce CRM** → clic en **Next**.
3. En **View Bundles**, selecciona **Sales Data Bundle** → clic en **Next**.
4. Revisa los campos y haz clic en **Next** (espera unos segundos si no cargan).
5. Deja todo por defecto y haz clic en **Deploy**.
6. Espera a que el despliegue termine (puede tardar unos minutos).

---

## Paso 3: Agregar Data Streams de Service Cloud (Case)

1. En **Data Streams**, haz clic en **New**.
2. Selecciona **Salesforce CRM** → **Next**.
3. Selecciona **View Objects**, busca **Case**.
4. Selecciona **Case** y **Case History** → **Next**.
5. En **Case_Home**, selecciona categoría **Engagement** y en **Event Time Field** elige **Created Date**.
6. En **CaseHistory2_Home**, selecciona categoría **Other**.
7. Haz clic en **Next** → **Deploy**.

---

## Paso 4: Crear el Query Workspace

1. Ve a la pestaña **Query Editor** → clic en **New**.
2. En **Workspace Name** escribe exactamente: `Customer Data Quality`
3. Deja **Data Space** como **Default**.
4. Haz clic en **Save**.

---

## Paso 5: Escribir y ejecutar la Query

1. En el editor, pega exactamente este código:

```sql
/*
This query retrieves all essential individual
records for Cara Ng's initial customer report.
The field list is explicit for performance optimization.
*/
SELECT ssot__FirstName__c,
       ssot__LastName__c,
       ssot__Id__c, -- Individual ID is critical for matching with other systems
       KQ_Id__c
FROM ssot__Individual__dlm
LIMIT 10
```

2. Haz clic en **Run Query** (esquina superior izquierda del editor).
3. Verifica que aparezcan resultados en el panel inferior.

---

## Paso 6: Guardar la Query

1. Haz clic en **Save** (esquina superior derecha).

---

## Paso 7: Verificar el reto

1. Regresa a Trailhead.
2. Haz clic en **Check Challenge**.

---

> **Tip:** Si el deployment tarda o falla, espera 2-3 minutos y vuelve a intentarlo. Los data streams pueden tardar en procesarse.