---
title: "Hackathon 2025: Handbrake Message Verification"
date: 2025-02-15T12:30:00-05:00
draft: false
tags: ["backend", "ai", "hackathon", "telecom"]
categories: ["Software Engineering"]
author: "Troy Archer"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Building an AI-driven telecommunications message compliance engine during Bandwidth Hackathon 2025."
canonicalURL: "https://tarcher.dev/posts/hackathon-2025-handbrake/"
disableHLJS: false
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
---

# Hackathon 2025: Handbrake Message Verification

During Bandwidth Hackathon 2025, our team of five engineers built Handbrake in 48 hours. Handbrake is an automated system that validates telecommunications message traffic against registered Toll-Free verification campaign profiles to identify campaign drift.

Our project placed 2nd out of 29 team submissions.

## Understanding Campaign Drift

Campaign drift occurs when a business sends messaging content that deviates from its registered Toll-Free verification use case profile. 

For example, a business registers a Toll-Free number for two-factor authentication alerts. If that number subsequently transmits promotional marketing offers, the traffic violates carrier rules.

### Industry Impact

Campaign drift leads to severe operational risks:

* Carrier blocking and message filtering.
* Financial penalties for regulatory non-compliance.
* Brand reputational damage with downstream carrier partners.

Manual message auditing across billions of annual messages is inefficient. Automated detection is necessary to protect network integrity.

## Technical Architecture

Handbrake uses a Flask REST API combined with OpenAI language models and Retrieval-Augmented Generation (RAG) using LangChain and a vector database.

### System Workflow

1. The API receives a JSON payload containing `use_case`, `use_case_summary`, and `message_content`.
2. The service queries the vector database for pre-embedded compliance examples relevant to the requested use case.
3. LangChain constructs an augmented prompt containing the retrieved context examples.
4. OpenAI `gpt-4o-mini` analyzes the message and returns a structured JSON payload containing a confidence score and deduction rationale.

### Prompt Engineering and RAG Integration

```python
# Query vector store for similar use case context
relevant_examples = message_validator.get_relevant_examples(
    data['message_content'],
    data['use_case']
)

context = "\n".join([
    f"Example {i+1}: {example[0].page_content}"
    for i, example in enumerate(relevant_examples)
])

# Enforce strict JSON output schema
developer_prompt = f"""You are a discriminator application validating telecommunications messaging compliance.
Compare message_content against use_case and use_case_summary.

Use case: {data['use_case']}
Use case summary: {data['use_case_summary']}

Reference examples:
{context}

Respond only with JSON containing:
"confidence_score" (int 0-100),
"score_positive_reasons" (array),
"score_deduction_reasons" (array).
"""
```

## Results and Value

Grounding the language model with RAG embeddings eliminated model hallucination and delivered accurate confidence scores. Handbrake provides telecommunications providers with automated enforcement tools to maintain messaging compliance at scale.
