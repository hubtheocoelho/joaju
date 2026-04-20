# Joaju | Agentic Workflow Orchestrator

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## 1. Executive Summary
Joaju is a desktop-based orchestration engine designed for high-fidelity SDLC (Software Development Life Cycle) automation. It implements a multi-agent architecture to bridge the gap between project management context and local execution, maintaining a strict **Human-in-the-Loop (HITL)** governance model.

## 2. Problem Statement
Generic LLM interfaces lack the statefulness and system-level access required for professional engineering tasks. Joaju solves this by providing a deterministic orchestration layer that manages agentic loops, local CLI interactions, and context retrieval.

## 3. System Architecture
Joaju operates as a hybrid orchestrator, decoupling the execution environment from the reasoning engine.

- **Control Plane (TS/Node.js):** Manages event loops, MCP (Model Context Protocol) tool-calling, and OS-level communication.
- **Reasoning Plane (Python/LangGraph):** Executes complex agentic workflows, utilizing directed acyclic graphs (DAGs) to ensure logical consistency and state management.
- **Communication:** Inter-process communication (IPC) via WebSockets and REST APIs for external data ingestion.

## 4. Tech Stack
| Layer | Technology | Rationale |
| :--- | :--- | :--- |
| **Core Host** | Node.js (TypeScript) | Native MCP compliance and high-performance asynchronous I/O. |
| **Agent Logic** | Python (LangGraph) | Industry standard for stateful, multi-agent graph orchestration. |
| **Protocols** | MCP, JSON-RPC | Standardization of tool-calling and data exchange. |

## 5. Core Features
- **SDLC Automation:** Automated environment setup, ticket-to-code synthesis, and PR review cycles.
- **Context Awareness:** Native integration with **Apoena** for RAG-driven decision making.
- **HITL Governance:** Explicit approval gates for all destructive system actions (e.g., `rm`, `git push`).

---
