# Use RAG to Bring Unstructured Data to Agentforce

## Learning Objectives

After completing this unit, you’ll be able to:

*   Define retrieval augmented generation (RAG).  
    
*   Explain how RAG grounds LLM responses in trusted, up-to-date data.  
    
*   Describe the benefits of using RAG for accuracy, transparency, and trust.  
    

## Enhance AI Responses with RAG

Retrieval augmented generation (RAG) is a framework that makes generative AI more accurate and trustworthy. It works by retrieving the most relevant customer or enterprise data from trusted sources and adding that context into the large language model (LLM) before generating a response.

With RAG, you get:

*   **Greater accuracy and relevance:** AI responses are grounded in real data, which reduces the chance of incorrect answers.  
    
*   **Up-to-date information:** The AI can access the latest data without retraining large models.  
    
*   **Trust and transparency:** Citations show where the information came from, so users can verify responses.  
    

## How RAG Works

RAG follows three steps.

1.  **Retrieval:** The system searches unstructured knowledge that Data 360 processed to find the most relevant data for the user’s query.  
    
2.  **Augmentation:** The retrieved data is added to the LLM prompt, giving the model more context.  
    

**Generation:** The prompt, now enriched with customer data, is sent to the LLM to produce an accurate, contextual, and trustworthy response.

## Northern Trail Outfitters: Apply RAG

Northern Trail Outfitters (NTO) is a retail company that sells outdoor gear, apparel, and equipment. NTO sales reps use Agentforce frequently while working on sales opportunities to quickly access customer insights and performance data.

For example, an NTO sales rep asks Agentforce, “What is my customer’s Q2 revenue for Product X in North America?”

Behind the scenes, RAG searches the customer’s financial PDF reports and finds the answer: $12.4 million in Q2 revenue, an 8% increase over Q1. This trusted data is added into the large language model prompt so the AI has the exact figures and context it needs.

The model then responds with: “In Q2, Product X generated $12.4 million in revenue in North America, reflecting an 8% growth from Q1.”

With RAG, the sales rep gets a response that is accurate, grounded in real customer data, and immediately useful in the flow of work.

## Fine-Tune RAG

You can customize how much and what kind of content to include by adjusting retriever settings such as search criteria and result limits to fine-tune what gets pulled in.

![RAG runtime flow: LLM prompt augmented with relevant information to instruct LLM response generation.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-process-content/use-rag-to-bring-unstructured-data-to-agentforce/images/1c6bea0309f0497da032e820853bca5f_kix.vctazlbcd7of.png)

Learn more in the [Retrieval Augmented Generation: Quick Look](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look) module.

In this unit, you explored how retrieval augmented generation builds on processed and indexed data to deliver fact-based, verifiable responses. With RAG, Agentforce and other AI applications can provide users with answers they can trust, grounded in the right data at the right time. Together, these resources will help you put knowledge-powered, AI-enhanced data strategies into action.

Take the next step by exploring how to use unified data to create meaningful audience groups. Next up, learn how to build and refine queries using the [Data 360: Query and Segment](https://trailhead.salesforce.com/content/learn/modules/data-cloud-query-and-segment) module to target the right customers and drive personalized engagement.

## Resources

*   [_Salesforce Help_: Ground with Knowledge Using Retrieval Augmented Generation](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_ground_rag.htm&type=5)
*   [_Trailhead_: Agentforce Data Library Basics](https://trailhead.salesforce.com/content/learn/modules/agentforce-data-library-basics)
*   [_Trailhead_: Hybrid Search for RAG: Quick Look](https://trailhead.salesforce.com/content/learn/modules/hybrid-search-for-rag-quick-look)
*   [_Trailhead_: Knowledge Grounding for AI: Quick Look](https://trailhead.salesforce.com/content/learn/modules/knowledge-grounding-for-ai-quick-look)

## Unit's quiz:

**Question 1:** What is the primary purpose of RAG in Data 360?
**Answer: B – It grounds large language model (LLM) responses in relevant, trusted data retrieved at runtime.**
The unit defines RAG as a framework that retrieves the most relevant data from trusted sources and adds that context into the LLM *before* generating a response — ensuring accuracy and trustworthiness rather than relying on the model's training data alone.

**Question 2:** Which is a key benefit of using RAG in Data 360?
**Answer: B – It allows AI models to access real-time, accurate, and verifiable information.**
The unit highlights three core benefits of RAG: greater accuracy, up-to-date information (without retraining models), and trust through citations. Option B captures all of these — real-time access, accuracy, and verifiability.