# Create and Verify Your Copy Field Enrichment

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create fields and grant permissions to those fields at the Account level.  
    
*   Create a copy field enrichment based on a calculated insight.  
    
*   Trace data from a copy field back to the calculated insight.  
    

You've done the hard work of bringing in your Case and Account data into Data 360. You used SQL to create a calculated insight to calculate the total cases and total open cases for each account. Now, you can copy those valuable insights to new fields on Accounts, so Wataru, your sales rep, can quickly see which customers most need to purchase a new software pack. By adding Data 360 insights to account fields, you can improve your sales reps' efficiency and help them increase sales. Let’s set up the copy field enrichment to sync regularly so your sales reps always get the latest insight into their accounts.

## Create New Fields on Account

In Sales, create a Total Open Cases field and a Total Cases field to hold the information you'll copy from Data 360.

1.  From Setup, search for and select **Object Manager**.  
    
2.  Select **Account**, then **Fields & Relationships**.  
    
3.  Click **New**.  
    
4.  For Data Type, select **Number** and click **Next**.  
    
5.  For Field Label, enter **Total Open Cases**. Accept the remaining defaults and click **Next**.  
    
6.  Accept the Field Level Security Details and click **Next**.  
    
7.  Add the fields to your desired page layouts and click **Save**.  
    

Your Total Open Cases field is added to Account. Repeat these steps to add the Total Cases field to Account.

## Grant the Customer 360 Data Platform Integration User Write Permission to Your New Field

Salesforce uses the behind-the-scenes Customer 360 data platform integration user to copy data from Data 360 to your Sales CRM. Let’s grant that user access to your new Case fields, so they can enrich your cases with Data 360 insights.

1.  In your Sales org, in **Setup**, search for and select **Permission Sets**.  
    
2.  Select the **Customer 360 Data Platform Integration** permission set.  
    
3.  Click **Object Settings**, then **Accounts**.  
    
4.  Select all options listed.  
    

![The object permissions for Accounts with all permissions checked in the Enabled column.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/3441ed57a2a0bebc4c9316d8a3bc9934_kix.d2a7j7gne1n2.png)

5.  For Total Cases field and Total Open Cases, grant edit and read access.  
    

![The permissions for the Total Cases field and the Total Open Cases field. All permissions are enabled.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/8773b9266a036bf79321146acee98d9c_kix.wagyt2zcvkcy.png)

6.  Click **Save**.  
    

## Create your Copy Field Enrichment

Create your copy field enrichment so that your sales reps can quickly see which accounts have a high number of cases. Armed with this information, your reps can target their outreach and drive sales by helping customers resolve their difficulties.

1.  In **Setup**, search for and select **Copy Field**.  
    
2.  Click **New**.  
    
3.  Select or enter the following information.  
    

*   Data Space is **default**.  
    
*   Data Cloud Object is **Open Cases on Account**.  
    
*   Target Object is **Account**.  
    

4.  ID Matching Method is **Use the Primary Key**.  
    

![Screenshot of the copy field enrichments page showing how the source object is mapped to the target object.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/720e0124ef3b63c5794d92490a91826f_kix.1c8b66qn8zah.png)

5.  Click **Next**.  
    
6.  Select the fields **total\_cases** and **total\_open\_case** and click **Next**.  
    
7.  Give your enrichment the name `Open Cases on AccountCopiar` and click **Next**.  
    
8.  In **Field Mapping**, map total\_open\_cases to Total Open Cases, and total\_cases to Total Cases.  
    

![The field mapping for total_open_cases metric in Data Cloud to the Total Open Cases field on Account.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/d9c7283b89ad604318362effe0cc7dbb_kix.oggrjrjs8148.png)

9.  Click **Save and Start Sync**. Syncing data from Data 360 takes a few minutes.  
    

## Verify Your Copy Field Enrichments

Once your copy field enrichment has successfully synced, you can see your account's total cases and total open cases. Trace the data in your Total Cases field back to your copy field enrichment in Data 360.

