# Build a Segment and Report

## Learning Objectives

In this step, you’ll:

*   Create a segment.  
    
*   Create an activation target.  
    
*   Create an activation.  
    
*   Publish a segment to a DMO.  
    
*   Build a report.  
    

## About Segmentation

When you're surrounded by a wealth of data, sometimes you want to narrow your focus to a specific group. You do this by creating a segment filter within Data 360, enabling you to comprehend, target, and engage your customer base with precision. To learn more about segmentation before you start, check out [Segmentation in Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation).

## Create a Segment

Segments can be used for multiple purposes. In this step, you create a segment based on the formula field and the calculated insights created previously. You segment based on if a unified profile has a support case **or** if they are US–based.

1.  From Data Cloud, go to the **Segments** tab under the More menu and click **New**.  
    
2.  Leave **Use a Visual Builder** and **Standard Segment** selected and click **Next**.  
    

![visual builder and standard segment selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/e8712f0edd06a6baac26b9d509e38fe5_kix.8v6okxfnn2mf.jpg)

3.  The default Data Space should be auto-selected. From the Segment On dropdown, select **Unified Individual**.  
    
4.  Next, name your segment, `Lead InfoCopiar`. Add an optional description to describe your segment.  
    
5.  Click **Next**.  
    

![Create a new segment.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/1288bf0e2f48b9a6c8223eb14bcc89f2_kix.bst3vgei4jpm.jpg)

6.  Leave **Standard Publish** selected.  
    

7.  Leave **Do Not Schedule** selected from the Publish Schedule.  
    
8.  Click **Save**.  
    

Now you’re ready to select attributes and define a filter for your new segment.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

The segment canvas may take a few moments to load.

### Add Filters

The goal of this segment is to narrow down the list of US–based leads or leads that have at least one case. Follow these steps to add filters to obtain this result.

1.  With the Attributes pane selected, expand **Related Attributes**.  
    
2.  Search for `Unified Individual Case CountsCopiar`, under the Calculated Insights category.  
    
3.  Drag the **\# count\_case\_id\_c** to the canvas.  
    
4.  From the Operator dropdown, select **Is Greater Than Or Equal To**.  
    
5.  For the Value, type `1Copiar`.  
    
6.  Click **Done**.  
    

![Related attributes with count_case_id_C selected with an operator of Is Greater Than Or Equal to 1.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/66ab9d4b2c45fe35ce57324a165b60d9_kix.x4htnn4f271e.png)

7.  Next, search for `Is US BasedCopiar` under the **Lead** category.  
    
8.  Select and then drag the **Is US Based** attribute to the canvas.  
    
9.  Within the Lead container:  
    

*   Under Container Path select Lead.Party > Party.Individual > Unified Individual.Unified Individual Id.  
    
*   For Measurement, select **Count**.  
    

*   For the Operator, select **At Least**.  
    
*   For Value, enter `1Copiar`.  
    
*   From the next Operator dropdown, select **Is Equal To**.  
    
*   For the Value, type `TRUECopiar`and select **True**.  
    

10.  Click **Done**.  
    
11.  Change the operator to the right of your selections in the canvas to **Or** and click **Save**.  
    
12.  Once the number has updated, click **Done**.  
    

Great! You’ve created a filtered segment for a group of unified profile leads who have a case or are US–based.

## Activate a Segment

After you create a segment in Data 360, you publish a segment to an activation associated with an activation target. An activation target is used to store authentication and authorization information for a given activation platform. Targets include Marketing Cloud, Data 360, B2C Commerce, Amazon Ads, and Google Audience Insights to name a few.

### Create a New Activation Target

First you need to create an activation target to store that data back in Data 360. This is useful if you don’t have a target system with which to activate Data 360 segments, but you still want to use the activated data.

1.  Go to the **Activation Targets** tab under the More menu option.  
    
2.  Click **New**.  
    
3.  Select **Data Cloud,** not Data Cloud (Loyalty), and click **Next**.  
    

