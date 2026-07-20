
# 3. `implementation-reflection.md`

```markdown
# Inquiro Implementation Reflection

## What?

I implemented Inquiro as a working multi-agent academic research assistant using Python, LangGraph, Ollama and the arXiv API.

The system contains Planner, Retriever, Processor and Writer agents. Each agent performs a separate task and passes updated information through a shared LangGraph state. The final system generates a structured report and saves logs and intermediate outputs for each run.

## So What?

Before implementing this project, I understood multi-agent systems mainly at a conceptual level. Building Inquiro helped me understand how agent roles, state management and workflow orchestration operate in a practical software system.

One important design decision was to use one local Ollama model for all four agents. Initially, I considered using different models, but this would have increased the hardware requirements and made testing more difficult. I learned that a multi-agent system does not necessarily require a different LLM for every agent. The agents can remain distinct because they have separate responsibilities, prompts, inputs and outputs.

Separating the code into individual files also made the system easier to debug. When a problem occurred, I could identify whether it came from planning, retrieval, processing or report generation.

The project also showed me that successful execution does not always mean a high-quality result. The code could run correctly while still returning irrelevant or insufficient academic papers. This made retrieval quality, testing and evidence inspection important parts of the evaluation.

## Now What?

Future improvements would focus first on retrieval quality rather than adding more features. I would introduce stronger relevance scoring, paper deduplication and additional academic sources.

I would also add a human approval step before the final report is produced. A web interface could be added later, but only after the retrieval and evaluation process is more reliable.

Overall, the project increased my confidence in designing, implementing and testing an intelligent-agent workflow while also making me more aware of its limitations.