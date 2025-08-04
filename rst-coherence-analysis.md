# RST Deep Integration – Coherence Metrics and Discourse Tracking in ALEPH

This document expands on the internal mechanisms used in ALEPH for deep rhetorical structure analysis and discourse tracking, specifically through the lens of Rhetorical Structure Theory (RST), Entity Grid Models, Centering Theory, and sliding-window discourse alignment.

---

## 🧠 Entity Grid Model – Managing Conceptual "Neglect"

### What is "Elapsed Time" in Discourse Context?
In ALEPH, "elapsed time" refers to the number of consecutive discourse windows (e.g., sequences of 3–5 sentences) during which a particular entity is not referenced, explicitly or implicitly. An entity is considered **neglected** if:

- It does not appear as subject or object within a configurable window size.
- It lacks associative support (e.g., via rhetorical satellites).
- It shows zero salience change across multiple turns.

### Consequences of Entity Neglect
Entities marked as "neglected" trigger:
- Attention reevaluation by the Resonance Engine.
- Event hooks in the agent layer to prompt narrative refocus or re-anchoring.

---

## 🔁 Detecting Sharp Shifts in Entity Grids

### What is Considered a "Sharp Shift"?
- Jaccard Similarity between adjacent sentence-level entity sets drops below a defined threshold.
- Entropy spike in entity-role transitions.
- Introduction of multiple high-salience new entities within a short window.

### Algorithms:
- `JaccardSimilarityMatrix(entity_sets[t-1], entity_sets[t])`
- `KL-Divergence(entity_distributions[t], entity_distributions[t-1])`
- `RoleTransitionEntropy(t, t+1)`

These are tracked in a rolling buffer that maintains discourse stability scoring.

---

## 🧭 Discourse Focus Tracking and Centering Shifts

### Implementation in ALEPH
Each agent maintains a **Discourse Focus Map** (DFM), a lightweight graph of entity salience over time. A Centering Shift is detected when:

- The `Cb` (backward-looking center) changes more than `N` times in `M` discourse turns.
- Discontinuities appear in forward-to-backward mappings (`Cf ↔ Cb`).

These trigger cognitive resonance checks and optional user queries.

---

## 📉 Ideational Slopes and Fragmentation Tags

### What is an "Ideational Slope"?
A pattern where conceptual richness or depth sharply decays within a narrative thread. Measured by:

- Drop in supporting rhetorical satellites per nucleus.
- Decline in lexical cohesion within concept clusters.
- Switch to unrelated topics without clear transitions.

**Software Representation:**
```json
{
  "topic": "Meta-Causality",
  "status": "slipping",
  "evidence": ["Entity dropout", "Satellite decay", "Cohesion weakening"]
}
```

---

## 🔄 Entry/Exit Points in the Discourse Map

### What are Conceptual Entry/Exit Points?
- **Entry Point**: When a new nucleus is introduced with support and salience shift.
- **Exit Point**: When no rhetorical links or semantic associations remain for a given idea.

ALEPH tracks these using concept activation traces and sliding salience scoring.

---

## ✅ Consistent Support for Nucleus

### Metric:
```python
support_ratio = satellites_supporting / total_EDUs_linked
if support_ratio < threshold:
    alert("Weak Nucleus")
```

---

## 🔁 Coherence Structure Validation

ALEPH evaluates argument structures based on recognized rhetorical schemas:
- Claim → Reason → Evidence → Conclusion
- Problem → Cause → Solution

Deviation from schema triggers resonance reevaluation or structural hints.

---

## 🌱 Dangling Roots and Abandoned Narratives

EDUs with no inbound RST arcs are considered dangling. These may indicate:
- Unresolved narrative threads.
- Concepts introduced but not elaborated.
- Shallow topical jumps.

---

## Summary

This document serves as a deep-dive technical articulation of how ALEPH uses and extends classical RST and related coherence models to dynamically monitor, validate, and support conceptual continuity and learning resonance in long-term dialogues.