![New Activation Target.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/a006be9df5362f8c9994c5a448cc07aa_kix.krgyvqp0nkl3.png)

4.  Name your Activation Target `Data Cloud SegmentsCopiar`. Add an optional description.  
    
5.  Select **default** for your Data Space.  
    
6.  Click **Save**.  
    

### Activate Your Segment

Now that you have a target established (the where), you can activate your segment (the what). In this case, you want to save the data from your segment into a Data 360 object. To see the content of your segment in Data 360, you need to activate it to the target selected. You can do this from the segment page or in the Activations tab.

1.  Go to the **Activations** tab under the More menu option.  
    
2.  Click **New**.  
    
3.  Select **Segment** and click **Continue**.  
    
4.  Keep the default data space, select the newly created **Lead Info** segment.  
    
5.  Select **Data Cloud Segments** as your Activation Target.  
    
6.  For Activation Membership, select **Unified** **Individual**.  
    
7.  Click **Continue**.  
    
8.  Next to Email, click **\+ Select** and then **Next**.  
    

![New Activation with email selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/a2b896b799773783b342c687f9f3bac1_kix.ibb9erouui2s.png)

9.  Click **Add Attributes**.  
    
10.  From Direct Attributes under Unified Individual, drag **First Name** and **Last Name** under the Unified Individual section on the right, next to the existing Unified Individual Id.  
    
11.  From Related Attributes add **Case Status** to the canvas below the Unified Individual section.  
    

![New Activation with last name added as an attribute.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/41bb2ecba62a749590807dbd910d7bda_kix.7oewg6ys95vd.jpg)

12.  Click **Save**.  
    
13.  Under Case, select **Case Status** from the Sort By dropdown and **Descending**.  
    

![From Case, sort by Case Status.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/7e56ab2eca26776e9c07dc11648db2a8_kix.62pclg6891bl.png)

14.  Click **Next**.  
    
15.  Name the activation `CasesCopiar`.  
    
16.  Confirm the Incremental Refresh is selected and then click **Save**.  
    

### Publish Your Segment

Now that you have your segment, activation target, and activation, you need to publish your Segment.

1.  Navigate back to **Segments**.  
    
2.  Select your Lead Info segment.  
    
3.  From the segment page, from the dropdown click **Publish Now**.  
    

![Dropdown with Publish Now selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/860266d3e1ca18812558ddf6d578dd46_kix.zah0j9qs9dy.png)

Once the segment is published to the activation target, an Audience DMO is created with the activated records. While it can take some time to process, to view these records, go to the Data Explorer tab and select the corresponding Audience DMO. It’s also good to know that segments activated to Data 360 can be retrieved using Query API.

## Create a Report

You can create reports based on insights and other objects. You can do this from the Reports tab and from the list view in Calculated Insights.

1.  Navigate to **Calculated Insights**.  
    
2.  From the list view, find the dropdown at the end of the row for the **Unified Individual Case Counts** insight.  
    
3.  Select **Create Report**.  
    
4.  View the Groups and Columns and adjust the order, if desired.  
    
5.  Click **Save & Run**.  
    
6.  Name your report, `Lead CasesCopiar`.  
    
7.  Click **Select Folder**, select **Public Reports** and then click **Select Folder** again.  
    

![Save Lead Cases report.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/build-a-segment-and-report/images/a2e8302a3a3a14e8a09af6d246d5020f_kix.t5zaqt5tmd9c.png)

8.  Click **Save**.  
    

## Verify Your Work

Now that you have your segment created, check your work and click **Verify Step.** For this exercise, we’re just checking that the segment and activation were set up correctly–you don’t have to wait for the activation to verify your work.

## Hands-on Journey

Congrats on finishing this hands-on journey about Data 360! In this project, you learned how to create data streams and formula fields, and how to map data to Data 360. You also learned how to query using insight builder, how to segment, create activation targets, and activate and publish your segment. And, you explored how to create a report from your calculated insight.

