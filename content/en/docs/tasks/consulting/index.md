---
title: Agent Console
description: >
  Agents respond to “Connect to agent” requests here.
date: 2024-01-05
weight: 4
---

{{% pageinfo %}}
When a user requests agent handoff, an agent connects automatically or manually and continues the chat.
{{% /pageinfo %}}

1. The user selects “Connect to agent”.
2. The agent starts the session from the waiting list.
3. The middle panel shows the prior user–bot conversation.
4. The user sees “Agent connected”.
5. The agent chats with the user.

![image-1.png](image-1.png)

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
    User->>Chatbot: Request agent handoff
    Chatbot->>User: Ask phone/name
    User->>Chatbot: Provide phone/name
    Chatbot->>Agent: Waiting for connection
    Agent->>Chatbot: Start
    Chatbot->>Agent: Provide chat history
    Agent->>User: Chat or phone
    Note right of Chatbot: Store Q&A
```

Video demo (Korean):

<iframe width="1000" height="700" src="https://www.youtube.com/embed/RW-2kjcbLGI?si=zoV89iY3H3PNS7yk&amp;controls=0&autoplay=1&mute=0&controls=0&loop=1&playlist=RW-2kjcbLGI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
