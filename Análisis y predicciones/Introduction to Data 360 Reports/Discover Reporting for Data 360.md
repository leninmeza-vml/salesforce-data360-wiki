# Discover Reporting for Data 360

## Learning Objectives

After completing this unit, you’ll be able to:

*   Explain how Data 360 reports help uncover trends in harmonized customer data.  
    
*   Build a standard report using a Data 360 data model object (DMO).  
    

Before you start this module, consider completing these recommended Trailhead badges:

*   [Data 360 Basics for Marketers](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-basics)  
    
*   [Reports and Dashboards for Lightning Experience](https://trailhead.salesforce.com/content/learn/modules/lex_implementation_reports_dashboards)  
    

## Turn Data into Insights with Data 360 Reports

You ingested data from multiple sources, consolidated it into a consistent format, and unified it into rich customer profiles. Now that you’ve built a 360° view of your customers with Data 360, how do you use it to make smarter decisions?

With the Lightning Experience, creating reports on one or more related Data 360 objects is easy. You can create a standard report on a data model object (DMO), semantic model, or ‌calculated insight. Or, you can build a custom report that brings in data from related DMOs. Once your report has the right data lined up, group data to compare meaningful categories, filter records to focus on what matters most, and summarize fields to highlight trends. Tailor your report to your business goals and run it for near real-time results. For better insights, add a chart to your report.

You can create both standard and custom reports with Data 360. Here's when you'd use each type.

| **Report Type** | **Data 360 Object** | **When to Use** |
| --- | --- | --- |
| Standard Report | DMO, semantic model, or calculated insight | Analyze data from a single source |
| Custom Report | Multiple related DMOs | Combine data from up to 4 related DMOs |

Here’s what a sample Data 360 report looks like.

![Data 360 report that shows lead source records. The chart shows breakdown by stage and the table shows breakdown by source.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/75114aef4eda128cfe922dc24b5c47f9_kix.rzdjis178ulo.png)

This Data 360 report groups leads by source \[1\], and the chart shows how those leads break down by stage \[2\].

You can explore how different industries use Data 360 reports to answer important business questions.

| **Industry** | **Use Case** |
| --- | --- |
| Retail | **Goal**: The marketing team at Northern Trail Outfitters (NTO) is curious to know which recent email campaigns sparked the most interest.<br><br>**Approach**: NTO creates a standard report based on the Product data model object (DMO) and filters it to show only promotional emails with an Activated status. After grouping the results by campaign ID and sorting them by record count, the team can review which promotional emails had the best reach. |
| Hospitality | **Goal**: Sales reps at Coral Cloud Resorts want to upsell premium services to their highest-value customers.<br><br>**Approach**: The company’s sales team builds a report on the customer Lifetime Value (LTV) calculated insight. By grouping lifetime values by both industry and region and filtering for customers with an LTV of $10,000 or more, sales reps can quickly identify top-tier customers in each segment. This helps them prioritize who to target with upgraded offerings. |
| Healthcare | **Goal**: The Patient Engagement team at Bloomington Caregivers is keen on optimizing communication strategies based on patient consent data.<br><br>**Approach**: The team creates a custom DMO report using data from both the Engagement Channel Type DMO and the Engagement Channel Type Consent DMO. First, they filter the report to show only patients who have given consent to receive communications. They then group the results by engagement channel to list users by their approved channels. This way, the team can communicate with each patient only through the channels they’ve consented to. |

## Dashboards: Multiple Insights in One Place

As you can see, Data 360 reports help you discover key trends in your customer data. However, reports are just the start. Sometimes, you need to compare data from multiple reports. Other times, you need to connect the dots between Data 360 records and CRM data. That’s where Lightning Dashboards can help.

You can build dashboards with components that use different Data 360 reports, or combine a Data 360 report with a CRM report in the same dashboard. Review results from both sources side by side, in a single view. Dashboards also let you share insights with your entire team. Pretty neat, right?

You’ve learned how reports and dashboards with Data 360 data can fast-track your decision-making with data. Now, create a Data 360 report by following along with the staff at Northern Trail Outfitters (NTO) as they build one.

## Build a Report with a Standard Data 360 DMO

NTO recently redesigned its website to improve the online shopping experience. The new layout focused on making product discovery easier, added high-quality visuals for a more engaging browsing experience, and streamlined the checkout process to help shoppers complete purchases faster.

Isabelle Givens, NTO’s Digital Marketing Manager, wants to get a sense of how the website redesign is influencing shopping patterns. Are some product categories attracting more attention than before? What do purchasing patterns look like among mobile shoppers? Isabelle recruits Michele, NTO’s Technical Marketer, to help. NTO has been using Data 360 to capture customer data, so the info Isabelle needs is already there. Since Isabelle is keen to learn how the revamped website is impacting customer journeys, Michele heads straight to the Website Engagement Data Model Object (DMO). This standard DMO contains all the data related to how shoppers interact with NTO’s website including clicks, device type, browser used, and more. With the right DMO for the job, Michele builds a report to explore the trends Isabelle is curious about.

Follow along with Michele as she builds a Data 360 report using the standard Website Engagement Data Model Object (DMO).

1\. From the Website Engagement DMO’s record page, click **Create Report**.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

You can also go to the DMO’s list view, and click **Create Report** from a DMO’s Action menu.

2\. Add the columns needed to analyze how long customers stay engaged on the website. From the **Add Columns** dropdown in the report builder, add **Website Engagement ID**, **Account Contact**, and **Website Visit Duration** to the report.

3\. Click **Refresh** for a report preview.

![Data 360 report on website engagement with columns that help analyze customer engagement on the website](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/722c41fc8028c4f052955982c042ce26_kix.i77d8wnzivtb.png)

4\. To calculate the average website session, from the **Website Visit Duration** column’s dropdown menu, select **Summarize** and click **Average**.

![The drop-down menu in Data 360 report’s column showing  summarize options](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/d6016d675998e7bb4069acbad6e80f7c_kix.sogab0m3fvn4.png)

5\. Run the report.

On the report run page, Michele reviews the average session duration. The number looks great‌—and well within a healthy range.

![The Data 360 report’s run page that shows the average website session in minutes.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/1313dd45ede82ff41d44c63501b22aa9_kix.1sbzioctl6te.png)

The website refresh seems to be a hit with customers! But, Michele wants to dig deeper. The latest spike in web traffic has mostly been from mobile users. And since Isabelle is curious about which product categories are trending with shoppers, Michele narrows the results to find just that.

1.  On the report run page**,** click **Edit** and add select **Website Catalog Category** as a row grouping.  
    
2.  In the **Filters** tab, apply a filter for **Device Type** not equal to **Desktop**.  
    

Select Device type as **Field,** Operator **Not equals** enter **Desktop** in the textbox.

3.  Run the report again.  
    
4.  Sort the **Catalog category** column by record count in descending order.  
    

![The sort option for a column in a Data 360 report.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/ef0090f8c4702a9ca51e758e6459523c_kix.2aexzh42vnmk.png)

Isabelle has a clearer view of which categories are trending—and which ones need a boost. Looks like NTO’s website visitors on handheld devices are most interested in watersports gear. But the camping and hiking categories are trailing behind.

![Data 360 web engagement report that shows results after applying the sort option.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/introduction-to-data-cloud-reports/discover-reporting-for-data-cloud/images/9c648e5556e8934df40a7b2a938d4ab1_kix.tupdvr70tss3.png)

## Wrap-Up

After gleaning some important information about her customers from the work Michele did, Isabelle decides to prioritize her marketing efforts, focusing on boosting engagement for categories that are underperforming while capitalizing on the success of trending categories.

Now you know how to create a standard report from a Data 360 object and find key business insights. In the next unit, you’ll learn how to create a custom report with Data 360 objects so you can combine records from multiple DMOs and gain a deeper knowledge of the related data.

## Resources

*   [_Salesforce Help_: Data 360 Reports and Dashboards](https://help.salesforce.com/s/articleView?id=data.datacloud_reports_dashboards_overview.htm&type=5)
*   [_Salesforce Video_: Build a Data 360 Report on a Standard Data Model Object](https://salesforce.vidyard.com/watch/kS19jnzK2L7vDrF767AmCR)

Respuestas de la prueba:

---

**Pregunta 1 — When should you create a custom report in Data 360?**

**Respuesta: C — When you need to analyze data from related DMOs.**

El documento especifica que los reportes personalizados se usan para combinar datos de hasta 4 DMOs relacionados, mientras que los reportes estándar se usan para analizar datos de una sola fuente.

---

**Pregunta 2 — Which Data 360 objects can you use to create a standard report?**

**Respuesta: A — Data Model Objects (DMOs), semantic models, and calculated insights.**

El documento indica explícitamente que puedes crear un reporte estándar sobre un **DMO**, un **modelo semántico** o un **calculated insight**, los tres tipos de objetos disponibles para reportes estándar en Data 360.