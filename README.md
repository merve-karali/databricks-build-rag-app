# Build Your LLM-Powered Chatbot with Databricks and RAG

In this tutorial, you will learn how to build a chatbot assistant to help identify the most suitable candidates for projects based on their CVs. Using Retrieval Augmented Generation (RAG) and Databricks’ state-of-the-art tools, including the Databricks Foundation Models and Vector Search, you'll create a powerful solution for intelligent candidate matching.

Explore this content to discover how to leverage all the Databricks Data Intelligence Platform capabilities for your GenAI Apps.

You will learn:

- How to extract information from unstructured documents (pdfs) and create custom chunks
- Leverage Databricks Embedding Foundation Model to compute the chunks embeddings
- Create a Self Managed Vector Search index and send queries to find similar documents
- Build an advanced langchain model with chat history, leveraging Databricks Foundation Models
- Ask external expert to test and review your chatbot with Mosaic AI Agent Evaluation review app
- Run online llm evaluation and track your metrics with Databricks Monitoring

## What is Retrieval Augmented Generation (RAG) for LLMs?

<img src="https://github.com/databricks-demos/dbdemos-resources/blob/main/images/product/chatbot-rag/rag-marchitecture.png?raw=true" width="700px" style="float: right" />

RAG is a powerful and efficient GenAI technique that allows you to improve model performance by leveraging your own data (e.g., documentation specific to your business), without the need to fine-tune the model.

This is done by providing your custom information as context to the LLM. This reduces hallucination and allows the LLM to produce results that provide company-specific data, without making any changes to the original LLM.

RAG has shown success in chatbots and Q&A systems that need to maintain up-to-date information or access domain-specific knowledge.

### RAG and Vector Search

To be able to provide additional context to our LLM, we need to search for documents/articles where the answer to our user question might be.
To do so,  a common solution is to deploy a vector database. This involves the creation of document embeddings, vectors of fixed size representing your document.<br/>
The vectors will then be used to perform real-time similarity search during inference.


## Cluster Setup:
For this notebook, we recommend using the DBRX 15.4 LTS Runtime for optimal performance.

## How to test:
Example Prompts to Test the Pipeline
These prompts test the pipeline’s ability to:
- Match candidates to specific skills.
- Understand follow-up questions in a conversational context.
- Handle unstructured project descriptions and derive key requirements for matching.
- This ensures the system performs effectively in real-world consultant scenarios.

####**Example 1**: Finding a Person with Specific Skills

Initial Query:

_“Find a candidate with expertise in Power BI and SQL for a data analytics project.”_

Expected System Behavior:
- The system retrieves CVs with strong experience in Power BI and SQL.
- It generates a summary of top candidates, highlighting their relevant projects and skills.

Follow-Up Query:

_“From the candidates you found, identify if any would be a good fit for a lead position. Focus on leadership experience and team management skills.”_

Expected System Behavior:
- The system filters candidates based on their leadership experience (e.g., previous roles as a team lead or project manager).
- It generates a summary highlighting leadership achievements and relevant experience.

### **Example 2**: Finding a Candidate Based on Project Context

Project Description:

_“We are planning a project to build an end-to-end business intelligence dashboard for an e-commerce client, integrating multiple data sources to track KPIs such as sales, inventory, and customer behavior.”_

Prompt to the System:

_“Find a candidate with experience relevant to this project. Prioritize expertise in business intelligence dashboard development, working with e-commerce data, and integrating multiple data sources.”_

Expected System Behavior:

- The system analyzes the project description to identify key skills and domain expertise.
- It retrieves CVs of candidates with experience in business intelligence, e-commerce, and data integration, summarizing relevant projects and accomplishments.

