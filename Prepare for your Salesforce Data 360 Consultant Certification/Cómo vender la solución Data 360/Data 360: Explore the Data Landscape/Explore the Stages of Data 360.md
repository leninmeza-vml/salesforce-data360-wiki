# Explore the Stages of Data 360

## Learning Objectives

After completing this unit, you’ll be able to:

*   Identify data processing stages of Data 360.  
    
*   Define Data 360 features for each stage.  
    

## The Stages of Data 360

Before you bring data into Data 360, learn how Data 360 transforms your fragmented data into unified action. The flow of data through Data 360 can be divided into three stages: Connect data, harmonize and unify, and analyze and act.![Data 360 data and functionality diagram.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-explore-the-data-landscape/explore-the-stages-of-data-cloud/images/94674a7336617755b8804092b1099b09_kix.18x1qjes9urv.png)

Let’s explore each stage.

## Stage 1: Connect Data

Connect all your enterprise data, whether it's structured or unstructured, and regardless of where it resides. Data 360 is flexible and extensible so it works for small and large business models.

### Use Data Cloud One

For companies that have multiple Salesforce orgs, consider Data Cloud One to expand Data 360 functionality across orgs. Connect multiple companion orgs to your Data 360 home org. Give companion orgs access to Data 360 data and features. Learn more in [Data Cloud One](https://trailhead.salesforce.com/content/learn/modules/data-cloud-one-quick-look).

### Make the Connection

In addition to connecting to all your Salesforce CRM data across clouds, Data 360 offers over 275 prebuilt connectors to third-party applications and systems such as SAP, NetSuite, and Stripe. With MuleSoft you can connect to legacy systems, industry specific systems and on-premise systems.

Through Zero Copy Data Federation, Data 360 can mirror data from a company’s existing data lakes and warehouses (such as AWS, Azure, Google Cloud, Snowflake, Databricks, and Amazon Redshift) without physically copying or duplicating it. This allows for faster insights, reduced costs, and improved governance.

### Get Unstructured Data Ready for Action

Data 360 is not just for structured data, data organized in a standard format. It can also connect and process unstructured data like video, audio, PDFs, and text. For unstructured data, Data 360 performs several key steps with the data.

*   **Connect:** Ingests unstructured data using prebuilt connectors (including Amazon S3, Azure, Google Cloud Storage).  
    
*   **Process:** Unpacks the data using various chunking and transcribing strategies, extracts metadata (entities, keywords, summaries, questions, topics), and categorizes it.  
    
*   **Store:** Vectorizes the processed data (converts it into numerical representation) and stores it in a Vector Database.  
    
*   **Index:** Creates keyword and knowledge graph indexes for efficient retrieval that goes beyond text matching.  
    
*   **Activate**: Makes the data available for activation in Agentforce, analytics, Apex Code, automations, Customer 360, and search using no-code retrievers, hybrid search, and retrieval augmented generation (RAG). This means AI provides answers that are grounded in a business’ own trusted information.  
    

## Stage 2: Harmonize and Unify

Once your data is connected, establish data governance. Then harmonize and cleanse it with data transforms. Finally unify the data to create a single, comprehensive unified customer profile.

### Establish Data Governance

Data governance is crucial for managing data securely and compliantly. Confidently manage data access and security with Data 360.

*   **Auto-tagging and classification:** Govern both structured and unstructured data through automatic tagging and classification with metadata tags.  
    
*   **Policy-based data access:** Enforce access across all data sources using a policy-based framework. Policies can be set at the field, object, or record level and automatically apply across all areas of Data 360, including Agentforce, Analytics, and Segmentation.  
    
*   **Platform encryption:** Add an extra layer of security to sensitive data with Platform Encryption.  
    
*   **Data spaces:** Segregate data, metadata, and processes by brand, business unit, or region, allowing each unit to control its data within a single Data 360 instance.  
    

### Transform Data and Create Unified Profiles

*   **Data prep and transformations:** Prepare and transform data to ensure consistency with batch and streaming data transforms.  
    
*   **Unified data model:** Map data to a unified metadata model that is deeply integrated with the Salesforce metadata framework. This means external data can behave like standard Salesforce objects and fields.  
    
*   **Identity resolution and unified profiles:** Resolve customer identities across disparate sources and build a unified profile for each customer. Teams across the business can easily access and work with the most complete and accurate picture of each customer.  
    

## Stage 3: Analyze and Act

Now that your data is harmonized and governed, generate valuable insights and drive smarter decisions. Create segments, enhance data with insights and predictions, and activate your data in apps and agents.

### Query and Segment

*   **Calculated insights:** Create new metrics and insights by combining data from various sources. These can be automatically updated, so customers are always working with the freshest data.  
    
*   **Segments:** Create targeted audience segments based on unified customer profiles. Deliver campaigns precisely tailored for these audiences.  
    

### Analyze and Predict

Analyze your data in various business intelligence (BI) tools or build your own predictive model.

*   **Predictive models:** Anticipate customer behavior and outcomes. You can develop and deploy predictive models in Einstein Studio or integrate existing models with Bring Your Own Model.  
    

### Act on Data Across Your Org

Data 360 enables teams to act on their data faster by powering personalized experiences that lead to smarter decision-making.

*   **Org and object enrichment:** Data and insights captured can be surfaced directly on Salesforce object records, such as accounts or contact profiles. This means richer context in the flow of work for every interaction.  
    
*   **Data 360 triggered flows:** Automate workflows and trigger actions based on real-time data and insights using Flow Builder.  
    

### Activate in Apps and AI

Activate unified, governed, and insightful data across your enterprise.

*   **Salesforce apps:** Power your Sales, Service, and Marketing Cloud applications with a complete view of the customer.  
    
*   **Agentforce:** Equip AI agents with trusted, contextual data to deliver effective responses, resolve issues, and automate tasks using retrieval augmented generation (RAG) and hybrid search capabilities.  
    
*   **Analytics:** Fuel powerful analytics and dashboards for comprehensive business intelligence.  
    
*   **Ad platforms:** Reach the right audience with precision for targeted advertising campaigns.  
    
*   **Third party business apps:** Extend the value of data to other business applications across an ecosystem.  
    

## Sum It Up

Data 360 is an integrated platform for customer experiences, unifying all structured and unstructured data, including Zero Copy external sources, into a single actionable profile. It powers AI and drives real-time personalized experiences, automation, and smarter decisions across Customer 360 and beyond.

Next, learn about developing an enterprise data strategy in [Customer-Centric Data Strategies](https://trailhead.salesforce.com/content/learn/modules/data-architecture-planning).

## Resources

*   [_Trailhead_: Data 360 Connectors and Integrations](https://trailhead.salesforce.com/content/learn/modules/data-cloud-connectors-and-integrations)
*   [_Trailhead_: Unstructured Data in Data 360](https://trailhead.salesforce.com/content/learn/projects/unstructured-data-in-data-cloud)
*   [_Trailhead_: Data 360 Governance](https://trailhead.salesforce.com/content/learn/modules/data-cloud-governance-quick-look/get-to-know-data-cloud-governance)
*   [_Trailhead_: Platform Encryption for Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/platform-encryption-for-data-cloud)
*   [_Trailhead_: Data Spaces in Data 360: Quick Look](https://trailhead.salesforce.com/content/learn/modules/data-spaces-in-data-cloud-quick-look)
*   [_Trailhead_: Batch Data Transforms: Quick Look](https://trailhead.salesforce.com/content/learn/modules/batch-data-transforms-in-data-cloud-quick-look)
*   [_Trailhead_: Streaming Data Transforms: Quick Look](https://trailhead.salesforce.com/content/learn/modules/streaming-data-transforms-quick-look)
*   [_Trailhead_: Data 360 Insights](https://trailhead.salesforce.com/content/learn/modules/customer-data-platform-insights)
*   [_Trailhead_: Segmentation and Activation](https://trailhead.salesforce.com/content/learn/modules/customer-360-audiences-segmentation)
*   [_Trailhead_: Build AI Models in Einstein Studio](https://trailhead.salesforce.com/content/learn/modules/build-ai-models-in-einstein-studio)
*   [_Trailhead_: Data 360 Enrichments](https://trailhead.salesforce.com/content/learn/modules/data-cloud-enrichments)
*   [_Trailhead_: Data 360 in Flows](https://trailhead.salesforce.com/content/learn/modules/data-cloud-in-flows)
*   [_Trailhead_: Advertising with Data 360](https://trailhead.salesforce.com/content/learn/modules/advertising-with-data-cloud)
*   [_Trailhead_: Introduction to Data 360 Reports](https://trailhead.salesforce.com/content/learn/modules/introduction-to-data-cloud-reports)

## Preguntas

1 Which of the following correctly identifies the name and correct order of data processing stages?

X.- Connect Data | Analyze and Act | Harmonize and Unify

X.- Harmonize and Unify | Analyze and Act | Connect Data

Connect Data | Harmonize and Unify | Analyze and Act

X.- Analyze and Act | Harmonize and Unify | Connect Data

2 After connecting data from disparate sources, what’s your next step?

Transform, prepare, and unify data.

X.- Build calculated insights.

X.- Activate data in Agentforce.

X.- Create targeted audience segments.