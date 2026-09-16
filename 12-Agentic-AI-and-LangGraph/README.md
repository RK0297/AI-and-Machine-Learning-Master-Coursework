# Module 12: Agentic AI & LangGraph Systems

Welcome to **Module 12: Agentic AI & LangGraph Systems**, part of the **Full-Stack AI & Machine Learning Master Coursework**.

This module covers the theory, architecture, and practical implementation of autonomous AI agents, multi-agent coordination, human-in-the-loop (HITL) safety middleware, stateful graph orchestration with **LangGraph**, and modern tool interoperability via the **Model Context Protocol (MCP)**.

All notebooks are powered by **Groq's high-speed flagship model `llama-3.3-70b-versatile`** and feature **14 high-resolution visual architectural and lifecycle diagrams** embedded directly into the lesson cells.

---

## 🗺️ Curriculum Overview

```
12-Agentic-AI-and-LangGraph
│
├── 🧠 PART 1: AGENTIC AI FOUNDATIONS & PROTOCOLS
│   ├── 01_agent_tools_and_memory.ipynb       ─── Tools, Docstring Schemas, Tavily, InMemorySaver
│   ├── 02_mcp_agent_protocols.ipynb          ─── Model Context Protocol (MCP), STDIO, MultiServerClient
│   ├── 03_multi_agent_coordinator.ipynb      ─── Supervisor Architecture, 3 Subagents, DB Tools, Retries
│   └── 04_dynamic_hitl_agent.ipynb           ─── Dynamic Prompts, RBAC Tool Gates, HITL Interruption
│
└── 🕸️ PART 2: LANGGRAPH STATEFUL ORCHESTRATION
    ├── 05_langgraph_core_stategraph.ipynb     ─── StateGraph, Functional Nodes, Edges, Pregel Supersteps
    ├── 06_langgraph_conditional_routing.ipynb ─── The LLM Router Pattern, ToolNode, tools_condition
    ├── 07_langgraph_state_reducers.ipynb      ─── Channels, Overwrite vs Add Reducers, add_messages
    ├── 08_langgraph_time_travel_and_state_edit.ipynb ─ Checkpoint History, Rewind, State Forking
    └── 09_langgraph_research_assistant_workflow.ipynb ─ Co-STORM Assistant, Send API, Map-Reduce
```

---

## 📚 Notebook Directory & Learning Objectives

| # | Notebook | Focus Area | Architectural Highlight | Key Concepts |
|:---|:---|:---|:---|:---|
| **01** | [`01_agent_tools_and_memory.ipynb`](./01_agent_tools_and_memory.ipynb) | Agent Tools & Memory | Tool Calling & Checkpointer Flowchart + Multi-turn Sequence | `@tool`, Tavily Search, Pydantic type hints, `InMemorySaver`, thread isolation (`thread_id`) |
| **02** | [`02_mcp_agent_protocols.ipynb`](./02_mcp_agent_protocols.ipynb) | Model Context Protocol | Host-Client-Server Diagram + JSON-RPC Protocol Sequence | MCP Primitives (Tools, Resources, Prompts), STDIO transport, subprocess communication, `MultiServerMCPClient` |
| **03** | [`03_multi_agent_coordinator.ipynb`](./03_multi_agent_coordinator.ipynb) | Multi-Agent Coordination | Hierarchical Supervisor Topology + Delegation Sequence | Coordinator pattern, shared `WeddingState`, subagents as callable tools, SQLite queries, MCP retry interceptor |
| **04** | [`04_dynamic_hitl_agent.ipynb`](./04_dynamic_hitl_agent.ipynb) | Dynamic Prompts & HITL | Middleware Interception Pipeline + Approval State Machine | Role-Based Access Control (RBAC), `@wrap_model_call`, `@dynamic_prompt`, `HumanInTheLoopMiddleware`, `Command(resume=...)` |
| **05** | [`05_langgraph_core_stategraph.ipynb`](./05_langgraph_core_stategraph.ipynb) | Core StateGraph Primitives | Topology Flowchart + Superstep Execution Sequence | `TypedDict` schemas, pure node functions, normal vs conditional edges (`Literal`), compiled Pregel engine |
| **06** | [`06_langgraph_conditional_routing.ipynb`](./06_langgraph_conditional_routing.ipynb) | The LLM Router Pattern | Decision Router Flowchart + Dispatch Sequence Diagram | `MessagesState`, `llm.bind_tools()`, `ToolNode`, `tools_condition` edge inspection |
| **07** | [`07_langgraph_state_reducers.ipynb`](./07_langgraph_state_reducers.ipynb) | State Channels & Reducers | Write Conflict vs Reducer Comparison + Message Reconciliation | Parallel fan-out, `InvalidUpdateError`, `Annotated[list, add]`, custom reducers, message updates & `RemoveMessage` |
| **08** | [`08_langgraph_time_travel_and_state_edit.ipynb`](./08_langgraph_time_travel_and_state_edit.ipynb) | Time Travel & Forking | Checkpoint Timeline GitGraph + State Checkpointing Architecture | 3 Pillars of HITL (Approval, Debugging, Editing), `get_state_history`, `update_state()`, branch forking |
| **09** | [`09_langgraph_research_assistant_workflow.ipynb`](./09_langgraph_research_assistant_workflow.ipynb) | STORM Multi-Agent Workflow | End-to-End STORM Pipeline + Interview Sub-Graph Diagram | Perspective generation, HITL persona approval, dynamic fan-out via `Send` API, Map-Reduce memo synthesis |

