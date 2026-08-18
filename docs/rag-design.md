# RAG Design Notes

## Goal

The assistant is designed to answer rabbit-care questions using retrieved domain knowledge as context for an LLM.

The central design objective is **grounding**: the final answer should be driven by relevant retrieved material rather than generated only from the model's prior knowledge.

## High-Level Flow

```text
1. User submits a question
2. The system prepares the query for retrieval
3. Relevant knowledge chunks are retrieved
4. Retrieved material is assembled into model context
5. The LLM generates a response using that context
6. Retrieval and answer quality are reviewed during testing
```

## Why RAG

Rabbit-care questions can be highly specific, and relevant information may be spread across different sources or phrased in different ways. A retrieval layer makes it possible to provide the model with focused material at answer time instead of depending only on general model knowledge.

## Design Priorities

### Retrieval relevance

A fluent answer is not enough if the retrieved context is weak. Retrieval quality is therefore treated as a first-class part of the system.

Questions used during testing include broad daily-care questions, more specific health-related questions, and queries that use different wording for similar concepts.

### Context quality

The retrieved chunks need to contain enough information to support a useful answer without introducing excessive unrelated material.

This creates a practical tuning problem around:

- how documents are divided into chunks
- how much context is retrieved
- how closely retrieved chunks match the actual user intent
- whether neighboring context is needed for completeness

### Grounded generation

The response-generation stage is expected to use the retrieved context as the primary evidence available to the model.

During development, answer quality is reviewed together with retrieval output. This makes it easier to distinguish a retrieval failure from a generation failure.

## Failure Cases Being Considered

Typical failure modes for a RAG system include:

- highly similar chunks being retrieved repeatedly
- a semantically related but practically irrelevant passage ranking too highly
- important supporting context not being retrieved
- a query being too broad for a single retrieval pass
- generated answers extending beyond what the retrieved context supports

The project is being iterated around these kinds of cases rather than relying only on successful example questions.

## Private Components

The following are intentionally not published in this showcase repository:

- full application source code
- private knowledge-base contents
- API credentials and environment configuration
- production prompts
- retrieval indexes / embeddings

The public repository focuses on architecture and development methodology.
