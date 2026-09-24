# 🧠 LangGraph Message Router

A LangGraph-based AI chatbot that classifies user messages as either **emotional** or **logical** and routes them to specialized LLM agents using Claude.

The project demonstrates how LangGraph can be used to build a simple state-based AI workflow with classification, routing, and specialized agents.

---

## 🚀 Project Overview

The chatbot analyzes every user message and determines what type of response is required.

### Emotional messages

Messages related to:

- Feelings
- Emotional support
- Personal problems
- Therapy-style conversations

are routed to the **Therapist Agent**.

### Logical messages

Messages related to:

- Facts
- Information
- Logical analysis
- Practical solutions

are routed to the **Logical Agent**.

---

## 🏗️ Architecture

```text
                 User Message
                      │
                      ▼
              ┌──────────────┐
              │  Classifier  │
              └──────┬───────┘
                     │
                     ▼
                ┌─────────┐
                │ Router  │
                └────┬────┘
                     │
            ┌────────┴────────┐
            │                 │
            ▼                 ▼
    ┌──────────────┐   ┌──────────────┐
    │  Therapist   │   │   Logical    │
    │    Agent     │   │    Agent     │
    └──────┬───────┘   └──────┬───────┘
           │                  │
           └────────┬─────────┘
                    ▼
               Final Response
