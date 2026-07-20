# Inquiro Project Summary

## Project Purpose

Inquiro is a prototype multi-agent academic research assistant. It accepts a research question, prepares a research plan, retrieves academic paper metadata and abstracts from arXiv, analyses the retrieved evidence and generates a structured Markdown report.

The aim was to implement a working and testable intelligent-agent system rather than a production-level research platform.

## Final Architecture

The system contains four specialised agent roles:

- **Planner Agent** – creates a research plan and technical search query.
- **Retriever Agent** – searches arXiv and returns academic paper information.
- **Processor Agent** – analyses the retrieved abstracts and identifies useful findings.
- **Writer Agent** – generates the final structured research report.

LangGraph coordinates the agents through a shared `ResearchState` object.

Although the agents have different prompts, inputs and responsibilities, they use one shared local Ollama model: `llama3.2:3b`. This reduced local hardware requirements while preserving the multi-agent architecture.

## Workflow

```text
Research Question
      ↓
Planner
      ↓
Retriever
      ↓
Processor
      ↓
Writer
      ↓
Markdown Report