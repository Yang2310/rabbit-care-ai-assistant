# Agent & RAG Evaluation Worksheet

**English** | [简体中文](evaluation-template.zh-CN.md) · [Portfolio](../README.md)

A public example of the **review criteria**, not an actual benchmark result. Fill it only with real test evidence before citing a result in a portfolio.

## 1. Test scope

- Scenario / user request: `[anonymized or synthetic input]`
- Tested build / configuration: `[revision and environment]`
- Test type: scripted deterministic / mock browser / real browser / real provider
- Expected allowed capabilities: `[public evidence / local history / clarification / no-write / other]`
- User restrictions and policy requirements: `[...]`

## 2. Semantic and planning review

- User goals, observations, ambiguities and relations represented faithfully: **Yes / Partly / No**
- All necessary capabilities or obligations considered: **Yes / Partly / No**
- Ambiguity and unsupported scope handled explicitly: **Yes / No**
- Any unsupported assumption or omitted user intent: `[describe]`

## 3. Evidence and retrieval review

- Selected sources and their scope: `[...]`
- Evidence actually relevant and sufficient: **Yes / Partly / No**
- Important evidence missed / redundant retrieval / unsupported claims: `[...]`
- Are citations and retrieved-unit references mechanically valid? **Yes / No**

## 4. Tool and state authority

- Tool requested and actually executed: `[...]`
- Source / identity / time / access authorization correct: **Yes / No**
- Record writes or state revisions explicitly authorized: **Yes / No / Not applicable**
- On failure, was protected state left unchanged? **Yes / No / Not applicable**

## 5. Outcome and limitations

- Structural/schema outcome: `[...]`
- Tool execution outcome: `[...]`
- **Independent human semantic assessment:** `[Pass / Fail / Not reviewed]`
- Observed issue and next test: `[...]`

**Rule:** Scripted-test PASS, JSON validity and an HTTP 200 response do not imply that the model understood the user correctly or that the end-to-end assistant is safe to release.