1.  From **Setup**, search for **Enrichments** and open **Copy Field**.  
    
2.  Double click your **Open Cases on Account** enrichment.  
    
3.  Select **Sync History** and verify that Sync Status is Complete.  
    

![Sync Status log is complete.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/42e27fa2bb29c2c6eee959f1f9929849_kix.bk0tx2kmjhxt.png)

4.  From Sales, select **Accounts** and open an account.  
    
5.  Verify that your copy field insight has populated the account's Total Cases and Total Open Cases fields.  
    

![An account with the new Total Cases and Total Open cases fields. This account has 7 total cases and 2 total open cases.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/8bf5bbc3d043b54af06ee8ca0dc49f2c_kix.35rh603evmfj.png)

Now your sales reps can quickly see the total and open cases on their accounts! To help you explain the source of these insights, let's trace the data back to your calculated insight.

1.  From your browser URL, copy the account ID. For example, if the account URL is `https://myorg.lightning.force.com/lightning/r/Account/0016P000008D9DwQAK/viewCopiar`, the account ID is **0016P000008D9DwQAK**.  
    
2.  In Data Cloud, from **Calculated Insights**, select **Open Cases on Account**.  
    
3.  Select the down arrow ( ![“”](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/e6707033ee963d5641a09210e8585550_kix.lhjjygidbl0z.png)), then select **Create Report**.  
    
4.  In the report, search for the account ID.  
    

Verify the account's Total Cases and Total Open Cases are copied from Data 360's calculated insight.

![An account with the new Total Cases and Total Open Cases fields next to a calculated insight report. In the report, the total cases and the total open cases match the total cases and total open cases in the account.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-enrichments/create-and-verify-your-copy-field-enrichment/images/077792ab3c12da741bc3a6b49c99f780_kix.u1ugww7m72iu.png)

## Summary

Wataru is under pressure to close more sales as the quarter's end approaches. He knows that some of his accounts have outgrown their current software and have recently had service escalations. His accounts can resolve their issues by purchasing more advanced software. Wataru doesn't have time to dig through case data in all the company's service orgs. He needs a fast way to find accounts with a high number of cases so he can help his customers and also drive sales. This is where your copy field enrichments save the day! Wataru can quickly see his account's total and still-open cases, then engage accounts most likely to need the new software's help.

Congrats! You’ve copied your calculated insight metrics to your custom account fields so that your sales reps can quickly see an account's cases and create a compelling outreach message. In this module, we used your CRM Service data from a single org, but you can also use case data from external data streams, or aggregate case data from multiple orgs.

## Resources

*   [_Salesforce Help_: Create a Copy Field Enrichment](https://help.salesforce.com/s/articleView?id=data.c360_a_create_a_copy_field_enrichment.htm&type=5)
*   [_Salesforce Help_: Enrichment Considerations](https://help.salesforce.com/s/articleView?id=data.c360_a_enrichment_considerations.htm&type=5)
*   [_Blog_: Ways to Leverage Data Cloud Copy Fields and Related Lists](https://www.salesforceblogger.com/2024/02/29/ways-to-leverage-data-cloud-copy-fields-and-related-lists/)

Respuestas de la prueba:

---

**Pregunta 1 — When is the data ready to view after creating a copy field enrichment?**

**Respuesta: D — When the copy field enrichment's sync status is complete.**

El documento indica que después de hacer clic en "Save and Start Sync", la sincronización tarda unos minutos, y para verificar que está lista debes ir a **Sync History** y confirmar que el **Sync Status** sea **Complete**.

---

**Pregunta 2 — How can you see the calculated insight's output to verify the enrichment?**

**Respuesta: B — In Data 360, open your calculated insight and select Create Report.**

El documento muestra exactamente este proceso para verificar los datos: desde Calculated Insights, abres **"Open Cases on Account"**, haces clic en la flecha desplegable y seleccionas **"Create Report"**, lo que te permite comparar los valores del calculated insight con los que aparecen en los campos del Account en Sales.