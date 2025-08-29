---
title: DfocusGPT Data Flow
date: 2024-01-03
weight: 3
description: Basic question-answer flow in DfocusGPT.
---

Below is a basic sequence for answering user questions with company knowledge and LLM.

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

> Details may vary by options.

