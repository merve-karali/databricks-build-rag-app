# Databricks build RAG app Hackathon

## Instructions:
text text

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

