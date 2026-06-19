# Build a Custom Data 360 Report

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create a custom report type using related DMOs.  
    
*   Build a Data 360 report with the custom report type.  
    

## Create a Custom Report Using Multiple Data 360 Objects

After reviewing the report Michele created, Isabelle has strategies to reengage shoppers with underperforming product categories. Now, Isabelle turns her focus to other ways of maximizing website revenue.

One area she’s targeting is to convert the products in customers’ shopping carts to purchases. Isabelle has an idea that could help drive more conversions. She thinks a quick reminder about unused discount vouchers could nudge loyalty program members to complete their orders. In this scenario, shoppers pay less and NTO sees a lift in sales. A win-win opportunity!

To roll out those reminders, the marketing team needs a list of loyalty program members with items pending checkout as well as valid discount vouchers. Michele’s on it! To help the team out, she focuses on these Data 360 DMOs:

*   **Loyalty Program Member DMO**, which contains details about people enrolled in NTO’s loyalty program.  
    
*   **Shopping Cart Engagement DMO**, which captures customers’ shopping cart activity.  
    
*   **Voucher DMO**, which includes information about the vouchers tied to the loyalty program.  
    

DMOs for the report identified? Check! But how do you tie data from all three together in a single report to get the answers you need? When you want to pull in data from multiple related DMOs, you use custom report types. They give you all the power of Lightning reports—with a setup tailored to your unique data needs.

## Set Up the Relationships That Define Your Report

Before Michele creates the custom report type, she starts by defining how the data from loyalty members, cart activity, and vouchers are connected. She does this by activating the relationships between the three DMOs: Loyalty Program Member, Shopping Cart Engagement, and Voucher DMOs. This initial step lets you choose which related objects to include, how to join them, and how the report handles related records using “with” or “with or without” logic.

Here’s how Michele establishes the relationships between Data 360 DMOs step by step.

1.  On the Shopping Cart Engagement DMO’s Relationship tab, click **Edit**.  
    
2.  In the Edit Relationships box, click + **New Relationship**.  
    
3.  Set these values:  
    

*   For the Shopping Cart Engagement object, select **Account Contact** as the field.  
    
*   Set Cardinality to **N:1**.  
    
*   Select **Loyalty Program Member** as the related object in Data 360.  
    
*   Select **Account Contact** as the related field in the Loyalty Program Member object.  
    

This relationship tells Data 360 that each cart engagement links to one loyalty member, but a member can have many engagements.

4.  Click **Save & Close**.  
    

![Setting the relationships between two Data 360 web objects.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/969d83942b4515c785237a499bdc8efc_kix.uqdmomxl3frl.png)

5.  Using a similar process, set up the relationship between the Voucher DMO and Loyalty Program Member DMO from the Voucher DMO’s Relationship tab.  
    *   For the Loyalty Program Member object, select **Party** as the field.  
        
    *   Set Cardinality to **N:1**.  
        
    *   Select **Voucher** as the related object in Data 360.  
        
    *   Select **Account Contact** as the related field in the Loyalty Program Member object.  
        
6.  Click **Save & Close**.  
    

## Set Up a Custom Report Type

With the required relationships between the DMOs established, Michele can build the custom report type that brings the data together and helps the team identify customers for reengagement.

Here are the steps she takes.

1.  In Setup, enter **Report Types** in the Quick Find box and select it from the results.  
    
2.  Click **New Custom Report Type**.  
    
3.  For the primary object, select **Loyalty Program Member**.  
    
4.  Add a name and a description for your report type.  
    
5.  Save the report type in the Data Cloud category and click **Next**.  
    
6.  In the New Custom Report Type window, relate the Shopping Cart Engagement DMO to the Loyalty Program Member DMO.  
    
7.  Because you want to include only loyalty members who have shopping cart activity, select the first option: **Each “A” record must have at least one related “B” record**.  
    

This option creates an inner join. So your report includes only records with related data from both DMOs. That’s what you need to identify members who recently added items to their carts.

![Selecting the join type for a custom Data 360 report.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/8c352476739b3e7d5d1bad0739f67b4f_kix.oi37uixcx0pi.png)

8.  Click **Save**.  
    

Next, Michele customizes the field layout for the report type.

1.  In the Edit Layout panel, click **+ Lookup Fields**.  
    
2.  To include voucher information in the report, select these fields from the Voucher DMO:  
    *   Voucher ID  
        
    *   Voucher Status  
        
    *   Discount Percent  
        

These details help the team spot which vouchers are active, how much of a discount they offer, and which voucher belongs to each member.

