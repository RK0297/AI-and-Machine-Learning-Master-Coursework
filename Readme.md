# Full-Stack AI & Machine Learning Master Coursework

Comprehensive coursework spanning Machine Learning, Deep Learning, Natural Language Processing, Retrieval-Augmented Generation (RAG), and Agentic AI Systems with LangGraph and MCP.

---

## 🗺️ Master Curriculum Map

```
00 Docker & Infrastructure ─────── Containerization for reproducible AI/ML environments
        │
01 ML Fundamentals ────────────── Scikit-Learn workflows & rigorous model evaluation
        │
02 Supervised Learning ────────── Linear/Logistic Regression, KNN, Trees, Random Forests, SVM
        │
03 Unsupervised Learning ──────── K-Means clustering, PCA dimensionality reduction
        │
04 Feature Engineering ────────── Imputation, scaling, encoding, ColumnTransformer pipelines
        │
05 Classical NLP ──────────────── Text vectorization (BoW, TF-IDF), Naive Bayes spam filter
        │
06 Recommender Systems ────────── Collaborative filtering, user-item matrices, SVD
        │
07 Deep Learning & NNs ────────── Keras, regression/classification, CNNs, Optimization, Attention & GANs
        │
08 Transformers & BERT ────────── Hugging Face transformers, hidden states, tokenizers, heads
        │
09 RAG & Vector Search ────────── RAG math from scratch, ChromaDB, chunking & hybrid retrieval
        │
10 Advanced RAG & Graphs ──────── Neo4j Knowledge Graphs, Self-Querying, RAGAS & LangSmith eval
        │
11 Fine-Tuning & Inference ────── LoRA, QLoRA, 4-bit PEFT quantization + KV cache notes
        │
12 Agentic AI & LangGraph ─────── StateGraph, reducers, MCP tools, HITL, Multi-agent coordinator
        │
13 Streaming & Big Data ───────── Apache Kafka broker, ZooKeeper, PySpark Structured Streaming
        │
14 MLOps & Model Deployment ───── FastAPI, Django, and production ML pipelines
```

---

## 📁 Repository Directory Structure

| Module | Directory | Key Topics & Hands-on Implementation | Co-located Lecture Materials |
|:---|:---|:---|:---|
| **00** | [`00-Docker-Fundamentals`](./00-Docker-Fundamentals/) | Containerization, multi-container networking, Compose | `Docker_Basics.pdf`, `Docker_Networks_and_Composition.pdf` |
| **01** | [`01-ML-Fundamentals`](./01-ML-Fundamentals/) | Scikit-learn basics, ROC/AUC, PR curves, K-Fold CV, Error metrics | `1. The Machine Learning Landscape.pdf` |
| **02** | [`02-Supervised-Learning`](./02-Supervised-Learning/) | Linear & Logistic Regression, KNN, Decision Trees, SVM, GridSearchCV | Classification, Linear Models, SVMs, Decision Trees, Naive Bayes, Random Forests PDFs |
| **03** | [`03-Unsupervised-Learning`](./03-Unsupervised-Learning/) | K-Means clustering, Elbow method, PCA projection | Dimensionality Reduction & Unsupervised Learning PDFs |
| **04** | [`04-Feature-Engineering-and-Pipelines`](./04-Feature-Engineering-and-Pipelines/) | Imputers (Simple/KNN), Scalers, One-Hot, ColumnTransformer, Joblib | Pipeline artifacts (`pipe.joblib`) |
| **05** | [`05-Classical-NLP`](./05-Classical-NLP/) | Bag of Words, TF-IDF, NLTK text cleaning, Naive Bayes spam classifier | NLP vectorization guides |
| **06** | [`06-Recommender-Systems`](./06-Recommender-Systems/) | MovieLens 100k, User-Item cosine similarity, SVD matrix factorization | `Recommender Systems.pdf`, `u.data`, `u.item` |
| **07** | [`07-Deep-Learning-and-Neural-Networks`](./07-Deep-Learning-and-Neural-Networks/) | Keras Sequential models, Dropout, EarlyStopping, MNIST CNNs | **Comprehensive Notes**: Neural Networks, Optimization, Transfer Learning, Attention & GANs PDFs |
| **08** | [`08-Transformers-and-BERT-Foundations`](./08-Transformers-and-BERT-Foundations/) | Hugging Face BERT, hidden states extraction, NER, classification head | `bert_flashcards.html` (Attention & Transformer theory referenced from Module 07) |
| **09** | [`09-RAG-and-Vector-Search-Fundamentals`](./09-RAG-and-Vector-Search-Fundamentals/) | Raw math RAG (dot products, cosine similarity), ChromaDB, HF Hub | `Hugging_Face.pptx`, RAG Foundations & Retrieval PDFs, `Vector_Search_Fundamentals.pptx` |
| **10** | [`10-Advanced-RAG-and-Knowledge-Graphs`](./10-Advanced-RAG-and-Knowledge-Graphs/) | Neo4j Graph RAG, SelfQueryRetriever, LangSmith RAGAS evaluation | `KV_and_Graph_DB_Notes.pdf`, `Pinecone__Vector_Database.pdf`, `AWS_EC2.pdf` |
| **11** | [`11-Fine-Tuning-and-Inference-Optimization`](./11-Fine-Tuning-and-Inference-Optimization/) | LoRA, QLoRA 4-bit NF4 fine-tuning on OPT-350M, PEFT adapters | Architecture diagrams, `[PLACEHOLDER] KV_Cache_and_Inference_Optimization_Notes.pdf` |
| **12** | [`12-Agentic-AI-and-LangGraph`](./12-Agentic-AI-and-LangGraph/) | LangGraph `StateGraph`, Reducers, MCP protocols, Multi-Agent Coordinator, HITL, Time Travel | Multi-server MCP, Chinook DB, `[PLACEHOLDER] Agentic_AI_StateGraph_and_Reflection_Notes.pdf` |
| **13** | [`13-Data-Engineering-and-Streaming`](./13-Data-Engineering-and-Streaming/) | Apache Kafka broker, ZooKeeper, PySpark Structured Streaming JSON | `Big_Data_Technologies.pdf`, `Database_Management_Fundamentals.pdf`, `Time_Series_Fundamentals.pdf` |
| **14** | [`14-Model-Deployment-and-MLOps`](./14-Model-Deployment-and-MLOps/) | FastAPI to Django deployment pipelines, production monitoring | `01_Production_MLOps.pptx`, `02_FastAPI_to_Django_Deployment.pptx` |

