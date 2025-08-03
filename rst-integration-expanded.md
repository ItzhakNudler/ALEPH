# Integration of Rhetorical Structure Theory (RST) in ALEPH

_Last updated: 2025-08-03 16:43 UTC_

This document details how ALEPH integrates Rhetorical Structure Theory (RST) for discourse understanding and cognitive resonance tracking.

---

## 1. Identifying Elementary Discourse Units (EDUs)

**Definition:** EDUs are minimal units of discourse that represent complete ideas or propositions.

### Conceptual Representation
Each EDU is:
- A short clause or sentence
- Contextually meaningful
- Structurally independent or semi-independent

### Implementation in ALEPH
EDUs are detected through:
- **Syntactic parsing**: Using dependency trees and sentence segmentation
- **Semantic boundary detection**: Fine-tuned transformers (e.g. RoBERTa) trained on discourse-annotated corpora
- **Pointer Networks**: For end-to-end boundary detection

Each EDU is stored as:

```json
{
  "edu_id": "E103",
  "text": "לכן חשוב לממש מנגנון הדהוד.",
  "tokens": [...],
  "embedding": [...],
  "discourse_function": null,
  "position": 45
}
```

---

## 2. Determining Rhetorical Relations

ALEPH uses these approaches:

### A. Pairwise Classification
- **Input**: Pairs of EDUs
- **Model**: Transformer encoder → MLP classifier
- **Output**: Rhetorical label (e.g., Elaboration, Contrast)

### B. Tree Induction
- Uses **shift-reduce parsing** or **neural top-down models**
- Based on [RST-DT treebank](https://aclanthology.org/D14-1084.pdf)
- Ensures coherent hierarchical structure

---

## 3. Building the RST Tree in Real-Time

- Incrementally builds the tree as user input progresses
- Evaluates relations between recent EDU and previous nodes
- Assigns **Nucleus/Satellite** roles dynamically
- Represented as:
  - Directed graph
  - Nodes = EDUs
  - Edges = rhetorical relations

---

## 4. Leveraging Nucleus/Satellite for Resonance Tracking

- **Nucleus**: Core propositions
- **Satellite**: Supporting, elaborative or concessive content

### Analytical Integration
- **Core Stability Index**: Measures if core ideas are reinforced
- **Peripheral Drift**: Detects movement towards marginal ideas
- Enhances ALEPH's ability to:
  - Track argument development
  - Detect mental shifts
  - Increase long-term coherence

---

## 5. Integration with Other ALEPH Layers

### A. Resonance Engine
- Receives full RST tree
- Detects:
  - Echoed cores
  - Dropped threads
  - Metaphorical leaps between nuclei

### B. Memory Layer
- Long-term persistence of central nuclei
- Metadata includes:
  - Timestamp
  - Context tag
  - Historical pattern of recurrence

### C. Agent Layer
- Dynamic agents adapt behavior based on:
  - Current discourse structure
  - Dominant rhetorical strategies (e.g., emphasis, concession)

---

## Future Enhancements
- Support for **multilingual RST parsing**
- Adaptive relation sets beyond standard 30 RST links
- Integration with analogical reasoning across nuclei

---

_This module forms a foundational layer for ALEPH’s cognitive discourse capabilities, enabling semantic, rhetorical, and epistemic coherence tracking in real-time._
