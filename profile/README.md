<div align="center">

<img src="../media/banner.svg" alt="Delta Prime" width="800" />

<br /><br />

**Cognition infrastructure. Context rot's cure.**<br />
Building the cognitive backbone for AI through bi-temporal knowledge graphs.

<br />

[Projects](#projects) &nbsp;&bull;&nbsp; [Architecture](#architecture) &nbsp;&bull;&nbsp; [Quick Start](#quick-start)

</div>

<br />

## Features

- **Graph-RAG Context Storage** &mdash; Memgraph + Qdrant for relational, searchable memory
- **Bi-Temporal Tracking** &mdash; Valid time vs. system time history for context evolution  
- **MCP Integrations** &mdash; Drop-in memory layer for Claude Code and other AI agents
- **GraphRAG Clustering** &mdash; Hierarchical summaries with automatic entity extraction

<br />

## Architecture

```mermaid
flowchart TB
    subgraph AGENTS["<b>Agent Layer</b>"]
        direction LR
        A1[Claude Code]
        A2[Custom Agents]
        A3[Workflows]
    end

    subgraph INTERFACE["<b>Interface Layer</b>"]
        direction LR
        I1[MCP Server]
        I2[REST API]
        I3[GraphQL]
    end

    subgraph PROCESSING["<b>Processing Layer</b>"]
        direction LR
        P1[Entity Extraction]
        P2[Embeddings]
        P3[Clustering]
        P4[Bi-Temporal Logic]
    end

    subgraph STORAGE["<b>Storage Layer</b>"]
        direction LR
        S1[(Memgraph<br/>Graph DB)]
        S2[(Qdrant<br/>Vectors)]
        S3[(Redis<br/>Cache)]
    end

    AGENTS --> INTERFACE
    INTERFACE --> PROCESSING
    PROCESSING --> STORAGE
    STORAGE -.->|"context retrieval"| INTERFACE
    
    style AGENTS fill:#1f2937,stroke:#58a6ff,color:#f0f6fc
    style INTERFACE fill:#1f2937,stroke:#a371f7,color:#f0f6fc
    style PROCESSING fill:#1f2937,stroke:#3fb950,color:#f0f6fc
    style STORAGE fill:#1f2937,stroke:#f78166,color:#f0f6fc
```

<br />

## Projects

| Repository | Description |
|------------|-------------|
| **[contextr](https://github.com/delta-prime/contextr)** | External Graph-RAG memory layer with MCP support |
| **specifications** | Bi-temporal AI context and graph clustering standards |
| **adaptors** | Bridge implementations for REST, MCP, and GraphQL |

<br />

## Quick Start

```bash
# Ingest a codebase into persistent memory
uv run python -m cli ingest ./src --session-id my-project

# Semantic search
uv run python -m cli lookup "authentication flow"
```

**Connect Claude Code via MCP:**

```json
{
  "mcpServers": {
    "contextr": {
      "type": "http",
      "url": "http://localhost:8000/mcp"
    }
  }
}
```

<br />

---

<div align="center">
  <sub>MIT License &bull; Delta Prime Labs &bull; 2026</sub>
</div>