---

## 🤖 Module 12: Agentic AI & LangGraph Roadmap

Module 12 integrates end-to-end agentic workflows powered by **Groq (`llama-3.3-70b-versatile`)**, **LangGraph**, and **Model Context Protocol (MCP)** with 14 visual architecture and lifecycle diagrams:

1. **[`01_agent_tools_and_memory.ipynb`](./12-Agentic-AI-and-LangGraph/01_agent_tools_and_memory.ipynb)**: Custom `@tool` schemas, Tavily live web search integration, docstrings as LLM specifications, and thread-scoped conversational memory checkpoints via `InMemorySaver`.
2. **[`02_mcp_agent_protocols.ipynb`](./12-Agentic-AI-and-LangGraph/02_mcp_agent_protocols.ipynb)**: Model Context Protocol (MCP) client-server architecture, local Python STDIO subprocess tool execution, remote MCP servers, and `MultiServerMCPClient`.
3. **[`03_multi_agent_coordinator.ipynb`](./12-Agentic-AI-and-LangGraph/03_multi_agent_coordinator.ipynb)**: Hierarchical Multi-Agent orchestration with shared `WeddingState(AgentState)` schema, 3 specialized subagents (Travel, Venue, Playlist), Chinook SQLite DB, and MCP exponential backoff retry interceptors.
4. **[`04_dynamic_hitl_agent.ipynb`](./12-Agentic-AI-and-LangGraph/04_dynamic_hitl_agent.ipynb)**: Dynamic system prompts (`@dynamic_prompt`), RBAC tool permissions based on authentication state (`@wrap_model_call`), and Human-in-the-Loop (HITL) email interrupt approval/rejection via `Command(resume=...)`.
5. **[`05_langgraph_core_stategraph.ipynb`](./12-Agentic-AI-and-LangGraph/05_langgraph_core_stategraph.ipynb)**: Low-level `StateGraph` core primitives, `TypedDict` state channels, pure functional nodes, normal edges, conditional edge routing with `Literal`, and Pregel superstep execution.
6. **[`06_langgraph_conditional_routing.ipynb`](./12-Agentic-AI-and-LangGraph/06_langgraph_conditional_routing.ipynb)**: The LLM Router Pattern, `MessagesState`, binding arithmetic tools to Groq Llama-3.3-70b, prebuilt `ToolNode`, and conditional branching via `tools_condition`.
7. **[`07_langgraph_state_reducers.ipynb`](./12-Agentic-AI-and-LangGraph/07_langgraph_state_reducers.ipynb)**: State channels and update mechanics: default overwrite vs `Annotated[list, add]` reducers, parallel node write conflict resolution, custom reducers, and message deduplication/pruning with `add_messages` & `RemoveMessage`.
8. **[`08_langgraph_time_travel_and_state_edit.ipynb`](./12-Agentic-AI-and-LangGraph/08_langgraph_time_travel_and_state_edit.ipynb)**: Checkpointing timeline inspection (`get_state_history`), state rewinding, in-place state mutation with `update_state()`, and replaying execution along forked timeline branches.
9. **[`09_langgraph_research_assistant_workflow.ipynb`](./12-Agentic-AI-and-LangGraph/09_langgraph_research_assistant_workflow.ipynb)**: Production STORM-inspired multi-agent research workflow: Pydantic perspective generation, HITL reviewer approval, dynamic Map-Reduce parallelization via `Send` API, Tavily/Wikipedia retrieval, and section-by-section report synthesis.

---

## 🚀 Quick Start

### 1. Clone the Unified Repository
```bash
git clone https://github.com/RK0297/Generative-AI-and-RAG-Coursework.git
cd Generative-AI-and-RAG-Coursework
```

### 2. Environment Setup
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

pip install -r requirements.txt
```

### 3. API Keys Configuration
Copy `.env.example` to `.env` in the required module folders:
```env
OPENAI_API_KEY=your_openai_key
GROQ_API_KEY=your_groq_key
TAVILY_API_KEY=your_tavily_key
LANGCHAIN_API_KEY=your_langsmith_key
LANGCHAIN_TRACING_V2=true
```

---

**Author:** Radhakrishna Bharuka  
**Status:** Unified Master Coursework (Modules 00–14)
