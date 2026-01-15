
# 🚀 Agentic RAG with LangChain and Gemini  
### Multi-Source Question Answering System

---

## 🧠 Overview
This project implements an **Agentic Retrieval-Augmented Generation (RAG)** system using **LangChain** and **Google Gemini**.

Unlike traditional RAG pipelines, this system uses an **LLM-driven agent** that can dynamically decide **when** and **which** data source to query—such as a vector database, Wikipedia, or arXiv—based on the user’s question.

The focus of this project is **agent-based orchestration**, real-world debugging, and handling framework + model constraints realistically.

---

## ✨ Key Features
- 🤖 **Agent-based reasoning** using LangChain (v1.x)
- 🔍 **Multi-source retrieval**
  - Vector store (document RAG)
  - Wikipedia (general knowledge)
  - arXiv (research papers)
- 🛠️ **Explicit Gemini-safe tool contracts**
- ⚠️ Handles real-world Gemini tool-calling constraints
- 🧩 Built with modern LangChain architecture (Runnable-based agents)

---

## 🏗️ System Architecture

```text
User Query
    ↓
Gemini Agent (Reasoning)
    ↓
Selects Tool(s)
    ├── Vector Store Retriever
    ├── Wikipedia Search
    └── arXiv Search
    ↓
Tool Observations
    ↓
Final Grounded Answer
````

🔹 Retrieval is **conditional**, not mandatory
🔹 The agent decides whether external knowledge is required

---

## ❓ Why Agentic RAG?

### Traditional RAG

```text
Query → Retriever → LLM → Answer
```

### Agentic RAG (this project)

```text
Query → LLM decides → Tool(s) → Observation → Final Answer
```

### Benefits

* Smarter and selective retrieval
* Reduced unnecessary context injection
* Better handling of mixed queries (factual + research)
* Clear separation between **reasoning** and **retrieval**

---

## 🛠️ Tool Design (Important)

Google Gemini enforces **strict validation rules** for tool schemas.

To ensure stability:

* ✅ All tools are **manually wrapped**
* ✅ Tool names follow **Gemini-safe naming rules**
* ❌ Auto-generated LangChain community tools are **not passed directly**

This prevents runtime failures and makes agent behavior predictable.

---

## 🤖 Gemini Model Choice

The project uses:

```text
models/gemini-2.5-flash
```

### Why?

* Fully supported by the Gemini **v1beta** API
* Stable for tool calling and agent execution
* Avoids model availability and 404 errors

---

## 🧰 Tech Stack

* **Python**
* **LangChain (v1.x)**
* **Google Gemini (ChatGoogleGenerativeAI)**
* **Vector Store** for document retrieval
* **Wikipedia & arXiv APIs**

---

## 🧪 Example Queries

* *“Summarize LangChain and its core concepts”*

<img width="1817" height="682" alt="image" src="https://github.com/user-attachments/assets/d83b6c12-a704-4d55-a640-57d543a301ef" />


---

## 🎯 Project Motivation

This project was built as a **hands-on learning milestone** to deeply understand:

* Modern LangChain agent APIs
* Tool-calling constraints with Gemini
* Real-world GenAI debugging (not tutorial demos)
* Design trade-offs between pipelines and agents

The emphasis is on **system design and decision-making**, not just output quality.

---

## 🔮 Future Improvements

* Migrate agent logic to **LangGraph** for better state control
* Add evaluation metrics for retrieval quality
* Support switching between **Gemini and local LLMs (Ollama)**
* Convert notebook implementation into a production-ready service

---

