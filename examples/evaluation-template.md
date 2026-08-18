# RAG Evaluation Template

This template can be used to review retrieval and response quality during development.

## Test Case

**User question**

```text
[Question]
```

**Expected information need**

```text
[What a useful answer should cover]
```

## Retrieval Review

**Retrieved chunks**

```text
1. [Source / chunk summary]
2. [Source / chunk summary]
3. [Source / chunk summary]
```

**Retrieval quality**

- Relevant context retrieved: Yes / Partly / No
- Important context missing: Yes / No
- Irrelevant context present: Yes / No
- Duplicate / near-duplicate retrieval: Yes / No

**Notes**

```text
[Why retrieval succeeded or failed]
```

## Response Review

**Generated answer**

```text
[Answer]
```

**Evaluation**

- Consistent with retrieved context: Yes / Partly / No
- Covers the main question: Yes / Partly / No
- Introduces unsupported claims: Yes / No
- Needs retrieval or prompt adjustment: Yes / No

**Next change to test**

```text
[Chunking / retrieval / context / prompt adjustment]
```
