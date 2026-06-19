# Create Calculated Fields and Metrics

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe what calculated fields are.  
    
*   Create a calculated dimension.  
    
*   Create a calculated measure.  
    

## Explore Calculated Fields

You can add calculated fields to your semantic model when you need additional fields that don’t exist in your data. Think of calculated fields as on-the-fly fields that can contain complicated logic and exist on top of your data. There are two types of calculated fields:

*   **Calculated dimensions:** Custom calculations to create new dimensions. Dimension fields are used to categorize or group your data, such as product category or car manufacturer.  
    
*   **Calculated measures:** Custom calculations that create new measures. Measures are fields that are aggregated and that you can do math with, such as test score or price.  
    

There are two ways to create calculated fields. You can either use Semantics AI to draft them for you or create them manually.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

If Einstein Generative AI isn’t enabled in your org, you won’t see this option. For more information, see [Set Up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&type=5) in Salesforce Help.

You must turn on Semantics AI in the Feature Manager. For more information, see [Enable Data 360 Features](https://help.salesforce.com/s/articleView?id=data.c360_a_feature_manager.htm&type=5) in Salesforce Help.

To use Semantics AI, enter a description of the calculated field you’re creating and click **Draft with Einstein**. A draft is created for you with all the properties and the formula.

Always review the drafted content carefully for accuracy before saving the calculated field. ![New Calculated Field dialog with Draft with Einstein buttons highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/dcc15028098182840d94c228af83f3fa_kix.abvam16bzhw6.png)

## Create a Calculated Dimension

[Calculated dimensions](https://help.salesforce.com/s/articleView?id=data.c360_a_sl_calc_fields_calc_dimension_settings.htm&type=5) don’t physically exist in the database and can be used to do data manipulations such as concatenating fields, grouping values, or performing logical tests.

*   **Consolidate dimensions:** If you have dimensions containing different pieces of information that are often used together you can concatenate them. For example, if there's a dimension for first name and a dimension for last name, you can combine them into a dimension for full name:  
    *   `[First Name] + " " + [Last Name]Copiar`to combine first and last name (don't forget the space between them.)  
        
    *   `[Last Name] + ", " + [First Name]Copiar`to combine them as last name comma first name (with a space after the comma)  
        
*   **Group dimensions:** If you have detailed values that you want to combine into categories, you can evaluate values and group them. For example, the following calculation takes five different types of book formats and casts them into two simple categories, paperback or hardcover.  
    *   CASE \[Book Format\] WHEN "Mass market paperback" THEN "Paperback" WHEN "Trade paperback" THEN "Paperback" WHEN "Paperback graphic" THEN "Paperback" WHEN "Hardcover" THEN "Hardcover" WHEN "Hardcover graphic" THEN "Hardcover" END
        

Imagine you want to create a calculated dimension to flag orders with same day shipping that weren't shipped on the same day.

1.  In the Semantic Model Builder, from the **New** dropdown menu, select **Calculated Field**.  
    ![Semantic Model Builder showing the calculated field option.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/8b419d8e150b7045b2f6622c45f5ea04_kix.7tb7v7z1nn3h.png)  
    
2.  In the **New Calculated Field** dialog, under **Field Type**, select **Dimension**.  
    
3.  From the **Data Type** dropdown menu, select the type of data you want to store in the calculated dimension. In this case, **Text**.  
    
4.  In the **Name** field, enter a descriptive and unique name such as`At Risk CasesCopiar`.  
    
5.  To define advanced settings, expand **Advanced**. Here you can  
    1.  Add a **Description**  
        
    2.  Customize the **API Name** (which can't be edited after the field is created)  
        
    3.  Set the **Data Role** as discrete or continuous, if applicable  
        
    4.  Toggle field visibility.  
        
6.  To add filters to the semantic calculated dimension, click **Filters**.  
    
7.  In the **Formula** area, enter the formula using the correct syntax. This is the heart of the calculated field.  
    1.  IF \[Ship Mode\] = "Same Day" AND ISNULL(\[Ship Date\]) = true AND DATEDIFF('day', \[Order Date\], TODAY()) > 1 THEN "Late shipping" END
        
    2.  This calculation looks at each record and checks to see if the case priority is High, the case status is New, and the case was created more than ten days ago. If so, the record is flagged as "At Risk"  
        
8.  Click **Save**.Here’s what the calculated dimension looks like when it’s done:  
    ![Create Calculated Field with example of syntax.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/2f10929e7be0ac6c8cac961715a10c4c_kix.31dp9931hpyy.png)  
    

You can now use this new calculated dimension when viewing a dashboard of case health so you can compare the number of high-risk cases, and the number of low-risk cases.

## Create a Calculated Measure

[Calculated measures](https://help.salesforce.com/s/articleView?id=data.c360_a_sl_calc_fields_calc_measure_settings.htm&type=5) don’t physically exist in the database and can be used to do numerical operations such as calculating ratios or percentiles.

Like other measures, a calculated measure has additional metadata like default aggregation, data type (number, percentage), data role (discrete or continuous).

Imagine your data has a field for Price and a field for Discount. To calculate Sale Amount, you'd need to create a calculated measure.

1.  In the Semantic Model Builder, from the **New** dropdown menu, select **Calculated Field**.  
    ![Semantic Model Builder showing the calculated field option.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/8b419d8e150b7045b2f6622c45f5ea04_kix.uwjxg2dwcct.png)  
    
2.  In the **New Calculated Field** dialog, under **Field Type**, select **Measure**.  
    
3.  From the **Data Type** dropdown menu, select data type. In this case, choose **Number**.  
    
4.  In the **Name** field, enter a descriptive and unique name such as`Sales AmountCopiar`.  
    
5.  To define advanced settings, expand **Advanced**. Here you can:  
    1.  Add a **Description**.  
        
    2.  Enter a unique **API Name**. You can’t edit the API name after creation.  
        
    3.  Set the **Aggregation Type**, such as Sum, Average, Count, etc  
        
    4.  Choose a setting for **Decimal Place**. The default is two.  
        
    5.  Set the **Data Role** to continuous or discrete  
        
    6.  Define the **Sentiment** by setting if an upward trend is good, bad, or neutral.  
        
    7.  Select **Treat Nulls as Zeros** if you want nulls to be replaced with zeros in calculated measures.  
        
    8.  Toggle field visibility.  
        
6.  To apply filters on the source fields for this calculated dimension to the semantic calculated dimension, select **Filters**.  
    
7.  In the **Formula** area, enter the formula using the correct syntax. This is the heart of the calculated field.  
    1.  `[Price]*(1-[Discount])Copiar`  
        

![Edit Calculated Field dialog with an example in the Formula box.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/851e3664d999a3e06b71ced9a59da1f0_kix.8sxurdxjazap.png)

17.  Click **Save**.  
    You can now query this field and see the number of escalated cases and then act accordingly.  
    

## Create a Metric

A metric is a KPI tracked over time, such as revenue over the past year. The core components of a metric are a measure representing the KPI and a time dimension that tracks its development over time.

For example, you can create a sales performance metric to track weekly sales, helping you assess whether your business is meeting its targets over a set period.

You can also create metrics in Tableau Next. For more information, see [Add a Metric to a Semantic Model](https://help.salesforce.com/s/articleView?id=analytics.tua_data_sdm_add_metrics.htm&type=5) in Salesforce Help.

1.  From the Semantic Layer tab, click to the **Metrics** tab then click **New Metric**. Select the Semantic Model to build your metric on.  
    1.  To create a metric from a specific model, navigate to the Semantic Model Builder, open the **New** dropdown, and select **Metric**.  
        

![New Metric dialog without values.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/faee316fe938f2176c6485cc30a424ec_kix.12ip7by0mdh2.png)

3.  Add a name and optional description to make the metric discoverable and easy to understand, and then click **Next**.  
    
4.  For Measure, select the field that represents your KPI.  
    
5.  (Optional) To add a filter, use the search box to **Add Filter**.  
    
6.  (Optional) Configure additional settings under **Measure Advanced Setup**.  
    3.  Define the Sentiment for an increase in the measure.  
        
    4.  Choose a default aggregation.  
        
    5.  Choose if the aggregation is cumulative or not.  
        
7.  For **Time Dimension**, choose a date field from your data source.  
    
8.  Click Next  
    
9.  (Optional) To add context and granularity, you can select **Additional Dimensions**.  
    You can add up to 20 dimensions. These dimensions act as are displayed on the metric card detail page. Insights that are toggled on will be calculated based on these dimensions.  
    
10.  Select **Next**.  
    
11.  (Optional) Adjust the insights as desired, including turning them on or off, and configuring details such as the singular and plural units for the insights.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

The Insights tab is only available for orgs that have Tableau Next.

Here’s what the metric looks like when it's done.![New Metric dialog.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-calculated-fields-and-metrics/images/ba601986c64d492da53884c8b61add82_kix.psyop0ddx7xn.png)

15.  Click **Save**.  
    

In this unit, you learned about calculated fields and how to create metrics in your semantic model. Head over to the next unit to learn how to test your semantic model, and how you can use the semantic model in other applications.

Respuestas de la prueba:

---

**Pregunta 1 — What is a calculated dimension in a semantic model?**

**Respuesta: B — A field defined by a formula.**

El documento describe las calculated dimensions como campos personalizados que no existen físicamente en la base de datos y se definen mediante fórmulas para crear nuevas dimensiones, como concatenar campos, agrupar valores o realizar pruebas lógicas.

---

**Pregunta 2 — Which of the following is a valid use case for a calculated dimension?**

**Respuesta: B — Creating a new field with the top-level domain of an email address (such as .org or .edu) without modifying the actual data.**

Este es el caso de uso más representativo de una calculated dimension: crear un campo derivado mediante lógica sobre datos existentes sin modificar la fuente original, similar a los ejemplos del documento como concatenar nombre y apellido, o agrupar formatos de libros en categorías. Las otras opciones describen operaciones fuera del alcance de una calculated dimension (crear tablas, calcular métricas temporales o configurar permisos).