These skills enable you to get started using and connecting your data to Data 360. Once you have data in Data 360, you can effectively manage and use your unified data to achieve a deeper understanding of your customers and make more impactful business decisions.

## Resources

*   [_Trailhead_: Segmentation in Data 360](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation)
*   [_Salesforce Help_: Create a Standard Segment in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_create_a_segment.htm&type=5)
*   [_Salesforce Help_: Segment On](https://help.salesforce.com/s/articleView?id=data.c360_a_segment_on.htm&type=5)
*   [_Salesforce Help_: Segmentation Operators in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_datatype_expression_operators.htm&type=5)
*   [_Salesforce Help_: Segment Types and Statuses](https://help.salesforce.com/s/articleView?id=data.c360_a_segment_types_statuses.htm&type=5)
*   [_Salesforce Help_: Create a Data 360 Activation Target](https://help.salesforce.com/s/articleView?id=data.c360_a_create_dc_audience_dmo_activation_target.htm&type=5)
*   [_Salesforce Help_: Create an Activation for a Data 360 Target](https://help.salesforce.com/s/articleView?id=data.c360_a_create_data_cloud_activation.htm&type=5)

# Guía: Build a Segment and Report

---

## Parte 1: Crear el Segmento

1. Ve a **More** → **Segments** → **New**
2. Deja seleccionado **Use a Visual Builder** y **Standard Segment** → **Next**
3. En "Segment On" selecciona **Unified Individual**
4. Nombre: `Lead Info` → **Next**
5. Deja **Standard Publish** y **Do Not Schedule** → **Save**

---

## Parte 2: Agregar Filtros al Segmento

**Filtro 1 - Casos:**
1. En el panel Attributes → expande **Related Attributes**
2. Busca `Unified Individual Case Counts` (categoría Calculated Insights)
3. Arrastra **# count_case_id_c** al canvas
4. Operator: **Is Greater Than Or Equal To**
5. Value: `1` → **Done**

**Filtro 2 - US Based:**
1. Busca `Is US Based` (categoría Lead)
2. Arrastra **Is US Based** al canvas
3. Configura:
   - Container Path: **Lead.Party > Party.Individual > Unified Individual.Unified Individual Id**
   - Measurement: **Count**
   - Operator: **At Least**
   - Value: `1`
   - Siguiente Operator: **Is Equal To**
   - Value: `TRUE`
4. **Done**

5. Cambia el operador entre los dos filtros a **Or** → **Save** → **Done**

---

## Parte 3: Crear Activation Target

1. Ve a **More** → **Activation Targets** → **New**
2. Selecciona **Data Cloud** (no Data Cloud Loyalty) → **Next**
3. Nombre: `Data Cloud Segments`
4. Data Space: **default** → **Save**

---

## Parte 4: Crear la Activación

1. Ve a **More** → **Activations** → **New**
2. Selecciona **Segment** → **Continue**
3. Selecciona el segmento **Lead Info**
4. Activation Target: **Data Cloud Segments**
5. Activation Membership: **Unified Individual** → **Continue**
6. Junto a **Email** → clic en **+ Select** → **Next**
7. Clic en **Add Attributes**
8. Desde Direct Attributes (Unified Individual) arrastra:
   - **First Name**
   - **Last Name**
9. Desde Related Attributes arrastra **Case Status** al canvas
10. En Case → Sort By: **Case Status**, orden: **Descending**
11. **Next** → Nombre: `Cases`
12. Confirma **Incremental Refresh** → **Save**

---

## Parte 5: Publicar el Segmento

1. Ve a **Segments** → selecciona **Lead Info**
2. Despliega el dropdown → **Publish Now**

---

## Parte 6: Crear el Reporte

1. Ve a **Calculated Insights**
2. Encuentra **Unified Individual Case Counts** en la lista
3. Al final de la fila, despliega el dropdown → **Create Report**
4. Revisa Groups y Columns → **Save & Run**
5. Nombre: `Lead Cases`
6. Clic en **Select Folder** → selecciona **Public Reports** → **Select Folder**
7. **Save**
