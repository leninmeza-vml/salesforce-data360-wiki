# Process Content for Use with AI

## Learning Objectives

After completing this unit, you’ll be able to:

*   Identify the role of Document AI in extracting key details from unstructured data.  
    
*   Describe how unstructured data enhances context for Agentforce and other AI applications.  
    
*   Describe how organizations can use Document AI to act on unstructured knowledge.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Before You Start

This badge is part of the [Data 360: Explore Setup to Activation](https://trailhead.salesforce.com/content/learn/trails/data-cloud-explore-setup-to-activation) trail. The trail is designed to give you hands-on experience with the core functionalities of Data 360.

In this badge, you learn how Data 360 processes content, particularly unstructured content. Structured data, such as account details or transaction history, has long been the backbone of CRM systems. However, unstructured data, such as articles, chat transcripts, case notes, and email, represents a vast knowledge base now available to organizations for use with AI applications to deepen context and improve customer engagement.

## Agentforce and Data 360

Imagine a support agent asking Agentforce, “What troubleshooting steps should I suggest for this customer’s error code?” Instead of scanning dozens of knowledge articles or case notes, Agentforce retrieves the right content from Data 360, grounds the AI response with that verified knowledge, and instantly generates a clear, contextual answer. The result is faster case resolution, less manual searching, and more accurate customer support.

## Unstructured Data in Data 360: Lay the Foundation for Agentforce

Unstructured data refers to information that doesn’t follow a consistent format and so can’t be easily placed into a relational database, fields tables, or spreadsheets. This type of data comes in many forms: text, images, audio, videos, email, chat transcripts, PDFs, knowledge articles, case notes, email exchanges, support chat transcripts, legal documents, and more. While it’s harder to organize, it’s rich with context such as customer feedback, sentiment, tone, and insights that structured data simply cannot capture.

Unstructured data requires a different approach than structured data. With Data 360, you can ingest content through prebuilt connectors, and create search index configurations to convert content like text, images, or tables into chunks and numerical vectors. Data 360 indexes these chunks and vectors for rapid search and retrieval by AI applications, analytics dashboards, and workflow automations.

Document AI is one tool to use to process unstructured (or semi-structured) data. Using Document AI, you can extract key details from PDFs, invoices, contracts, and reports into data lake objects (DLOs), which represent schemas of the extracted data.

Essentially, Document AI identifies fields such as customer name, dates, addresses, and dollar amounts and converts these into structured, searchable data in Data 360. This makes the content ready for use in AI prompts, analytics, and automation. For example, a Service Cloud admin for a hotel chain could use Document AI to extract guest feedback from survey forms, and then assign an AI agent to create customer records and follow-ups for future opportunities based on that extracted data.

## Use Case: Bring It Together

Get Cloudy Consulting is a global consulting firm that relies on thousands of proposals, research reports, and client presentations stored across regions and practices to do business. A consultant preparing for a client meeting needs quick insights into past recommendations for digital transformation in the retail sector.

Since the consultant’s team previously used Document AI to extract frameworks, case studies, and benchmarks from unstructured decks and reports, the consultant can simply query Agentforce and retrieve the most relevant recommendations and supporting data points for the client.

Instead of combing through folders or relying on memory, the consultant gets accurate, context-rich insights instantly. Now they’re ready to deliver a personalized, high-impact client presentation.

By transforming unstructured content into structured knowledge, Get Cloudy Consulting empowers their teams to deliver faster, more personalized, and trustworthy experiences.

In this unit, you learned how Document AI makes unstructured data usable in Data 360. By extracting and structuring insights from diverse formats, Data 360 equips AI applications like Agentforce with trustworthy information that supports faster, more accurate responses. Next, explore how this foundation powers retrieval augmented generation (RAG) to ground AI outputs in verifiable data.

## Resources

*   [_Salesforce Help_: Document AI](https://help.salesforce.com/s/articleView?id=data.c360_a_document_ai.htm&type=5)
*   [_Salesforce Help_: Using Unstructured Data in Data Cloud](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_connect_overview.htm&type=5)
*   [_Salesforce Help_: Use Search for AI, Automation, and Analytics](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&type=5)

## Unit's quiz:

**Question 1:** What does Document AI do with unstructured content such as contracts or case notes?
**Answer: B – It extracts key details and converts them into structured data.**
The unit describes exactly this: Document AI identifies fields like customer names, dates, addresses, and dollar amounts from PDFs, invoices, and reports, then converts them into structured, searchable data stored in data lake objects (DLOs).

**Question 2:** How does unstructured data enhance AI capabilities in Data 360?
**Answer: C – It adds additional context, sentiment, and relevant knowledge from real-world text sources.**
The unit emphasizes that unstructured data is "rich with context such as customer feedback, sentiment, tone, and insights that structured data simply cannot capture" — making it a valuable complement to structured data for grounding AI responses.
