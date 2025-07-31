# ALEPH - Cognitive Dialogue: File 4 - Semantic and Cognitive Processing (Expanded)

## Conceptual Clarifications and Software Representations

### 1. Core Concepts

#### Previous Mention
- **Definition**: Reference to an entity or idea previously introduced in the conversation.
- **Software Representation**: 
  - `mention_id`, `coreference_chain`
  - Token span and dependency links
- **Methods**: Coreference resolution using models like SpanBERT, token similarity matching.

#### Theme
- **Definition**: Central topic linking a group of ideas or mentions over time.
- **Software Representation**: 
  - `theme_id`, cluster of topic embeddings
- **Methods**: Topic modeling (LDA, BERTopic), clustering.

#### Autonomous Reference
- **Definition**: References relying on user’s internal context, not established in dialogue.
- **Software Representation**: 
  - Unfamiliarity score, implicit context tagging
- **Methods**: Out-of-context detection, NER/Entity Linking.

### 2. Anaphora Resolution

#### Ambiguous Reference
- **Definition**: Phrases like “he”, “this”, “such”, requiring context to resolve.
- **Detection Techniques**:
  - Coreference Resolution
  - Dependency parse trees
  - Ambiguity score computation

### 3. Indirect References
- **Definition**: Ideas referenced through metaphors or indirect framing.
- **Representation**: 
  - Implicit context tags, semantic linking.
- **Methods**: Inference models, LSA, NLI, concept similarity graphs.

### 4. Cognitive Jumps
- **Definition**: Abrupt shifts to unrelated topics or abstract levels.
- **Representation**: 
  - Semantic distance spikes, transition nodes
- **Methods**: Embedding distance, anomaly detection.

### 5. Complex Concepts
- **Definition**: Multilayered concepts used across disciplines.
- **Representation**: 
  - Composite nodes, ontology graph expansions.
- **Methods**: Ontology flattening, recursive decomposition.

### 6. Transitional Ideas
- **Definition**: Concepts that bridge between major thematic ideas.
- **Detection**: Graph betweenness, information flow analysis.

### 7. Depth of Discussion
- **Definition**: The richness and level of conceptual elaboration.
- **Indicators**: Argument layers, inference chains, graph depth.

### 8. Personal Style Analysis

#### Thinking Style
- **Definition**: Analytical, associative, intuitive, etc.
- **Techniques**: Behavior profiling, distributional analysis.

#### Formulation Style
- **Definition**: Syntactic patterns, complexity.
- **Techniques**: Stylometry, POS tag sequencing.

### 9. Idea Consistency
- **Definition**: Thematic coherence and semantic continuity.
- **Techniques**: Semantic drift detection, entailment checking.

### 10. Mental Dispersion
- **Definition**: Frequent topic switching or cognitive scatter.
- **Techniques**: Switching rate analysis, graph fragmentation.

### 11. Immersion Level
- **Definition**: Attention depth and subject engagement.
- **Metrics**: Time on topic, cognitive stability, depth metrics.

### 12. Cognitive Oscillation
- **Detection**: Variation in tone, depth, and speed.
- **Techniques**: Sentiment analysis, temporal discourse markers.

### 13. Discipline/Metaphor Switching
- **Detection**: Domain shift markers, metaphor structure parsing.

---

This file integrates foundational and advanced conceptual representations from the dialogue about semantic parsing, idea structure, and user-model interaction in ALEPH.