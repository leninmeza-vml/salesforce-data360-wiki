# Craft Effective Advertising with Data 360

## Learning Objectives

After completing this unit, you’ll be able to:

*   Build an advertising plan with Data 360 features.  
    
*   Identify stakeholders for your advertising strategy.  
    
*   Use Data 360 to implement an advertising use case.  
    

## Introduction

In this unit, you follow along with Northern Trail Outfitters (NTO) as they build an advertising plan and implement it with Data 360.

NTO is a retail company that sells outdoor and recreational gear. They’re committed to a highly personalized experience for each customer, which includes their marketing. Isabel Givens, the manager of digital marketing at NTO, is all about marketing with first-party data. She’s been using Data 360 for a few feature rollouts now, and she and her team have a solid advertising strategy built around Data 360.

![Meet Isabel Givens, the manager of digital marketing at NTO.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/advertising-with-data-cloud/craft-effective-advertising-with-data-cloud/images/5c1987dc5c3826ddb251576c75957ade_kix.gmtfzxa2bre5.png)

## NTO’s Advertising Plan

NTO is preparing to roll out new models of its most popular camping equipment. Everyone at NTO is excited about the new models, and they want to make sure that as many customers as possible, new and old, know about and purchase the equipment. Isabel and her team draw up an advertising plan.

1.  **Reach new customers with lookalike audiences.** Isabel and her team want to grow their customer base with this new model. They know who bought the last model in their camping line. These are their customers who are most likely to buy the new models, or their best customers. They use Data 360 features such as Calculated Insights to understand the traits of their best customers. Then they create a segment of their best customers and activate it to an advertising platform, such as Meta and Google Ads. In the advertising platform, they use lookalike modeling to find new audiences similar to their existing customers, and include these new audiences in their advertising campaign.  
    

2.  **Target interested customers to increase conversion and decrease costs.** Isabel and her team also want to make sure their existing customers know about the rollout. But a general campaign that gets sent to everyone wastes money and is less effective. Isabel wants to use targeted ads that only get sent to customers that meet a certain criteria. For example, Isabel creates a segment that includes customers who recently searched for camping equipment on their website. These users have a demonstrated interest and are much more likely to buy than a customer who only searches for soccer equipment. Isabel and her team target this audience with ads to increase conversions and decrease costs.  
    

3.  **Suppress certain customers to prevent churn.** Isabel’s team also wants to exclude, or suppress, certain customers from their campaign. Suppression is an advertising strategy where you exclude certain customers from seeing your ad to save money and avoid sending unwanted messages. Isabel’s team knows from previous campaigns that when they send ads to customers with open service cases, it increases the chance that these customers churn, or stop buying altogether. The last thing an irritated customer wants to see is more ads. They decide to suppress all customers with open service cases. They can do this by creating a segment that they exclude from the campaign.  
    

4.  **Optimize with insights.** After launching their campaign, Isabel and her team plan to use Calculated Insights, Google insights, and Amazon Marketing Cloud insights to further optimize their campaign. For example, Google’s report tells them what categories the members of their segment also belong to. Most of Isabel’s segment members might also be interested in fishing. Isabel can edit her segment to include fishing enthusiasts and reach more people who are interested in NTO’s products.  
    

5.  **Improve campaign performance with Meta Conversions API (CAPI).** CAPI sends first-party data about customer engagement, collected from NTO’s website, to Meta. Meta uses that data to improve ad targeting, lower acquisition costs, and more accurately measure campaign outcomes. For example, for lookalike audiences, Meta can optimize its seed audience using the new engagement data and find lookalike audiences that are most likely to convert.  
    

After figuring out their plan, Isabel and her team still have one more step before they can start implementing: Identify stakeholders.

## Identify Project Stakeholders

Isabel’s advertising project needs some key stakeholders on board. These are people who have an interest, influence, or impact on the project.

Isabel reaches out to these people.

*   Ralph Vasquez (VP of marketing): Ralph is Isabel’s boss and the VP of Marketing at NTO. He looks over her plan and gives her the go ahead.  
    
*   Michele Hansley (technical marketer): Michele is the technical backbone of NTO’s Marketing team. She’ll be the one to implement Isabel’s plan in Data 360.  
    
*   Pia Larson (enterprise architect): Pia manages all the data across orgs at NTO. She’ll help Michele find the data she needs.  
    

With her stakeholders on board, Isabel’s all done! She hands the project over to Michele to implement.

