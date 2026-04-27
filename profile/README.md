<div align="center">

<img src="../media/banner.svg" alt="Delta Prime" width="800" />

### *Cognition without continuity is just computation.*

[The Problem](#the-problem) &nbsp;&bull;&nbsp; [Philosophy](#philosophy) &nbsp;&bull;&nbsp; [Cognitive Stack](#the-cognitive-stack) &nbsp;&bull;&nbsp; [Contact](#contact)

</div>

## The Problem

> *"Current systems create a category error: they apply cognitive decay to factual claims, or treat facts and experiences with identical update mechanics."*
> &mdash; [Roynard, 2026](https://arxiv.org/abs/2604.11364)

AI agents forget. Context windows overflow. Facts contradict without reconciliation. This is **context rot** &mdash; the systematic degradation of coherent reasoning as operational history grows.

The root cause: applying uniform persistence to fundamentally different types of knowledge. Gaussian decay is correct for experiences. It's wrong for facts.

## Philosophy

We implement the [four-layer cognitive decomposition](https://arxiv.org/abs/2604.11364) that identifies the missing knowledge layer in cognitive architectures:

| Layer | Persistence Semantics | Examples |
|-------|----------------------|----------|
| **Memory** | Ebbinghaus decay &mdash; experiences fade | "User asked about auth on 2026-04-21" |
| **Knowledge** | Indefinite supersession &mdash; facts persist until contradicted | "OAuth tokens expire in 30 days" |
| **Wisdom** | Evidence-gated revision &mdash; beliefs update on evidence, not time | "This team ships on Fridays" |
| **Intelligence** | Ephemeral inference &mdash; per-session working memory | "For this query, I considered A, B, C" |

Different knowledge types require different update mechanics. A fact shouldn't decay like a memory. A pattern shouldn't update like an observation. Contradictions create supersession edges, not silent overwrites.

<br />

## The Cognitive Stack

<table>
<tr>
<td width="50%">

### Memory
*Experiences that fade*

```mermaid
flowchart LR
    subgraph MEMORY["Memory Layer"]
        direction TB
        P[Passages] --> G[(Graph)]
        V[Events] --> G
        U[Utterances] --> G
        G --> S[(Vectors)]
    end
    
    style MEMORY fill:#0d1117,stroke:#58a6ff
```

Raw experience storage: passages, events, utterances. Ebbinghaus decay — experiences fade with time.

</td>
<td width="50%">

### Knowledge
*Facts that persist*

```mermaid
flowchart LR
    subgraph KNOW["Knowledge Layer"]
        direction TB
        C[Claims] --> F[Facts]
        F --> CI[Citations]
        CI --> G[(Graph)]
    end
    
    style KNOW fill:#0d1117,stroke:#a371f7
```

Extracted claims promoted to facts. Indefinite supersession &mdash; facts persist until contradicted, not until they age.

</td>
</tr>
<tr>
<td width="50%">

### Wisdom
*Beliefs that revise*

```mermaid
flowchart LR
    subgraph WISDOM["Wisdom Layer"]
        direction TB
        P[Patterns] --> H[Hierarchies]
        H --> B[Beliefs]
        B --> S[Summaries]
    end
    
    style WISDOM fill:#0d1117,stroke:#3fb950
```

GraphRAG clustering surfaces emergent patterns. Beliefs update on evidence shift, not on time.

</td>
<td width="50%">

### Intelligence
*Ephemeral reasoning*

```mermaid
flowchart LR
    subgraph INTEL["Intelligence Layer"]
        direction TB
        Q[Query] --> R[ReasoningChain]
        R --> CR[Crystallizations]
        CR --> K[(Knowledge)]
    end
    
    style INTEL fill:#0d1117,stroke:#f78166
```

Per-session reasoning chains. Ephemeral by design &mdash; only crystallized conclusions survive the session.

</td>
</tr>
</table>

<br />

### Meta-Memory
*Provenance, time-travel, reflection*

```mermaid
flowchart LR
    subgraph META["Meta-Memory"]
        direction TB
        P[Provenance] --> T[Time-Travel]
        T --> R[Reflection]
        R --> H[History]
    end
    
    style META fill:#0d1117,stroke:#d29922
```

Cross-cutting capability spanning all four layers. Enables metacognition:
- **Provenance**: "Why do I believe X?" &mdash; full citation chain to source
- **Time-travel**: "What did I know last Tuesday?" &mdash; query historical state
- **Reflection**: Agents store observations about their own cognition

Bi-temporal tracking means every fact knows *when it was true* vs *when we learned it*.

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
            direction TB
            MEM[Memory]
            KNOW[Knowledge]
            WIS[Wisdom]
            INTEL[Intelligence]
            META[Meta-Memory]
            
            MEM --> KNOW
            KNOW --> WIS
            WIS --> INTEL
            META -.-> MEM
            META -.-> KNOW
            META -.-> WIS
            META -.-> INTEL
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
    style META fill:#1f2937,stroke:#d29922,color:#f0f6fc
```

<br />

## Coming Soon

<div align="center">

*We're building in stealth. First repositories drop soon.*

Watch this space &mdash; or [reach out](#contact) if you'd like an early look.

</div>

---

<p align="center">
  <img src="../media/footer.svg" width="800">
</p>

<p align="center">
  <i>"Cognition infrastructure. Context rot's cure."</i>
</p>

<p align="center">
  <sub>Delta Prime Labs &bull; 2026</sub>
</p>
