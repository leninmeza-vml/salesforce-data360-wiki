# Access Data 360 from Flows

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create a record-triggered flow.  
    
*   Retrieve data model object (DMO) data in a flow.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

We highly recommend that you have a good level of knowledge of flows and Data 360 before you work on this badge. To learn about flows, complete the [Build Flows with Flow Builder](https://trailhead.salesforce.com/content/learn/trails/build-flows-with-flow-builder) trail. To learn about Data 360, complete the [Unlock Your Data with Data Cloud](https://trailhead.salesforce.com/users/strailhead/trailmixes/unlock-your-data-with-data-cloud) trailmix.

In Flow Builder, you can use the Get Records element in any flow to retrieve data from any data model object (DMO). With this ability, your flows can access data from any of your external data sources, such as preferred identity or contact information, loyalty program status, web-based purchases, mobile app activity, and more.

Your new Data 360 playground (the one you created in the previous unit) is set up to resemble Coral Cloud Resorts’ Salesforce org and their new Data 360 installation. In these exercises and hands-on challenges, you work with DMOs and CIOs that simulate Coral Cloud Resorts’ guest data, reservations, and shopping behaviors.

## Create a Flow to Retrieve Data from a Data Model Object

Let’s look at an example of how to access DMO data in a flow. As a member of Coral Cloud Resorts’ Salesforce admin team, you’re responsible for data accuracy in your Salesforce org. In this org, the Contacts object contains your guest records, but there’s also an external guest database outside of Salesforce. To keep these two groups of data aligned, the Contact object’s External ID field contains the unique ID of the same person in the external guest database.

Today, your team keeps this External ID field up-to-date on every contact manually. That’s prone to human error and also tedious. So let’s automate setting the External ID when a contact is created. The guest’s email address is the most consistent commonality between the Salesforce contacts and the external guest records, so use the email address to line up the records. And while you’re at it, check if the contact’s phone number is blank; if so, fill it in from the external guest information.

Fortunately, the email address, phone number, and unique external ID are all found in the Contact Point objects, such as Contact Point Phone and Contact Point Email. The Contact Point objects don’t have a field called “External ID”, but Coral Cloud has mapped the guests’ unique IDs to the Contact Point objects’ Party field.

For this flow, you retrieve from the external guest data source the Contact Point Email record that has the new contact’s email address. Then, if the contact’s phone number is:

*   Blank:  
    *   Retrieve the Contact Point Phone record that has the same Party value as the Contact Point Email.  
        
    *   Update the new contact’s External ID with the Party value.  
        
    *   Update the contact’s Phone with the phone number from the Contact Point Phone record.  
        
*   Not blank: Update the new contact’s External ID with the Party value.  
    

![”Diagram corresponding to the preceding flow logic.”](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/access-data-cloud-from-flows/images/9fa60bfe9c45d42f8a8185518d8c0f60_kix.ss7zaqg0xnfn.png)

1.  From Setup, enter `FlowsCopiar` in the Quick Find box and then click **Flows**.  
    
2.  Click **New Flow**.  
    
3.  Under Frequently Used, select **Record-Triggered Flow**.  
    
4.  In the Configure Start panel:  
    *   For Object, select **Contact**.  
        
    *   For Trigger the Flow When, select **A record is created**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   In the condition requirement fields:  
        *   For Field, select **Email**.  
            
        *   For Operator, select **Is Null**.  
            
        *   For Value, select **False**.  
            
    *   Click **Add Condition**.  
        
    *   In the second condition requirement:  
        *   For Field, select **External Id**.  
            
        *   For Operator, select **Is Null**.  
            
        *   For Value, select **True**.  
            
    *   Make sure Optimize the Flow for is set to **Actions and Related Records**.  
        When you retrieve Data 360 data in a flow, it must be set to Actions and Related Records.  
        
    *   Enable the **Add Asynchronous Path** toggle.  
        This setting enables the flow’s Run Asynchronously path. When you retrieve Data 360 data, it must be in a Run Asynchronously or scheduled path, not in the Run Immediately path.  
        
5.  On the Run Asynchronously path, click ![Add Element](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/access-data-cloud-from-flows/images/13f5207391f198a601856fce8a8a6280_kix.1o8n5ueb9s6s.png).  
    
6.  Select **Get Records**.  
    *   For Label, enter `Get CP EmailCopiar`.  
        
    *   For API Name, enter `Get_CP_EmailCopiar`.  
        
    *   For Data Source, select **Data Cloud Object**.  
        
    *   For Data Space, select **default**.  
        
    *   For Object, select **Contact Point Email**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   In the condition requirement fields:  
        *   For Field, select **Email Address**.  
            
        *   For Operator, select **Equals**.  
            
        *   For Value, select **Triggering Contact**, then select **Email**.  
            
    *   Click **Add Condition** and set these values in the second condition requirement:  
        *   For Field, select **Data Source Object**.  
            
        *   For Operator, select **Equals**.  
            
        *   For Value, enter `External_Guest__cCopiar`.  
            This value tells the Get Records to only retrieve the Contact Point Email record that comes from the external guest data.  
            
    *   Leave the other fields as default.  
        
7.  After the Get CP Email element, click ![Add Element](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/access-data-cloud-from-flows/images/13f5207391f198a601856fce8a8a6280_kix.ooeppwu597m1.png) and add a Decision element.  
    *   For Label, enter `Phone is Blank?Copiar`
    *   For API Name, enter `Phone_is_BlankCopiar`.  
        
    *   In the Outcome Details:  
        *   For Label, enter `YesCopiar`.  
            
        *   For Outcome API Name, enter `YesCopiar`.  
            
        *   For Condition Requirements to Execute Outcome, select **All Conditions Are Met (AND)**.  
            
        *   For Resource, select **Triggering Contact**, then select **Business Phone**.  
            The Business Phone field is usually visible on record pages as “Phone”.  
            
        *   For Operator, select **Is Blank**.  
            
        *   For Value, select **True**.  
            
    *   In the Outcome Order, select **Default Outcome**.  
        *   For Label, enter `NoCopiar`.  
            
8.  On the Yes path, add a Get Records element.  
    *   For Label, enter `Get CP PhoneCopiar`.  
        
    *   For API Name, enter `Get_CP_PhoneCopiar`.  
        
    *   For Data Source, select **Data Cloud Object**.  
        
    *   For Data Space, select **default**.  
        
    *   For Object, select **Contact Point Phone**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   In the condition requirement fields:  
        *   For Field, select **Party**.  
            
        *   For Operator, select **Equals**.  
            
        *   For Value, select **Contact Point Email from Get CP Email**, then select **Party**.  
            
    *   Leave the other fields as default.  
        
9.  After the Get CP Phone element, add an Update Records element.  
    *   For Label, enter `Update Contact External ID and PhoneCopiar`.  
        
    *   For API Name, enter `Update_Contact_External_ID_and_PhoneCopiar`.  
        
    *   For How to Find Records to Update and Set Their Values, select **Use the contact record that triggered the flow**.  
        
    *   Set Field Values:  
        *   Field: **External Id**, Value: **Contact Point Email from Get CP Email** > **Party**  
            
        *   Field: **Business Phone**, Value: **Contact Point Phone from Get CP Phone** > **Formatted E164 Phone Number**  
            
10.  On the No path, add an Update Records element.  
    *   For Label, enter `Update Contact External IDCopiar`.  
        
    *   For API Name, enter `Update_Contact_External_IDCopiar`.  
        
    *   For How to Find Records to Update and Set Their Values, select **Use the contact record that triggered the flow**.  
        
    *   Set Field Values:  
        *   Field: **External Id**, Value: **Contact Point Email from Get CP Email** > **Party**  
            
11.  Save the flow.  
    *   For Flow Label, enter `New Contact - Update External ID and PhoneCopiar`.  
        
12.  Click **Activate** to enable the flow.  
    

![The New Contact Update External ID and Phone flow corresponding to the preceding steps.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/access-data-cloud-from-flows/images/aa68a5c7b21684c2ff1ab4b1882cc6fd_kix.e8cmfhabwmdp.png)

Now when someone creates a contact, Salesforce automatically fills in that External ID field, saving your team time and effort! And with the External ID field consistently filled in, it’s easier to build flows that work with both sets of data. You build more flows that use this field in the next unit.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Because your Data 360Playground doesn’t have data in all of its objects, some of this badge’s exercises and hands-on challenges fail if you run them. Don’t worry, you don’t need to run any of the flows in these exercises or challenges to complete them!

## Resources

*   [_Trailhead_: Customer 360 Data Model for Data Cloud](https://trailhead.salesforce.com/content/learn/modules/customer-360-data-model-for-customer-data-platform)
*   [_Salesforce Help_: Data Model Objects (DMOs)](https://help.salesforce.com/s/articleView?id=data.c360_a_data_model_objects.htm&type=5)