![Meet Michele Hansley, the technical marketer of NTO’s team.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/advertising-with-data-cloud/craft-effective-advertising-with-data-cloud/images/95f357dbd723ba38c71e644b66659713_kix.u30fw7g152t8.png)

## Implement Lookalike Audiences

Let’s follow Michele as she implements a portion of the project: reach new audiences with lookalike audiences.

1.  **Ingest and unify customer profiles.** First, Michele needs to find customer profiles who have bought previous versions of the camping equipment. Michelle works with Pia to find this data in NTO’s Sales orgs. Michele ingests this data into her Marketing org. Michele unifies the profiles with identity resolution.  
    

2.  **Use a calculated insight to identify traits to look for.** Next, Michele creates and runs a calculated insight to identify trends about NTO’s best customers, such as purchasing habits, interaction with content, and interests.  
    

She reviews the calculated insight to identify which shared traits to look for in lookalike audiences.

Michele makes these observations about her best customers.

*   The customers purchase new equipment every 1 to 3 months.  
    
*   The customers click an email or social media post every month.  
    
*   The customers are interested in national parks.  
    

3.  **Create a segment of best customers.** Next, Michele creates a segment of her best customers based on these traits. Michele creates an Einstein segment, which uses AI to translate her description into attributes to apply to the segment. Michele describes the segment she wants in natural human language: “Create a segment with customers that purchase new equipment every 1 to 3 months, click an email or social media post every month, and are interested in national parks.” Einstein does the rest, turning her description into attributes.  
    

4.  **Activate the segment to paid media partners.** Michele activates the segment to NTO’s paid media partners, such as Meta, where her segment is used as a seed audience. Meta finds lookalike audiences based on the seed audience, and delivers NTO’s ads to the lookalikes. NTO’s campaigns are reaching brand-new customers that have a high potential to become loyal customers.  
    

5.  **Send engagement data with Conversions API (CAPI).** Michele also creates a Meta CAPI activation target. She activates the Engagement DMO, which stores engagement data, to the CAPI activation target. Now Data 360 will send engagement events to Meta, where Meta uses this data to optimize the seed audience and find lookalike audiences who are most likely to convert.  
    

6.  **Capture new leads and ingest them into Data 360.** Michele also adds users who engage with her campaign from Meta into Salesforce as new leads. Then she ingests the new leads into Data 360 to use in her campaign. This helps her campaign continuously improve and narrow in on the most interested audience.  
    

Michele and Isabel are ready to sit back, relax, and let the new customers come rolling in!

## Wrap Up

Round of applause for Michele and Isabel! They implemented an advertising plan completely built on first-party data and Data 360.

At the beginning of this module, you learned about the decline of third-party data due to regulations and industry changes, and the rising importance of first-party data. Then you learned how Data 360 unlocks the value of your first-party data and explored advertising use cases for Data 360. Finally, you followed Isabel and Michele as they strategized and implemented an advertising campaign. Now it’s time to complete the final quiz and earn a shiny new badge!

## Resources

*   [_Salesforce Help_: Connect Data](https://help.salesforce.com/s/articleView?id=data.c360_a_data_ingestion.htm&type=5)
*   [_Salesforce Help_: Create Segments and Activate](https://help.salesforce.com/s/articleView?id=data.c360_a_segments.htm&type=5)
*   [_Salesforce Help_: Act on Data in Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_act_on_data.htm&type=5)
*   [_Salesforce Help_: Lead Capture in Marketing Cloud Advertising](https://help.salesforce.com/s/articleView?id=mktg.mc_ads_lead_capture.htm&type=5)
*   [_Salesforce Knowledge Article_: How to Activate Events to Meta via the Data 360 Conversions API Connector](https://help.salesforce.com/s/articleView?language=en_US&id=003960741&type=1)

## Preguntas

**Pregunta 1:** ¿Cómo segmenta NTO a los clientes interesados para mejorar la conversión del nuevo equipo de camping?

✅ **A — Isabel targets a segment of customers that previously searched for camping equipment.**

El documento lo describe claramente: Isabel crea un segmento con clientes que recientemente buscaron equipo de camping en su sitio web, ya que tienen un interés demostrado y son más propensos a comprar.

---

**Pregunta 2:** Después de que Isabel termina de hablar con los stakeholders, ¿quién toma el liderazgo en la implementación del proyecto?

✅ **C — Michele Hansley, the technical marketer**

El documento lo confirma: *"She hands the project over to Michele to implement."* Michele es descrita como la columna vertebral técnica del equipo de marketing, y es quien lleva a cabo todos los pasos de implementación.