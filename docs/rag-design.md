# Public RAG: Knowledge and Retrieval Architecture

**English** | [简体中文](rag-design.zh-CN.md) · [System architecture](architecture.md)

## Beyond “put PDF chunks into a vector DB”

The project treats **source verification, reusable knowledge, retrieval representation and model-side evidence decisions** as distinct engineering responsibilities.

```text
Source research + verified evidence scopes
    ↓
Canonical Knowledge (stable sections / provenance)
    ↓
Retrieval Units (index-ready representation)
    ↓
Embedding provider + indexed Chroma collection
    ↓
Candidate retrieval / follow-up retrieval if justified
    ↓
Selected evidence / grounded post-evidence reasoning
```

A source's topic label or current research-batch position is **not** a safe runtime provenance identifier. Canonical content is managed separately from research workflow metadata. Retrieval units can be rebuilt or re-embedded while preserving their underlying evidence identity.

## Technical decisions

1. **Provenance before embedding:** preserve enough source/scope context to explain why knowledge is accepted and where claims came from. A vector similarity score alone does not establish authority.
2. **Canonicalization before indexing:** consolidate findings into reusable sections, track overlaps, conflicting evidence and deferred coverage rather than indiscriminately treating raw documents as ready-to-answer chunks.
3. **Representation versus knowledge:** the embedding/index representation is downstream of canonical knowledge and can change independently; changing embedding spaces requires staged indexing and validation.
4. **Evidence quality at runtime:** candidate retrieval, refinement/follow-up and evidence selection are separate from final answer generation. When evidence is weak, the agent can seek clarification or acknowledge insufficiency instead of inventing certainty.
5. **Controlled evaluations:** deterministic benchmarks check retrieval traces, provenance links, candidate selection, refinement and index isolation. Real LLM decisions and medical appropriateness remain separate manual-review questions.

## Current scope

The private repository contains real knowledge assets and RAG evaluation infrastructure, with selected public-evidence flows implemented. **This is not a claim that every canonical section is live-indexed, that the default retrieval path has fully switched, or that the full real-model assistant is ready.**

The private source corpus, protected health information, model credentials and raw indexes are intentionally excluded from this public portfolio.
