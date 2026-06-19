Superbadge: Data Stream Fundamentals
------------------------------------

### Lo que tendrá que hacer para ganar esta Superbadge

1.  Configure a data stream from a bundle.
2.  Create a custom formula field.
3.  Add to the data model object (DMO).

### Conceptos puestos a prueba en esta Superbadge

*   Data Stream
*   Data Model

### [](#superbadge-intro)Introduction to Superbadges

Heads-up! A **superbadge** is different from other learning on Trailhead. It's a hands-on technical skills assessment where you take business requirements and apply your skills to build something amazing, without the step-by-step guidance. We have provided recommended learning and Help articles filled with resources to aid you along your journey. The estimated completion time assumes prior experience with the superbadge concepts and completion of the recommended learning. Your hard work will pay off!

![](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Note

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

  

### [](#prework-and-notes)Prework and Notes

#### Sign Up for a Developer Edition Org with Special Configuration

To complete this superbadge, you need a special Developer Edition org that contains special configuration and sample data. Note that this Developer Edition org is designed to work with the challenges in this superbadge.

1.  Sign up for a free 2-day [Developer Edition org with special configuration](https://orgfarm.salesforce.com/signup?type=superBadge&badge=DSFSU) and Data 360.
    
2.  Fill out the form. For Email address, enter an active email address where you can receive the email confirmation for the new account.
    
3.  After you fill out the form, click **Submit**. A confirmation message appears.
4.  When you receive the activation email (this might take a few minutes), open it and click the link to reset your password.
    
5.  Complete your registration by setting your password and challenge question. Tip: Save your username, password, and login URL in a secure place—such as a password manager—for easy access later.
    
6.  You are logged in to your superbadge Developer Edition org.
    

Now, connect your new Developer Edition org to Trailhead.

1.  Make sure you’re logged in to your Trailhead account.
    
2.  In the Challenge section at the bottom of this page, select **Connect Org** from the picklist.
    
3.  On the login screen, enter the username and password for the Developer Edition org you just set up.
    
4.  On the Allow Access? page, click **Allow**.
    
5.  On the Want to connect this org for hands-on challenges? page, click **Yes! Save it**. You are redirected back to the Challenge page and ready to use your new Developer Edition org to earn this superbadge.
    
6.  Now that you have a Salesforce org with special configuration for this superbadge, you’re good to go.
    

This superbadge requires access to a special Developer Edition org that includes Data 360. These Developer Edition orgs are only available for a 2-day period, so **be sure to complete this superbadge before your org expires.**

  

![](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Note

Before you begin the challenges, please review [Data Stream Fundamentals Superbadge: Trailhead Challenge Help](https://trailhead.salesforce.com/en/help?article=Data-Stream-Fundamentals-Superbadge-Unit-Trailhead-Challenge-Help).

**Make sure you’re using a new Developer Edition org from [this sign up link](https://orgfarm.salesforce.com/signup?type=superBadge&badge=DSFSU) to complete the challenges in this superbadge.** If you use an org that has been used for other work, you won’t pass the challenges in this superbadge.

### [](#use-case)Use Case

Codey's Den & Breakfast (CDB), a popular travel destination in the United States of America for families from all over the world, leverages Salesforce to provide each guest with an enjoyable and unforgettable stay. Guests are drawn to Codey's for the soft, comfy beds and the delicious pancakes and waffles every morning, but what keeps them coming back is Codey's commitment to hospitality that's customized for every visitor.

That's where Salesforce Data 360 comes in! CDB is just getting started with Data 360, and is excited about using it to ensure:

*   **Comprehensive guest profiles.** Salesforce Data 360 consolidates guest data from various sources into a single Customer 360 view. This unified profile includes booking history, preferences, feedback, and interactions, allowing Codey’s to tailor services to each guest’s unique needs.
*   **Targeted marketing campaigns.** With detailed insights into guest preferences and behaviors, CDB can create compelling, customized marketing campaigns. For example, international guests who tend to prefer extended stays can receive tailored promotions for long-term visits. The same idea applies to guests who are likely to be interested in cultural tours, outdoor adventures, and local attractions.
*   **Data-driven decision making.** Thanks to Data 360, Codey's can easily identify trends and patterns by analyzing guest data. These insights will allow them to invest wisely in progams that will have the greatest impact for their visitors.

Just as we all know that a bed and breakfast should always have clean towels and extra blankets at the ready, we also know that a good marketing strategy includes personalization. CDB is ready to implement a marketing strategy specifically for international guests. This will allow it to develop services, amenities, and marketing initiatives that might be appealing to guests from other countries, such as specific dietary options or cultural activities. Codey's Den & Breakfast has tasked you, their admin for Data 360, with preparing a strategy for identifying global visitors to enable customized marketing campaigns and benefit from unified data. Once it’s completed, CDB will be able to efficiently and more effectively reach out to these important potential guests.

### [](#business-requirements)Business Requirements

As the admin for Data 360, you’re already equipped with the knowledge to optimize guest experiences. By putting the power of Salesforce solutions to work, you can help CDB to not only maintain its popularity with travelers but also improve visits with customized promotions and experiences.

To get started, you’ll identify and consolidate international contacts into the CDB Customer 360 data model. This will help the company provide personalized services and, ultimately, more memorable experiences—all tailored to the unique preferences and needs of diverse, global guests. You'll use data streams to consolidate and analyze guest data, which will allow for dynamic updates to guest profiles, ensuring that all interactions and preferences are up-to-date. Data streams provide a comprehensive view of each specific traveler, enabling personalized service and timely, relevant communications.

#### [](#Connect-the-Sales-Data-Stream-Bundle)Connect the Sales Data Stream Bundle

Before CDB can receive data into its org with Data 360, its data streams need to be properly configured. Fortunately, the Salesforce Platform admin team has already enabled Data 360 in the org, with the standard Data 360 bundles for Sales and Service. First things first: Make sure the standard data bundle for **Sales** is connected, so that you can enable the flow of critical profile data into Salesforce Data 360, integrating it seamlessly with other data streams.

The Sales Data Stream Bundle is a powerful tool that focuses on profile data, helping Codey's collect, analyze, and use guest-related information to optimize its operations and enhance guest experiences. CDB can now use data effectively to anticipate guest needs and cater to their visitors from all over the world.

![](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Note

The data streams usually ingest the sample records quickly, so you shouldn’t have to wait long. However, occasionally it may take up to 15 minutes for the Last Run Status to show "Success." Be sure to wait for that to be complete before starting the next challenge.

Great work! You've taken the first step toward configuring data streams, which will support CDB’s effort to consolidate and analyze guest data. There are so many ways this data unification can be used, but for now we'll keep focusing on Codey's international guests.

#### [](#Create-a-Custom-Formula)Create a Custom Formula

Now that the data streams are ready, we can start making use of the data by implementing a way to consistently identify international contacts. Create a formula field that will distinguish international guests from domestic ones, so that CDB can tailor communication, anticipate language preferences, and address potential cultural considerations. Use the field label **International Contact** for the new field in the **Contact Data Stream**, and make sure your formula returns true if the contact's `Mailing CountryCopiar` is not **USA**. While we won't check for the exact formula you use, be sure to test it out to make sure it's returing the expected results. Tip: If you get stuck, check out the [Help article](https://trailhead.salesforce.com/en/help?article=Data-Stream-Fundamentals-Superbadge-Unit-Trailhead-Challenge-Help) for some suggested formulas.

Now that we have a way to identify international contacts, CDB's guest data is becoming more and more useful.

#### [](#Add-to-the-Data-Model-Object)Add to the Data Model Object

It's time to put it all together! Codey's Den & Breakfast plans to create an email campaign targeting international guests as part of its marketing strategy. You'll lay the groundwork for this by adding the **International Contact** field in the CDB contact data stream to the **Account Contact** data model object (DMO), for use in Data 360.

*   Field Label: **International Contact**
*   API Name: `International_ContactCopiar`
*   Usage: This field will be used to segment the guest database and create targeted marketing campaigns for international travelers.

Now that CDB can quickly and consistently identify international guests, it will be able to ensure more accurate, efficient, and personalized communication and service, enhancing the overall guest experience and fostering long-term loyalty.

#### [](#Sum-It-Up)Sum It Up

As the admin for Data 360, you know that Codey's Den & Breakfast is just getting started reaping the rewards of using Data 360—in the future, you can map more fields, bring together data from more sources, and use historical data to visualize and identify preferences and trends among international travelers. You can also develop special packages and offers customized for long-stay guests, and personalize email campaigns and mobile app notifications to promote those tailored offers. The possibilities are endless!

CDB enjoys being a popular destination in its region, and it’s doubling down on its success by investing in ways to make better use of all that guest information. No matter where guests call home, Codey's is a welcome respite for all, and its commitment to personalized service—powered by Data 360—makes it a bed and breakfast of choice for guests from all over the world.

#### Complete each challenge to earn your superbadge

Challenge Not yet complete... here's what's wrong:  
We can't find the special settings preinstalled in this org. Make sure to use a special org made for this superbadge and linked in the scenario above.

1 Connect the Sales Data Stream Bundle
Set up the Sales data stream standard bundle.

For more guidance, refer to the [Help article](https://trailhead.salesforce.com/en/help?article=Data-Stream-Fundamentals-Superbadge-Unit-Trailhead-Challenge-Help).

2 Create a Custom Formula
Create a custom formula field for international contacts.

For more guidance, refer to the [Help article](https://trailhead.salesforce.com/en/help?article=Data-Stream-Fundamentals-Superbadge-Unit-Trailhead-Challenge-Help).

3 Add to the Data Model Object
Add the International Contact field to the DMO.

For more guidance, refer to the [Help article](https://trailhead.salesforce.com/en/help?article=Data-Stream-Fundamentals-Superbadge-Unit-Trailhead-Challenge-Help).
