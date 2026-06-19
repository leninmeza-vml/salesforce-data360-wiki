# Trigger Flows from Data 360

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create a flow that’s triggered by a change to DMO data.  
    
*   Create a flow that’s triggered by a change to a calculated insight’s results.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

We highly recommend that you have a good level of knowledge of flows and Data 360 before you work on this badge. To learn about flows, complete the [Build Flows with Flow Builder](https://trailhead.salesforce.com/content/learn/trails/build-flows-with-flow-builder) trail. To learn about Data 360, complete the [Unlock Your Data with Data Cloud](https://trailhead.salesforce.com/users/strailhead/trailmixes/unlock-your-data-with-data-cloud) trailmix.

Record-triggered flows can be triggered by a change to Salesforce data. Likewise, Data Cloud-triggered flows can be triggered by changes in a data model object (DMO) or calculated insight object (CIO). In other words, you can trigger a flow when the data in a DMO changes, or when a calculated insight’s results change.

## Trigger a Flow from a DMO Data Change

Let’s build a flow that’s triggered by changes in DMO data.

Coral Cloud Resorts store their guest loyalty program information in an external database, and streams it into Data 360 as the External Guest Loyalty object. The hospitality team has started a new concierge program to reach out to guests when they reach the loyalty program’s new Diamond level. Create a flow that sends an email to a guest when the guest reaches the Diamond loyalty level.

1.  From Setup, enter `FlowsCopiar` in the Quick Find box and then click **Flows**.  
    
2.  Click **New Flow**.  
    
3.  Select the **Triggered** category.  
    ![The New Automation window with the Triggered category highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/trigger-flows-from-data-cloud/images/b2362199dd41af92f4be5170db8c479b_kix.rkh3gn1hlm9x.png)  
    
4.  Select **Data Cloud-Triggered Flow**.  
    
5.  In the Start element’s configuration panel:  
    *   For Data Space, select **default**.  
        
    *   For Object, select **External\_Guest\_Loyalty\_\_c\_Home**.  
        
    *   For Trigger the Flow When, select **A record is updated**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **Loyalty\_Level\_c\_\_c**.  
        
    *   For Operator, select **Equals**.  
        
    *   For Value, enter `DiamondCopiar`.  
        
    *   For When to Run the Flow for Updated Records, select **Only when a record is updated to meet the condition requirements**.  
        

### Collect Data and Send the Email

Create a Get Records element to get information from the guest’s Contact record. With that data, you can create an action that sends the email to the guest.

1.  Add a Get Records element.  
    *   For Label, enter `Get ContactCopiar`.  
        
    *   For API Name, enter `Get_ContactCopiar`.  
        
    *   For Data Source, select **Salesforce Object**.  
        
    *   For Object, select **Contact**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **External Id**.  
        
    *   For Operator, select **Equals**.  
        
    *   For Value, select **Triggering External\_Guest\_Loyalty\_c\_Home\_\_dlm** > **Guest ID**.  
        
    *   Leave the other fields as default.  
        
2.  After the Get Contact element, add an Action element.  
    *   In the Search field, enter `emailCopiar`, then select **Send Email**.  
        
    *   For Label, enter `Send Email to GuestCopiar`.  
        
    *   For API Name, enter `Send_Email_to_GuestCopiar`.  
        
    *   For Subject, enter `Welcome to Diamond level!Copiar`  
        
    *   In the Body field, change **View as Rich Text** to **View as Plain Text**.  
        
    *   For Body, enter this text:  
        `Congratulations {!Get_Contact.Name}, you're our newest guest to reach our esteemed Diamond level! Your dedicated concierge will contact you this week to discuss the benefits of your Diamond membership.Copiar`  
        
    *   For Recipient ID, select **Contact from Get Contact** > **Contact ID**.  
        
3.  Save the flow.  
    *   For Flow Label, enter `New Diamond Level GuestCopiar`.  
        
4.  Click **Activate**.  
    

![The New Diamond Level Guest flow corresponding to the preceding steps.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/trigger-flows-from-data-cloud/images/1c5b80d8a6e52d8cbe4c42b30ee2d339_kix.vemt7o9fptvw.png)

This is obviously a very basic email and probably shouldn’t be sent to an actual customer. Use merge fields, email templates, and rich text to create more professional emails for your customers.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Because your Data 360Playground doesn’t have data in all of its objects, some of this badge’s exercises and hands-on challenges fail if you run them. Don’t worry, you don’t need to run any of the flows in these exercises or challenges to complete them! Feel free to add your own data and test the flows with that data.

## Trigger a Flow from a CIO Data Change

Now let’s build a flow that’s triggered by changes in a calculated insight’s results.

Coral Cloud Resorts recently created an ecommerce site for guests to quickly purchase additional experiences from their rooms, but a lot of guests have been leaving selected experiences unpurchased, abandoning the shopping cart.

Because this is a growing problem, the ecommerce team keeps track of each time a guest leaves a cart abandoned for 24 hours, storing each incident in an external database. That database is available in Data 360 as the External Abandoned Cart object.

A case should be assigned to the hospitality team when a guest does this three times within a span of two weeks, so the hospitality team can follow-up directly. You’ve already created the Number of Abandoned Carts calculated insight to track the number of times a guest abandons a cart. Now create a flow that’s triggered when the NumberOfAbandons value in that calculated insight is 3 or more.

1.  Create a Data Cloud-Triggered flow.  
    
2.  In the Start element’s configuration panel:  
    *   For Data Space, select **default**.  
        
    *   For Object, select **Number of Abandoned Carts**.  
        
    *   For Trigger the Flow When, select **A record is updated**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **NumberOfAbandons\_\_c**.  
        
    *   For Operator, select **Greater Than or Equal**.  
        
    *   For Value, enter `3Copiar`.  
        
    *   For When to Run the Flow for Updated Records, select **Only when a record is updated to meet the condition requirements**.  
        

### Get Records

Add some Get Records elements to retrieve the guest’s Contact record, the information from their most recent Abandoned Cart record, and the ID of the Hospitality Upsells queue.

1.  Add a Get Records element.  
    *   For Label, enter `Get ContactCopiar`.  
        
    *   For API Name, enter `Get_ContactCopiar`.  
        
    *   For Data Source, select **Salesforce Object**.  
        
    *   For Object, select **Contact**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **External Id**.  
        
    *   For Operator, select **Equals**.  
        
    *   For Value, select **Triggering Number\_of\_Abandoned\_Carts1\_\_cio** > **CartGuestID**.  
        
    *   Leave the other fields as default.  
        
2.  After the Get Contact element, add another Get Records element.  
    *   For Label, enter `Get External Abandoned CartCopiar`.  
        
    *   For API Name, enter `Get_External_Abandoned_CartCopiar`.  
        
    *   For Data Source, select **Data Cloud Object**.  
        
    *   For Data Space, select **default**.  
        
    *   For Object, select **External\_Abandoned\_Cart\_\_c\_Home**.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **Guest ID**.  
        
    *   For Operator, select **Equals**.  
        
    *   For Value, select **Triggering Number\_of\_Abandoned\_Carts1\_\_cio** \> **CartGuestID**.  
        
    *   For Sort Order, select **Descending**.  
        
    *   For Sort By, **CreatedDate\_\_c**.  
        These Sort Records field values ensure that the flow saves the most recently created External Abandoned Cart record.  
        
    *   Leave the other fields as default.  
        
3.  After the Get External Abandoned Cart record, add one more Get Records element.  
    *   For Label, enter `Get QueueCopiar`.  
        
    *   For API Name, enter `Get_QueueCopiar`.  
        
    *   For Data Source, select **Salesforce Object**.  
        
    *   For Object, select **Group**.  
        Make sure you select the Group object whose API Name is “Group”, _not_ “CollaborationGroup”.  
        
    *   For Condition Requirements, select **All Conditions Are Met (AND)**.  
        
    *   For Field, select **Developer Name**.  
        
    *   For Operator, select **Equals**.  
        
    *   For Value, enter `Hospitality_UpsellsCopiar`.  
        
    *   Leave the other fields as default.  
        

### Create a Case

The case needs important details about the most recent abandoned cart, so create a text template that collects those details. Finally, add an element that uses the info collected earlier in the flow to create a case.

1.  Add a text template resource.  
    *   For API Name, enter `CaseDescriptionTemplateCopiar`.  
        
    *   Change the **View as Rich Text** setting to **View as Plain Text**.  
        
    *   For Body, enter the following text:  
        
        This guest has abandoned their add-ons shopping cart {!$Record.NumberOfAbandons\_\_c} times in the past two weeks. Please reach out and attempt to close the sale. Most recent abandoned cart: {!Get\_External\_Abandoned\_Cart.CreatedDate\_\_c} - ${!Get\_External\_Abandoned\_Cart.Cart\_Value\_c\_\_c} Products in cart: {!Get\_External\_Abandoned\_Cart.Product\_List\_c\_\_c}
        
    *   Click **Done**.  
        
2.  After the Get Queue element, add a Create Records element.  
    *   For Label, enter `Create CaseCopiar`.  
        
    *   For API Name, enter `Create_CaseCopiar`.  
        
    *   For How to set record field values, select **Manually**.  
        
    *   For Object, select **Case**.  
        
    *   Set Field Values:  
        *   Field: **Contact ID**, Value: **Contact from Get Contact > Contact ID**  
            
        *   Field: **Description**, Value: **CaseDescriptionTemplate**  
            
        *   Field: **Owner ID**, Value: **Group from Get Queue > Group ID**  
            
        *   Field: **Priority**, Value: **High**  
            
        *   Field: **Status**, Value: **New**  
            
        *   Field: **Subject**, Value: `Abandoned Cart Follow-Up - {!Get_Contact.External_Id__c}Copiar`  
            This value sets the case’s subject as `Abandoned Cart Follow-UpCopiar` followed by the contact’s External Id field.  
            
3.  Save the flow.  
    *   For Flow Label, enter `Create Case After 3 Abandoned CartsCopiar`.  
        
4.  Click **Activate**.  
    

![The Create Case After 3 Abandoned Carts flow corresponding to the preceding steps.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/trigger-flows-from-data-cloud/images/518e1ca689af7b3b66658d4d38e845b4_kix.9d27xs4dil22.png)

Now when the Number of Abandoned Carts calculated insight recalculates its values, the flow runs. On the calculated insight’s page, you can click **Publish Now** to run the calculations, or **Schedule** to run the calculation at a set interval of time. You can do the same for any calculated insight in your Data 360 installation.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

To trigger a flow from other types of insights, such as streaming insights, see [Data Actions in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_actions_CDP.htm&type=5).

## Resources

*   [_Trailhead_: Data Cloud Insights](https://trailhead.salesforce.com/content/learn/modules/customer-data-platform-insights)
*   [_Trailhead_: Enhance Data in Data Cloud](https://trailhead.salesforce.com/content/learn/trails/enhance-data-in-customer-data-platform)
*   ​​[_Salesforce Help_: Calculated Insights](https://help.salesforce.com/s/articleView?id=data.c360_a_calculated_insights.htm&type=5)

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Cancel Booked Experiences When a Reservation is Canceled

In Coral Cloud's data infrastructure, guests’ scheduled activities are stored in the Bookings object in Salesforce, but the reservations for their stays are stored in an external database. The reservation database is connected to their Salesforce org by Data 360.  
  
Create a flow that runs when an external reservation is canceled. The flow should cancel all of that guest’s Booking records that take place during the canceled reservation.  
  
**Prework**  
If you haven’t completed unit 1, do that now. Otherwise, you won't be able to complete this challenge.  
  
**Requirements**  

*   Create a Data 360-triggered flow:
    
    *   Data Space: **default**
    *   Object: **External\_Reservation\_\_c\_Home**
    *   Trigger the Flow When: **A record is updated**
    *   Condition Requirements: **All Conditions Are Met (AND)**
    *   Field: **Reservation Status**
    *   Operator: **Equals**
    *   Value: `CanceledCopiar`
    *   When to Run the Flow for Updated Records: **Only when a record is updated to meet the condition requirements**
    
    - - -
    
*   Add a Get Records element:
    
    *   Label: `Get ContactCopiar`
    *   API Name: `Get_ContactCopiar`
    *   Data Source: **Salesforce Object**
    *   Object: **Contact**
    *   Condition Requirements: **All Conditions Are Met (AND)**
    *   Field: **External Id**
    *   Operator: **Equals**
    *   Value: **Triggering External\_Reservation\_\_c\_Home > Guest ID**
    *   Leave other fields as default
    
    - - -
    
*   After the Get Contact element, add a Get Records element:
    
    *   Label: `Get BookingsCopiar`
    *   API Name: `Get_BookingsCopiar`
    *   Data Source: **Salesforce Object**
    *   Object: **Booking**
    *   Condition Requirements: **All Conditions Are Met (AND)**
    *   Define a condition requirement:
        *   Field: **Contact**
        *   Operator: **Equals**
        *   Value: **Contact from Get Contact > Contact ID**
    *   Add another condition requirement:
        *   Field: **Date**
        *   Operator: **Greater Than or Equal**
        *   Value: **Triggering External\_Reservation\_\_c\_Home > Check-in Date**
    *   Add another condition requirement:
        *   Field: **Date**
        *   Operator: **Less Than or Equal**
        *   Value: **Triggering External\_Reservation\_\_c\_Home > Check-out Date**
    *   How Many Records to Store: **All records**
    *   Leave other fields as default
    
    - - -
    
*   After the Get Bookings element, add a Loop element:
    
    *   Label: `BookingsLoopCopiar`
    *   API Name: `BookingsLoopCopiar`
    *   Collection Variable: **Bookings from Get Bookings**
    
    - - -
    
*   Add a variable:
    
    *   API Name: `CanceledBookingsCopiar`
    *   Data Type: **Record**
    *   Allow multiple values (collection): _checked_
    *   Object: **Booking**
    
    - - -
    
*   On the For Each path, add an assignment element:
    
    *   Label: `Set Is Canceled to TrueCopiar`
    *   API Name: `Set_Is_Canceled_to_TrueCopiar`
    *   First variable:
        *   Variable: **Current Item from Loop BookingsLoop > Is Canceled**
        *   Operator: **Equals**
        *   Value: **True**
    *   Click **Add Assignment** to create a second variable:
        *   Variable: **CanceledBookings**
        *   Operator: **Add**
        *   Value: **Current Item from Loop BookingsLoop** > **Entire Resource**
    
    - - -
    
*   On the After Last path, add an Update Records element:
    
    *   Label: `Cancel BookingsCopiar`
    *   API Name: `Cancel_BookingsCopiar`
    *   How to Find Records to Update and Set Their Values: **Use the IDs and all field values from a record or record collection**
    *   Record or Record Collection: **CanceledBookings**
    
    - - -
    
*   Save the flow.
    *   Flow Label: `Reservation Canceled - Cancel BookingsCopiar`
    *   API Name: `Reservation_Canceled_Cancel_BookingsCopiar`

Aquí está la guía completa para el reto:

---

# Guía: Cancelar Bookings cuando se Cancela una Reservación

## Paso 1 — Crear el Data Cloud-Triggered Flow

1. En Setup busca **"Flows"** → clic en **"New Flow"**
2. Selecciona la categoría **"Triggered"**
3. Selecciona **"Data Cloud-Triggered Flow"**
4. Configura el Start element:
   - Data Space: **default**
   - Object: **External_Reservation__c_Home**
   - Trigger the Flow When: **A record is updated**
   - Condition Requirements: **All Conditions Are Met (AND)**
   - Field: `Reservation Status` | Operator: `Equals` | Value: `Canceled`
   - When to Run: **Only when a record is updated to meet the condition requirements**

---

## Paso 2 — Get Contact

1. Haz clic en **"+"** → selecciona **"Get Records"**
2. Configura:
   - Label: `Get Contact`
   - API Name: `Get_Contact`
   - Data Source: **Salesforce Object**
   - Object: **Contact**
   - Condition Requirements: **All Conditions Are Met (AND)**
   - Field: `External Id` | Operator: `Equals` | Value: `Triggering External_Reservation__c_Home > Guest ID`
3. Deja los demás valores por defecto

---

## Paso 3 — Get Bookings

1. Haz clic en **"+"** → selecciona **"Get Records"**
2. Configura:
   - Label: `Get Bookings`
   - API Name: `Get_Bookings`
   - Data Source: **Salesforce Object**
   - Object: **Booking**
   - Condition Requirements: **All Conditions Are Met (AND)**
3. Define estas 3 condiciones:

| Field | Operator | Value |
|---|---|---|
| `Contact` | `Equals` | `Contact from Get Contact > Contact ID` |
| `Date` | `Greater Than or Equal` | `Triggering External_Reservation__c_Home > Check-in Date` |
| `Date` | `Less Than or Equal` | `Triggering External_Reservation__c_Home > Check-out Date` |

4. How Many Records to Store: **All records**
5. Deja los demás valores por defecto

---

## Paso 4 — Crear la variable CanceledBookings

1. En Toolbox → **"New Resource"**
2. Configura:
   - Resource Type: **Variable**
   - API Name: `CanceledBookings`
   - Data Type: **Record**
   - ✅ Marca **"Allow multiple values (collection)"**
   - Object: **Booking**
3. Clic en **"Done"**

---

## Paso 5 — Loop Element

1. Haz clic en **"+"** → selecciona **"Loop"**
2. Configura:
   - Label: `BookingsLoop`
   - API Name: `BookingsLoop`
   - Collection Variable: **Bookings from Get Bookings**

---

## Paso 6 — Assignment (path "For Each")

1. En el path **"For Each"** haz clic en **"+"** → selecciona **"Assignment"**
2. Configura:
   - Label: `Set Is Canceled to True`
   - API Name: `Set_Is_Canceled_to_True`
3. Primera asignación:
   - Variable: `Current Item from Loop BookingsLoop > Is Canceled`
   - Operator: **Equals**
   - Value: **True**
4. Haz clic en **"Add Assignment"** para la segunda:
   - Variable: `CanceledBookings`
   - Operator: **Add**
   - Value: `Current Item from Loop BookingsLoop > Entire Resource`
5. Clic en **"Done"**

---

## Paso 7 — Update Records (path "After Last")

1. En el path **"After Last"** haz clic en **"+"** → selecciona **"Update Records"**
2. Configura:
   - Label: `Cancel Bookings`
   - API Name: `Cancel_Bookings`
   - How to Find Records to Update: **Use the IDs and all field values from a record or record collection**
   - Record or Record Collection: **CanceledBookings**
3. Clic en **"Done"**

---

## Paso 8 — Guardar y Activar

1. Haz clic en **"Save"**
2. Flow Label: `Reservation Canceled - Cancel Bookings`
3. API Name: `Reservation_Canceled_Cancel_Bookings`
4. Clic en **"Save"**
5. Clic en **"Activate"**

---

## Paso 9 — Verificar en Trailhead

Regresa a Trailhead y haz clic en **"Check Challenge"** para ganar los **500 puntos**. 🎉

---

> ⚠️ **Recuerda:** No necesitas ejecutar el flow para completar el reto. Solo necesita estar creado y activado correctamente.