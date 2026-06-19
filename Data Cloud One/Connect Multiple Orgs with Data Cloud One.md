Connect Multiple Orgs with Data Cloud One
=========================================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Identify Data Cloud One benefits.  
*   Learn Data Cloud One best practices and use cases.  
*   Explain next steps for getting started with Data Cloud One.  
    

What’s Data Cloud One?
----------------------

With Data 360, your business can ‌unlock trapped data from external systems, deliver more personalized customer experiences, and power enterprise AI. But what if you could get even more value from Data 360?

As your company grows, your business needs grow as well. Your company might start with just one org, a virtual space that contains Salesforce data and applications. But as time passes, you might create many different Salesforce orgs for different departments, regions, or brands, or inherit them as part of an acquisition. And data about the same customer can end up being stored in multiple orgs. It’s great to have all that data, but it’s more valuable if every part of your business can access a single view of each customer.

Without Data Cloud One, you could use standard Salesforce CRM connections to ingest data from many orgs into Data 360. But connected orgs can’t directly access that unified data, unless you set up complicated custom-coded solutions with Apex and Flows. Or you have to provision, set up, and maintain a Data 360 on every org. That sounds time-consuming and expensive!

Data Cloud One can make the multi-org management experience better.

Benefits of Data Cloud One
--------------------------

Data Cloud One makes accessing a single view of Data 360 across multiple orgs a snap. With Data Cloud One, users in connected orgs, called companion orgs, can easily access unified data and many Data 360–powered features through the Data Cloud One app. Companion org users can see a complete view of their customers with unified profiles, build custom flows on unified data, directly access calculated insights, and optimize business processes for their use case.

By implementing Data Cloud One, you can:

*   **Streamline multi-org architectur​​e:** Easily connect multiple Salesforce orgs with one central Data 360, unifying Salesforce, and external data.  
    
*   **Implement Data 360 faster:** Share your Data 360 data with multiple Salesforce orgs using metadata sync and no-code point-and-click setup.  
    
*   **Collaborate across orgs:** Share Data 360 objects and insights across orgs, eliminating duplicative efforts.  
    

Improve the Customer Experience with Data Cloud One
---------------------------------------------------

Northern Trail Outfitters (NTO) is a major retailer with multiple brands and departments. NTO is passionate about creating the perfect customer experience, and to do so, NTO unifies its external data with Data 360.

NTO is a big organization with many Salesforce orgs. NTO has one for every department of the company—including Sales, Marketing, Operations, and even more. Each of these orgs has its own data, its own configurations, and its own customizations. Getting cross-org insights on NTO’s customers gets gnarly pretty quickly.

NTO already has an org with Data 360, but unfortunately, it doesn’t have Data Cloud One. This means its Data 360 org can ingest data from its other Salesforce orgs, but those orgs have a hard time accessing that unified data. How can all of NTO’s Salesforce orgs get access to the data in Data 360?

What NTO is looking for is a multi-org architecture strategy—a way to organize all of its orgs to work best together. Time to walk through the different ways NTO could set up a multi-org architecture.

Multi-Org Architecture Without Data Cloud One
---------------------------------------------

Without Data Cloud One, NTO has two options for a multi-org architecture: the DIY route, and the multiple Data 360s route.

![Corresponding diagram of DIY and multiple Data 360s architectures.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-one-quick-look/connect-multiple-orgs-with-data-cloud-one/images/97b17f15398c75d818836b54519d8459_kix.k7czkalfc7zk.png)

The DIY route uses cross-org actions and queries. This involves using custom Apex code, data actions, and Flows to send data from your Data 360 org to your Salesforce orgs. But this is time-consuming and expensive—NTO would likely have to hire a full-time, dedicated team to maintain this architecture. Even worse is that it doesn’t scale well. For a growing business like NTO, where needs can vary greatly year to year, this code would likely need to be overhauled all the time to keep up. Or NTO might end up accumulating tons of technical debt that drags its productivity and agility down.

