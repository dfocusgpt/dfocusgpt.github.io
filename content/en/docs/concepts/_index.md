---
title: Core Concepts
weight: 4
description: What your customers expect and what to deliver.
---

1. Narrow the knowledge gap – make organizational knowledge instantly accessible.
2. Instant service – deliver answers quickly via an AI chatbot.
3. Keep it intuitive – provide only what’s needed at a fair price.

Below is a basic sequence of how user questions are answered.

```mermaid
sequenceDiagram
    autonumber
    loop History
    User->>Chatbot: Question
    Chatbot->>Company KB: Search
    Company KB->>Chatbot: Results
    loop LLM
    Chatbot->>LLM: Prompt (Q + KB + History)
    LLM->>Chatbot: Answer
    end
    Chatbot->>User: LLM answer + sources
    Note right of Chatbot: Store Q&A
    end
```

> Flows may vary by options. Agent handoff and KB management flows are similar.

