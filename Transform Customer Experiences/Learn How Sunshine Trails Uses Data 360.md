Learn How Sunshine Trails Uses Data 360
=======================================

Learning Objectives
-------------------

After completing this unit, you’ll be able to:

*   Review the key concepts and learnings from the Unlock the Value of Your Data trail.  
    
*   Walk through how Sunshine Trails selected its use case.  
    
*   Explore how Sunshine Trails uses Data 360 and Agentforce to create a personalized experience for its customers.  
    
*   Review a Sunshine Trails customer’s contact record with unified data.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

Before You Start
----------------

This badge is part of the [Data 360: Unlock the Value of Your Data](https://trailhead.salesforce.com/content/learn/trails/data-cloud-unlock-the-value-of-your-data) trail. The trail explains the strategic importance and benefits of Salesforce Data 360. In this badge, we recap the learning from the trail and then follow along with hotel chain Sunshine Trails, and explore how it transformed customer experiences through Data 360.

Review Key Concepts
-------------------

Throughout this trail, we’ve covered concepts that help you understand the benefits and value of Data 360 to enhance your business goals.

### Understand the Data Landscape

You learned that Data 360 unifies scattered, unstructured data to overcome challenges like data silos and unreliable insights. You explored the key capabilities including real-time processing, zero-copy integration with external data lakes and warehouses, and how Data 360 serves as the foundation for AI by providing trusted, unified data for predictive models and AI agents.

### Discover the Value

You learned how Data 360 transforms raw business data into actionable intelligence for various functions like sales, service, marketing, or AI-driven automation. You can identify business objectives, requirements, and craft an actionable use case, emphasizing starting small to quickly demonstrate value. You can select and calculate key performance indicators (KPIs), such as increasing sales revenue or decreasing case resolution time, and provide methods for calculating ROI. You also learned about Data 360’s flexible, consumption-based pricing model, where costs adapt to usage rather than fixed seat-based fees, with credits tied to data volume, speed, features, and storage.

### Prepare for Success

You learned the essential steps for preparing an organization for a successful Data 360 implementation, such as data assessment. Data 360’s effectiveness relies on the quality of ingested data, and poor quality can lead to inaccurate insights and eroded trust. You know how to review existing data sources for quality, structure, unique identifiers, and data types in advance. And you learned how to assemble a cross-functional implementation team. You learned how to outline typical roles and responsibilities within an implementation team, from executive sponsor to IT and security teams, and emphasize the importance of shared skills and a clear data strategy for alignment.

### Build a Solid Foundation

You learned how a Data 360 foundation relies on scalable and flexible architecture, ethical and secure data use, and extensibility. You explored how Data Cloud One extends Data 360’s reach across Salesforce organizations and data spaces segregate data and processes. Secure data use is maintained via Data 360 Governance, offering policy-based access, AI tagging, and dynamic masking, supplemented by Platform Encryption. Finally, you know that extensibility and testing are supported by packaging and data kits for component building and testing in sandbox environments, allowing for development and training without affecting production.

By understanding how to determine a use case, prepare for success, and build a foundation, organizations like Sunshine Trails can transform guest experiences with Data 360. Let’s walk through Sunshine Trails’s process.

Sunshine Trails Transforms Guest Experiences
--------------------------------------------

When choosing a strategic use case to implement, especially with Salesforce Data 360, it's crucial to start with a small, actionable project that can quickly demonstrate value and track return on investment (ROI). Successful small-scale implementations pave the way for tackling larger initiatives. To help select this initial use case, the Sunshine Trails team explored the following key questions.

*   Desired outcomes: What specific results do you aim to achieve?  
    
*   Success metrics: How will you define success in the short- and long-term?  
    
*   Beneficiaries: Which roles or teams within your company will benefit from this use case?  
    
*   Business context: What is the specific business problem or scenario this use case addresses?  
    
*   Data-driven action: What specific activity or action needs to be performed using data?  
    
*   Data requirements: What data is necessary for this use case, and is it readily accessible?  
    
*   Timeline: What is the ideal timeframe for completing this use case?  
    
*   Key stakeholders: Who needs to be involved to ensure successful implementation?  
    

The team decides to enhance guest experiences and streamline operations using Salesforce Data 360 for personalized service and intelligent automation. They choose to begin by improving the experience for their customer support representatives. Their goal is to enhance overall customer experience and reduce the time support reps spend on booking rooms. This will allow their reps to focus on more complex support issues and measure the resulting outcomes.

**Use Case:** Create an interactive guest experience that answers customer questions and helps customers book their vacation.

**Goals**: Improve personalization and customer experience, while reducing customer support hours.

**Trackable KPIs:**

*   Lower customer support hours  
    
*   Higher customer survey results  
    

**Implementation Team:** Based on their discussions, they hire an implementation team to help set up their guest experience. Their own team, including their existing data architect shadows the team throughout the experience.

**Initial Data Sources**

*   Sales Cloud  
    
*   Service Cloud  
    
*   Loyalty Cloud  
    
*   Amazon S3  
    
*   Snowflake  
    
*   MuleSoft  
    

**Decisions:** Here are a few key decisions made by the Sunshine Trails team before implementation.

*   Connect Data 360 to their existing Sales Cloud instance as their home org  
    
*   Use Experience Cloud for their website development  
    
*   Create a unified guest profile based on normalized email, fuzzy name and normalized phone, or party identification  
    
*   Use a zero copy integration with Snowflake  
    
*   Build a service agent using Agentforce  
    

Personalized Guest Experiences on Data 360
------------------------------------------

Let’s see the end result on how the Sunshine Trails use case came together. Sunshine Trails implemented Data 360 and Agentforce to deliver a personalized experience for its guests, starting with searching for a property that matches guests’ needs.

On the Sunshine Trails new Experience Cloud site, the hotel chain has added a service agent to assist guests. Once the guest engages with the agent to find the perfect property, the agent provides suggestions tailored from preferences for the identified guest based on information found on their unified profile.

![Sunshine Trails website with agent.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-transform-customer-experiences/learn-how-sunshine-trails-uses-data-cloud/images/a3b1d93a6a3895f8380843d2b484cbf7_kix.41cauoelrs0q.jpg)

The customer shares a request with the agent, “Find a beachfront family-friendly hotel for next weekend” and the agent gets to work. The agent uses the large language model (LLM) in the background to determine the dates referenced as “next weekend”. The agent also accesses both structured and unstructured data using Data 360 hosted data assets and resources to match hotels based on the requirements specified and available reservations based on the requested dates.

![Chat provides available hotels for the following weekend.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-transform-customer-experiences/learn-how-sunshine-trails-uses-data-cloud/images/caa7bf0cee303e8323f6cb20d94e30bd_kix.uvdwd4tj4s6l.png)

This customer then asks what activities the hotel offers. The agent understands the context and responds by displaying the experiences for that property. These suggested experiences are tailored to the preferences from the guest and their past experiences, which the agent is available to access from the unified guest profile.

Explore the Unified Guest Profile
---------------------------------

The customer is impressed because the Agent understands their requests and is able to provide relevant information for a trip they would like to plan and did so in record time. This initial guest experience is possible due to the powerful features of Data 360 based on the unified guest profile and calculated insights created about each guest.

Let’s take a look at the guest profile for Marje Coley, a high-priority guest, to see what information is available there. Not only can the agent access information about Marje, the customer service representatives (CSRs) at Sunshine Trails can use this data to drive an unforgettable guest experience.

Marje’s data has been connected from multiple data sources including Sales, Service, Loyalty Cloud, and from MuleSoft, Snowflake, and Amazon. Because this data is connected with Data 360, this data is easily accessible to the CSR. In this case, the CSR can see the calculated insight of Marje’s customer lifetime value (1) and other helpful data points, like past survey feedback.

![Marje Croley’s contact record in Salesforce.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-transform-customer-experiences/learn-how-sunshine-trails-uses-data-cloud/images/efe1fea85707a97c7d4584377d576594_kix.goa3fpxk8btn.png)

The details section of Marje’s record also shows guest preferences, past stays, number of children, and experience interests. This helps the agent and the CSR provide a personalized guest experience.

Data 360 gives CSRs access to data that they need while still respecting data governance guidelines. With Zero Copy Data Federation and Data 360, a CSR does not need to switch systems to access key guest information. Additionally, data such as third-party survey results and unique data like key swipes can be easily brought into Sunshine Trails using out-of-the-box connectors. For example, after looking through some survey results regarding unkept rooms, the CSR can request housekeeping to pay extra attention to a guest's room during their upcoming stay.

Real-time data also allows customer browsing behavior to be recorded as it occurs. As guests look at different Sunshine Trails products available on its Experience Cloud website, the agents can use these browsing behaviors in real time to offer product suggestions and answer questions.

The unified profile made possible by Data 360 provides a wealth of information to the customer service rep and the agent. By connecting and unifying data from multiple sources to create a full view of the guest, quick and actionable insights can be used to drive guest satisfaction.

Just the Beginning
------------------

With the unified guest profile, the power of zero copy, and recommendations generated from Salesforce data, Agentforce is able to maximize the guest experience and interact in real time. Since Sunshine Trails has achieved its first use case, the hotel chain can begin calculating time saved and satisfaction scores. In addition, since the foundation is set within Data 360 and its unified profile rules, Sunshine Trails can now move on to its next use case to improve the check-in experience!

Continue Your Learning
----------------------

As shown by Sunshine Trails’s experience, Data 360 can help improve guest experiences, streamline operations, and enhance customer satisfaction through access to unified data. Let this inspire you to explore the ways Data 360 can enhance your business.

Great job completing this trail! Explore more about Data 360 and when ready, continue your learning and get hands-on by checking out [Data 360: Explore Setup to Activation](https://trailhead.salesforce.com/content/learn/trails/data-cloud-explore-setup-to-activation).

Resources
---------

*   [_Salesforce Help_: About Data 360 Releases](https://help.salesforce.com/s/articleView?id=data.c360_a_dc_releases.htm&type=5)
*   [_Salesforce_: Sample Industry App: Sunshine Trails Hospitality](https://www.salesforce.com/data/resources/sample-app-hospitality/)
*   [_GitHub_: DataCloudAndAgentForceForHospitality](https://github.com/salesforce-misc/DataCloudAndAgentForceForHospitality)
*   [_Salesforce_: Travel, Transportation & Hospitality: Orchestrate Guest Journeys](https://www.salesforce.com/travel-hospitality-transportation/hospitality/)

Prueba
------

Para completar esta unidad, debe responder correctamente todas las preguntas de la prueba.

1 Which tool connects and unifies structured and unstructured data from disparate sources, enabling real-time analytics and insights?
A) Data Structure
B) Agentforce
C) Customer 360
D) Data 360 *

2 When choosing a strategic use case for Salesforce Data 360, what is the primary recommendation for initial projects?
A) Focus on a large, complex initiative to demonstrate comprehensive value of your investment.
B) Choose a use case based on scalable and flexible architecture.
C) Prioritize projects that require minimal data integration.
D) Select a small, actionable project that can quickly demonstrate value. *