The multiple Data 360s route involves setting up multiple Data 360s, each to handle a different business purpose. So NTO could set up a Data 360 for every single department. If NTO is concerned about data residency, it could be good to have a separate Data 360 for each region NTO stores its data in. But this is also complex and expensive to maintain, and even creates data silos—it’s harder than ever to create that one source of truth.

Luckily for NTO, there’s Data Cloud One.

Data Cloud One Streamlines Multi-Org Architecture
-------------------------------------------------

![Corresponding diagram of the Data Cloud One architecture.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-one-quick-look/connect-multiple-orgs-with-data-cloud-one/images/ab938b4adee25f90c4530a1060199f59_kix.9l8ndwhq3lk.png)

With Data Cloud One, you can simplify how you connect Data 360 to your Salesforce orgs.

Data Cloud One allows you to bidirectionally connect your Salesforce orgs to Data 360. So Salesforce orgs that used to only send out data to Data 360 can now easily access that unified data, and also use some Data 360–powered features.

Here are some important terms to know about Data Cloud One.

#### Standard Salesforce CRM Connector

This connects Data 360 to a Salesforce org and enables Data 360 to ingest data and send back data actions. Standard connections don’t sync metadata back to connected orgs and don’t give connected orgs access to Data 360 features or data. You can’t set up features powered by Data 360 if your org is connected to Data 360 only via a standard connection.

#### Data 360 Home Org

This is the Salesforce organization that Data 360 is provisioned on. It’s the central hub where all your data is ingested and stored, and serves as the single source of truth for your unified Customer 360 view.

#### Data Space

A data space is a logical partition within Data 360 to organize your data for profile unification, insights, and marketing efforts. You can select which data spaces you choose to share with your companion orgs. Only the metadata for these objects is shared across connected orgs. Learn more about data spaces in the [Data Spaces in Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/data-spaces-in-data-cloud-quick-look) module, or in the [Data 360 Video Series: Data Spaces](https://salesforcedatacloud.hubs.vidyard.com/watch/EfZ47u81CogN9N6LSabeQq) video.

#### Companion Connection

This is a bridge that links companion orgs to the home org, enabling metadata sharing for the data spaces you choose to share.

#### Companion Org

Any org that is connected to a home org via a companion connection is a companion org. Users in companion orgs have access to a subset of Data 360 functionality in the Data Cloud One app. Data 360 data is available in companion orgs to power platform features like Flow and Enrichments.

#### Data Cloud One App

The Data Cloud One app is available on any companion org. The Data Cloud One app gives users on the companion org access to some Data 360 features. Not all Data 360 features are accessible in Data Cloud One.

![An example of the Data Cloud One App user interface.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-one-quick-look/connect-multiple-orgs-with-data-cloud-one/images/19663d30e41dbeff72621600cdced533_kix.hdtoamukh422.png)

Set Up Data Cloud One
---------------------

In the next unit, see how Northern Trail Outfitters can use and get started with Data Cloud One.

Resources
---------

*   [_Salesforce Help_: Connect Salesforce CRM Orgs to Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_connect_salesforce_orgs.htm&type=5)
*   [_Salesforce Help_: Data Cloud One Companion Connections](https://help.salesforce.com/s/articleView?id=data.c360_a_companion_connections.htm&type=5)
*   ​[_Salesforce Help_: Data 360 Architecture Strategy](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud_architecture_strategy.htm&type=5)
*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)
*   ​​[_Salesforce Help_: Compare Standard Salesforce CRM and Data Cloud One Companion Connections](https://help.salesforce.com/s/articleView?id=data.c360_a_compare_salesforce_connections.htm&type=5)

Prueba
------

Para completar esta unidad, debe responder correctamente todas las preguntas de la prueba.

1 Without Data Cloud One, what is one way you can have a multi-org architecture?
A) Download all the data from every org locally.
B) Upload all your data to a public repository.
C) Create custom Apex code, data actions, and Flows. *
D) Disconnect all your Salesforce orgs.

2 What is the term for a Salesforce org that isn’t provisioned with its own Data 360, but is bidirectionally connected to Data 360 on a different home org?
A) Companion org *
B) Standard org
C) Data space org
D) Home org
