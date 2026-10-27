# Insurance RAG Chatbot

## Overview

This project explores how **Retrieval-Augmented Generation (RAG)** can support insurance product enquiries by combining a large language model with information retrieved from reference documents. The academic prototype was designed to provide clear, document-grounded responses to questions from insurance agents and customers.

Developed for the **Business Cases with Data Science** course in the MSc in Data Science and Advanced Analytics at **NOVA IMS** (May 2025). The case study uses Fidelidade's savings products as its business context. **This is a student project, not an official Fidelidade chatbot or a production deployment.**

## Objectives

- Retrieve relevant information from authorized product documents to answer questions about insurance savings products.
- Support responses in Portuguese and English.
- Use prompt instructions to maintain the appropriate product scope, tone, and fallback behavior.
- Explore the usefulness and limitations of document-grounded conversational AI.

**Scope:** The implemented knowledge base focused on **Fidelidade Savings**. Although PPR Evoluir was discussed in the broader business case and referenced in the prompt, its source documents were not included in the final project knowledge base.

## Approach

The [Jupyter Notebook](insurance_rag_chatbot.ipynb) demonstrates a RAG workflow using Azure OpenAI:

1. Load authorized PDF documents from a local `documents/` folder.
2. Upload the files to a hosted vector store for indexing and retrieval.
3. Configure an assistant with document-search access and domain-specific instructions.
4. Accept user queries through a notebook-based conversation loop.
5. Retrieve relevant information and generate responses using the language model.

The implementation uses **`gpt-4o-mini`** as specified in the notebook. The project report refers more broadly to GPT-4o; these are not the same model configuration.

## Technologies

Python · Jupyter Notebook · Azure OpenAI · OpenAI Python SDK · Retrieval-Augmented Generation (RAG) · Vector stores · Hosted file search · Prompt engineering

## Evaluation and findings

The academic assessment used sample product questions and out-of-scope cases to examine answer correctness, citation quality, fallback behavior, and Portuguese/English support.

The results were reported qualitatively: answers and multilingual handling were generally encouraging, and out-of-scope handling was satisfactory. **Source-citation matching was less reliable and required improvement.** The assessment was limited in scale; it does not establish production readiness or measurable business outcomes.

## Repository files

- [`insurance_rag_chatbot.ipynb`](insurance_rag_chatbot.ipynb) — sanitized notebook documenting the 2025 prototype.
- `README.md` — project overview and limitations.
- `requirements.txt` — Python packages imported by the notebook, plus Jupyter.
- `.gitignore` — excludes local source documents, credentials, and generated files.

Original source PDFs, credentials, and saved chatbot conversations are **not included**. The academic report is also not published here.

## Reproduction and compatibility

This repository is a **historical implementation for portfolio review**, not a currently runnable chatbot application. It uses the Assistants API, which was retired on **August 26, 2026**. Running an equivalent solution today requires migration to supported APIs, appropriate Azure configuration, and access to authorized reference documents. See the [OpenAI migration guide](https://developers.openai.com/api/docs/assistants/migration).

The `requirements.txt` file lists project dependencies, but installing them does **not** restore the retired API.

To adapt the prototype, configure the `AZURE_OPENAI_API_KEY` and `AZURE_OPENAI_ENDPOINT` environment variables and use only documents you are authorized to process. Never publish API keys or private source materials.

## Limitations

- The published notebook does not include the Streamlit interface described in the broader project report.
- The knowledge base depends on static documents and does not provide live insurance prices or access to individual customer policies.
- The prototype has not been established as production-ready, and citation grounding needs further improvement.
- The chatbot is not a substitute for personalized insurance or financial advice.

## Team

**Group E · NOVA IMS · May 2025**

- Tomás Ribeiro
- Afonso Silva
- Jude Gbenimako
