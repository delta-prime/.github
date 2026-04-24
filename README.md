<p align="center">
  <img src="media/banner.svg" width="800">
</p>

<p align="center">
  <b>AGENTIC MEMORY ARCHITECTURE | BI-TEMPORAL CONTEXT ENGINEERING</b><br>
  <i>Eliminating context rot through externalized semantic graphs.</i>
</p>

---

### CORE THESIS
**Delta Prime** builds the infrastructure for persistent, high-fidelity AI memory. We solve the "context rot" problem by moving enriched semantic context out of the ephemeral conversation window and into a bi-temporal knowledge graph.

---

### INFRASTRUCTURE STACK

<p align="center">
  <img src="media/icon-stack.svg" width="800">
</p>

---

### FLAGSHIP IMPLEMENTATIONS

<details open>
<summary><b>01 // CONTEXTR</b></summary>
<br>

Our core engine for Graph-RAG based context management. It transforms raw interactions into a structured, searchable, and relational memory bank.

- **RELATIONAL MEMORY:** Deep relationship traversal powered by Memgraph.
- **SEMANTIC RETRIEVAL:** Qdrant-backed vector search with Jina embeddings.
- **TEMPORAL LINEAGE:** Separate tracking for event occurrence and system recording.
- **PROTOCOL NATIVE:** Native support for the Model Context Protocol (MCP).

[View Repository](https://github.com/delta-prime/contextr)
</details>

<details>
<summary><b>02 // RESEARCH & STANDARDS</b></summary>
<br>

- **BI-TEMPORAL SPEC:** Standardizing how AI memory tracks "valid time" vs "system time".
- **GRAPH CLUSTERING:** Hierarchical summarization techniques for infinite context windows.
- **MCP ADAPTORS:** Reference implementations for high-density tool-calling.
</details>

---

### IMPLEMENTATION

```bash
# Ingest codebase into the memory layer
uv run python -m cli ingest ./path/to/source --session-id "sync-01"
```

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=delta-prime&theme=tokyonight&layout=compact&hide_border=true" />
</p>

<br>

<p align="center">
  <i>"STRUCTURING AGENTIC INTELLIGENCE."</i>
</p>
