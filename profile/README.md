<div align="center">

<img src="../media/banner.svg" alt="Delta Prime" width="800" />

<br /><br />

**Cognition infrastructure. Context rot's cure.**<br />
Building the cognitive backbone for AI through bi-temporal knowledge graphs.

<br />

[The Problem](#the-problem) &nbsp;&bull;&nbsp; [Philosophy](#philosophy) &nbsp;&bull;&nbsp; [Cognitive Stack](#the-cognitive-stack) &nbsp;&bull;&nbsp; [Projects](#projects)

</div>

<br />

## The Problem

AI agents forget. Every conversation starts from zero. Context windows fill up and overflow. Facts learned yesterday contradict facts learned today, with no mechanism to reconcile them.

**This is context rot** &mdash; the systematic degradation of an agent's ability to reason coherently as its operational history grows. Current systems commit a category error: they apply identical update mechanics to facts, experiences, and inferences, when each requires distinct persistence semantics.

<br />

## Philosophy

We build on the [four-layer cognitive decomposition](https://arxiv.org/abs/2604.11364) proposed by Roynard (2026), which identifies the missing knowledge layer in cognitive architectures:

| Layer | Persistence | What It Holds |
|-------|-------------|---------------|
| **Memory** | Ebbinghaus decay | Raw experiences, observations, context |
| **Intelligence** | Ephemeral | Active inference, working memory |
| **Wisdom** | Evidence-gated | Validated patterns, curated insights |
| **Meta-Memory** | Indefinite | Facts with bi-temporal supersession |

The insight: *different types of knowledge require different update mechanics*. A fact shouldn't decay like a memory. A pattern shouldn't update like an observation. Delta Prime implements this separation.

<br />

## Why Delta Prime

- **Memory** &mdash; Graph + vector storage for entities, facts, and events
- **Intelligence** &mdash; Automatic entity extraction and relationship discovery
- **Wisdom** &mdash; GraphRAG clustering surfaces patterns and hierarchical insights
- **Meta-Memory** &mdash; Bi-temporal tracking knows what you knew, and when

<br />

## The Cognitive Stack

<table>
<tr>
<td width="50%">

### Memory
*Raw context persistence*

```mermaid
flowchart LR
    subgraph MEMORY["Memory Layer"]
        direction TB
        E[Entities] --> G[(Graph)]
        F[Facts] --> G
        V[Events] --> G
        G --> S[(Vectors)]
    end
    
    style MEMORY fill:#0d1117,stroke:#58a6ff
```

Storage of atomic context: entities, facts, events, and their embeddings. The foundation everything else builds on.

</td>
<td width="50%">

### Intelligence
*Understanding through structure*

```mermaid
flowchart LR
    subgraph INTEL["Intelligence Layer"]
        direction TB
        X[Extract] --> R[Relate]
        R --> C[Cluster]
        C --> E[Embed]
    end
    
    style INTEL fill:#0d1117,stroke:#a371f7
```

Entity extraction, relationship discovery, semantic clustering. Turning raw text into structured knowledge.

</td>
</tr>
<tr>
<td width="50%">

### Wisdom
*Patterns and insights*

```mermaid
flowchart LR
    subgraph WISDOM["Wisdom Layer"]
        direction TB
        P[Patterns] --> H[Hierarchies]
        H --> I[Insights]
        I --> S[Summaries]
    end
    
    style WISDOM fill:#0d1117,stroke:#3fb950
```

GraphRAG clustering builds hierarchical summaries. Emergent patterns surface from connected context.

</td>
<td width="50%">

### Meta-Memory
*Context about context*

```mermaid
flowchart LR
    subgraph META["Meta-Memory Layer"]
        direction TB
        VT[Valid Time] --> BT{Bi-Temporal}
        ST[System Time] --> BT
        BT --> H[History]
    end
    
    style META fill:#0d1117,stroke:#f78166
```

Bi-temporal tracking: what was true vs. when we learned it. Enables reasoning about knowledge evolution.

</td>
</tr>
</table>

<br />

### System Architecture

```mermaid
flowchart TB
    subgraph AGENTS["Agents"]
        A1[Claude Code]
        A2[Custom Agents]
    end

    subgraph DELTA["Delta Prime"]
        direction TB
        subgraph COGNITIVE["Cognitive Engine"]
            META[Meta-Memory]
            WISDOM[Wisdom]
            INTEL[Intelligence]
            MEM[Memory]
            
            META --> WISDOM
            WISDOM --> INTEL
            INTEL --> MEM
        end
        
        API[Interface Layer]
    end

    subgraph INFRA["Infrastructure"]
        direction LR
        MG[(Memgraph)]
        QD[(Qdrant)]
        RD[(Redis)]
    end

    AGENTS <--> API
    API <--> COGNITIVE
    COGNITIVE <--> INFRA
    
    style AGENTS fill:#1f2937,stroke:#58a6ff,color:#f0f6fc
    style DELTA fill:#1f2937,stroke:#a371f7,color:#f0f6fc
    style COGNITIVE fill:#161b22,stroke:#3fb950,color:#f0f6fc
    style INFRA fill:#1f2937,stroke:#f78166,color:#f0f6fc
```

<br />

## Projects

| Repository | Description |
|------------|-------------|
| **[contextr](https://github.com/delta-prime/contextr)** | The cognitive memory layer for AI agents |
| **specifications** | Bi-temporal context and knowledge graph standards |
| **adaptors** | Integration bridges for agent frameworks |

<br />

---

<div align="center">
  <sub>MIT License &bull; Delta Prime Labs &bull; 2026</sub>
</div>
