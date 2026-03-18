# Agentic RAG Chatbot with LangGraph

An intelligent, stateful AI agent capable of **Retrieval-Augmented Generation (RAG)**, web searching, and tool-assisted reasoning. This project leverages **LangGraph** to create a cyclic agentic workflow, allowing the LLM to decide whether to search the web, query local documents, or perform calculations.

![Agent Graph](./agent%20graph.png)

## Features

* **Agentic Decision Making**: Uses LangGraph to manage state and conditional transitions between nodes.
* **Dual-Source Retrieval**:
    * **Local RAG**: Ingests and queries private documents (Docx/PDF/Text).
    * **Web Search**: Integrates DuckDuckGo for real-time information.
* **Tool Integration**: Built-in mathematical calculator and search tools.
* **Local LLM Support**: Powered by **Ollama** (optimized for `llama3-groq-tool-use`) for privacy and offline capability.
* **Visual Workflows**: Includes graph visualizations of the agent's logic and decision paths.

---

## Architecture

The agent operates as a state machine. It evaluates the user's query and determines the best path forward:

1.  **Categorization**: Does the query need a search, a document lookup, or a direct answer?
2.  **Action**: Executes the selected tool (e.g., `calculator`, `duckduckgo_search`).
3.  **Refinement**: If the information is insufficient, the agent can loop back to gather more data or refine the answer.

### **Workflow Visualizations**
| Main Graph | Conditional Logic |
| :--- | :--- |
| ![Graph](./graph.png) | ![Conditional Graph](./conditional_graph.png) |

---

## 🛠 Tech Stack

* **Framework**: [LangGraph](https://github.com/langchain-ai/langgraph), [LangChain](https://github.com/langchain-ai/langchain)
* **LLM**: Ollama (Model: `llama3-groq-tool-use`)
* **Embeddings**: Ollama Embeddings
* **Tools**: DuckDuckGo Search, Python-based Calculator
* **Environment**: Jupyter Notebook / Python 3.10+

---

## Setup & Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name