3.  Click **Apply**.  
    
4.  Add the fields to the Shopping Cart Engagement section.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Alternatively, create a section to keep the voucher fields separate. They’ll appear in their own group in the report builder’s Fields pane.

5.  Click **Save**.  
    

![Setting the relationships between two Data 360 web objects](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/f55a040cd433962272c06161f335d404_kix.jd3ldq3pw94.png)

## See Your Custom Report in Action

The report type is ready. Michele’s next step is to build the report using the report type she just created.

1.  In the Reports tab, click **New Report**.  
    
2.  From the Data Cloud category, select the report type you created and click **Start Report**.  
    
3.  Add the fields that provide the details you’ll use to reach out to loyalty members with voucher reminders: Account Contact, product name, and the discount available to them.  
    
4.  Apply filters to narrow the report to active loyalty members who have vouchers and were in the process of buying products from your online store.  
    
5.  To do that, in the Filters tab, set these filters:  
    *   Shopping Cart Event Type = Add to cart or Checkout in progress  
        
    *   Loyalty Program Member Status = Active  
        
    *   Voucher Status = Issued  
        

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

When applying multiple filters that need to work together, [use filter logic](https://help.salesforce.com/s/articleView?id=analytics.filter_logic.htm&type=5) so your report shows only the records that meet all your criteria.

![The Filters tab in a Data 360 report with filter logic applied between the filters.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/49ac5571a901b29a47c6db5cb9e56484_kix.ca6e3bz753jj.png)

6.  Run the report.  
    

Michele has the report ready for review. She follows the instructions in this [help documentation](https://help.salesforce.com/s/articleView?id=analytics.reports_export.htm&type=5) to export the report and share it with Isabelle. The team can now quickly identify which loyalty members to reach out to and turn cart activity into completed orders. This is great progess!

## Turn Grouped Data into Visual Insights

Michele has another question on her mind. Is there a connection between members’ unfinished orders and the product categories they’re shopping for? To investigate, she groups and visualizes the data.

Let’s see how Michele can surface patterns by grouping the data in the report.

1.  In the report builder, click **Edit**.  
    
2.  In the Outline tab, under Group Rows, from the **Add group** picklist, select **Product Category**.  
    

Now, Michele decides to visualize the data with a chart to quickly see patterns.

3.  To add the chart, click ![chart icon](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/efb77be2969dcaaf1c88b5714c72cd7f_kix.xntthu1q0uun.png) at the top of the report.  
    
4.  Save and run the report.  
    

The report now highlights data patterns, both in table and visual formats.

![Data 360 report with both chart and table included.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/build-a-custom-data-cloud-report/images/e904c2d1f7a24b895b3562457b070719_kix.39v89gv0cxgd.png)

The report reveals that watersports gear has the highest rate of cart abandonment. Michele shares this finding with Isabelle, and together with the marketing team, they prioritize the watersports gear category and brainstorm ideas to re-engage shoppers and convert abandoned carts into sales.

## Wrap Up

Great job! You can now build reports that provide valuable insights into your customer data. These skills enable you to make powerful data-driven decisions and execute your business strategy by tailoring reports to your specific needs, whether you’re analyzing a single object or combining multiple Data Model Objects.

## Resources

*   [_Salesforce Video_: Build a Data 360 report Using a Custom Report Type](https://salesforce.vidyard.com/watch/83zVwQFksiuWABh4fdRWHb)
*   [_Salesforce Help_: Create a Custom Report in Lightning Experience](https://help.salesforce.com/s/articleView?id=xcloud.reports_enhanced_defining_report_types.htm&type=5)

Respuestas de la prueba:

---

**Pregunta 1 — How do you unify Data Model Objects (DMOs) in a custom report type?**

**Respuesta: B — Link the DMOs using relationships.**

El documento muestra que antes de crear el reporte personalizado, Michele establece las relaciones entre los DMOs (Loyalty Program Member, Shopping Cart Engagement y Voucher) desde la pestaña **Relationships** de cada DMO, definiendo campos, cardinalidad y objetos relacionados.

---

**Pregunta 2 — How can you tailor your custom report to a specific use case?**

**Respuesta: C — Apply filters to relevant fields.**

El documento ilustra exactamente esto cuando Michele aplica filtros específicos para narrowear los resultados: `Shopping Cart Event Type = Add to cart or Checkout in progress`, `Loyalty Program Member Status = Active` y `Voucher Status = Issued`, logrando así que el reporte muestre solo los registros relevantes para su caso de uso.