---

## 🖼️ Visual Architecture Gallery

This module includes **14 native visual diagrams** located in [`images/`](./images/):

1. **Agent Tools & Memory Architecture** (`images/01_agent_tools_memory.png`)
2. **Conversational Memory Lifecycle Sequence** (`images/seq_agent_memory.png`)
3. **MCP Client-Server Architecture** (`images/02_mcp_client_architecture.png`)
4. **MCP Protocol JSON-RPC Sequence** (`images/seq_mcp_protocol.png`)
5. **Multi-Agent Coordinator Hierarchy** (`images/03_multi_agent_coordinator.png`)
6. **Dynamic Middleware & HITL Pipeline** (`images/04_dynamic_hitl_pipeline.png`)
7. **StateGraph Core Nodes & Routing** (`images/05_stategraph_core_nodes.png`)
8. **StateGraph Superstep Lifecycle Sequence** (`images/seq_stategraph_lifecycle.png`)
9. **LangGraph Router Pattern** (`images/06_langgraph_router_pattern.png`)
10. **Router Dispatch Sequence** (`images/seq_router_dispatch.png`)
11. **State Reducers Comparison (Overwrite vs Add)** (`images/07_state_reducers_comparison.png`)
12. **Message Channel Reconciliation Logic** (`images/msg_reducer_reconciliation.png`)
13. **Time Travel Checkpointing & Forking Timeline** (`images/08_time_travel_forking.png`)
14. **Co-STORM Multi-Agent Research Assistant** (`images/09_storm_research_pipeline.png`)

> [!TIP]
> Every diagram cell in the notebooks displays the visual PNG natively at the top and provides an expandable `<details>` section containing the full raw Mermaid syntax underneath for complete reproducibility.

---

## ⚡ Tech Stack & Key Frameworks

- **LLM Engine**: [Groq](https://groq.com/) Cloud Inference
  - Model: `llama-3.3-70b-versatile` (128k context, tool calling, structured outputs)
- **Agent Framework**: [LangGraph](https://langchain-ai.github.io/langgraph/) (`StateGraph`, `MessagesState`, `MemorySaver`, `Send`)
- **Protocol**: [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) (`MultiServerMCPClient`)
- **Search & Retrieval**: [Tavily Search API](https://tavily.com/), Wikipedia Loader
- **Database**: SQLite (`Chinook.db`) for structured SQL tool agents
- **Environment**: Python 3.11+ / 3.12+ with `python-dotenv`

---

## 🚀 Getting Started

### 1. Configure Environment Variables
Create a `.env` file in this directory (or in the repository root):

```env
# Required for all LLM calls
GROQ_API_KEY=gsk_your_groq_api_key_here

# Required for notebooks 01, 03, and 09 (web search tools)
TAVILY_API_KEY=tvly-your_tavily_api_key_here

# Optional: LangSmith Observability
LANGCHAIN_API_KEY=lsv2_pt_your_langchain_key_here
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=Module-12-Agentic-AI
```

### 2. Install Dependencies
Each notebook includes self-contained installation cells, or you can install all required packages at once:

```bash
pip install -U langgraph langchain-groq langchain-community langchain-core tavily-python wikipedia python-dotenv
```

### 3. Run the Notebooks
Open any notebook in JupyterLab, VS Code, or Cursor and execute cells sequentially:

```bash
jupyter lab
```

---

**Author:** Radhakrishna Bharuka  
**Coursework:** Full-Stack AI & Machine Learning Master Coursework
