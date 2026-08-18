# Rabbit Care AI Assistant

A RAG-based AI assistant for rabbit care and health-related knowledge retrieval.

> **Status:** In active development  
> **Role:** Independent developer  
> **Focus:** Retrieval-Augmented Generation (RAG) · LLM integration · knowledge retrieval · grounded response generation

## Project Overview

This project explores how a domain-focused AI assistant can answer rabbit-care questions using retrieved reference material instead of relying only on a language model's general knowledge.

The assistant is being developed as a **single-agent RAG system**. The current work focuses on improving retrieval quality and making the generated answers more closely grounded in the retrieved knowledge.

The goal is not to replace veterinary diagnosis. The system is intended as a knowledge-access and question-answering tool for rabbit-care information.

## System Concept

```text
User Question
     ↓
Query Processing
     ↓
Knowledge Retrieval
     ↓
Relevant Context
     ↓
LLM Response Generation
     ↓
Grounded Answer
```

The architecture is intentionally kept modular so retrieval, context construction, prompting, and answer generation can be evaluated and improved independently.

## What This Project Demonstrates

- Designing a domain-specific RAG workflow
- Building a retrieval layer around a curated knowledge base
- Integrating retrieved context with an LLM
- Iterating on retrieval relevance and answer grounding
- Separating retrieval, context construction, and response generation responsibilities
- Evaluating failure cases rather than treating the LLM as a black box

## Current Development Focus

The project is still being tuned. Current work is centered on:

- retrieval relevance
- chunk selection and context quality
- reducing irrelevant or weakly related retrieval results
- improving answer grounding
- testing questions with different levels of specificity
- refining the user-facing interaction flow

Because the system is still under development, this public repository documents the **architecture, design decisions, and development progress** rather than publishing the complete private implementation or knowledge base.

## Repository Structure

```text
.
├── README.md
├── docs/
│   ├── rag-design.md
│   └── development-status.md
└── examples/
    └── evaluation-template.md
```

## RAG Design

More detail about the reasoning behind the retrieval pipeline is available in [`docs/rag-design.md`](docs/rag-design.md).

## Development Status

Current progress and planned improvements are tracked in [`docs/development-status.md`](docs/development-status.md).

## Evaluation Approach

The assistant is being evaluated with practical questions rather than only checking whether a response is fluent. Important criteria include:

- whether the retrieved context is actually relevant to the question
- whether important information is missed during retrieval
- whether the final answer stays consistent with the retrieved material
- whether the system behaves sensibly when retrieval is weak or incomplete

A lightweight evaluation template is included in [`examples/evaluation-template.md`](examples/evaluation-template.md).

## Why This Repository Is Public

The production source code, knowledge base, prompts, and configuration remain private while the system is under development. This repository is a portfolio-oriented technical overview showing the system design, RAG workflow, and development methodology without exposing sensitive project assets.

## Planned Portfolio Updates

As development progresses, this repository can be expanded with:

- architecture diagrams
- anonymized retrieval examples
- evaluation results
- interface screenshots
- a short demonstration when the application is ready for presentation
