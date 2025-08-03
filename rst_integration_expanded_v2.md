
# Expanded Implementation of RST (Rhetorical Structure Theory) in ALEPH

## 1. Overview

Rhetorical Structure Theory (RST) is a linguistic framework that analyzes the relationships between units of discourse, focusing on how segments of text support, elaborate, or contrast with each other to form coherent structures. In ALEPH, RST serves as a fundamental mechanism to understand, model, and support high-level reasoning over user dialogues and textual corpora.

This expanded documentation details how RST is integrated and operationalized within ALEPH across several critical dimensions.

---

## 2. Identification of Elementary Discourse Units (EDUs)

### Conceptual Definition:
An EDU is the smallest unit of discourse that expresses a single coherent idea, typically a clause or sentence. 

### Implementation in ALEPH:
- **Segmentation Model**: ALEPH uses a Transformer-based model, fine-tuned on annotated RST corpora (e.g., RST-DT), to segment user text into EDUs.
- **Linguistic Cues**: The segmentation engine relies on syntactic signals (punctuation, subordinating conjunctions), discourse markers, and cue phrases.
- **Neural Augmentation**: Contextual embeddings (from models such as RoBERTa or T5) are used to distinguish clause boundaries and avoid over-segmentation.

---

## 3. Classification of Rhetorical Relations

### Conceptual Definition:
Rhetorical relations define the function between two EDUs — such as Elaboration, Cause, Contrast, etc.

### Algorithms Used:
- **BERT-based Classifier**: Given a pair of EDUs, the model predicts the most probable relation among 30+ standard RST relations.
- **Relation Embedding Matching**: Pre-trained relation vectors are matched against EDU pairs using cosine similarity to guide classification.
- **Bayesian Confidence Modeling**: The classifier outputs a probability distribution over potential relations; a confidence score is used to defer ambiguous links for additional context.

### Example:
```
EDU1: "The experiment failed."
EDU2: "Because the temperature was too low."
→ Relation: Cause
```

---

## 4. Nucleus and Satellite Assignment

### Conceptual Definition:
In RST, the nucleus contains the central idea, and the satellite supports or qualifies it.

### ALEPH Implementation:
- **Semantic Weighting**: Each EDU is scored for centrality using metrics like TF-IDF weight, discourse prominence, and attention weight from transformer layers.
- **Learned Rules**: A hybrid symbolic-statistical layer applies rules like "causes are often satellites" to disambiguate structural roles.
- **Structural Learning**: Models are trained on RST trees with gold-standard nucleus/satellite labels.

---

## 5. Real-Time RST Tree Construction

### Tree Building in ALEPH:
- **Greedy Bottom-Up Parser**: The system iteratively combines the most coherent EDU pairs using predicted relation strengths.
- **Beam Search with Attention**: In ambiguous contexts, beam search tracks multiple candidate trees and selects the highest-scoring structure.
- **Temporal Tagging**: Each node is timestamped, allowing backward/forward traversal of the evolving discourse structure.

### Visualization:
Trees are rendered in ALEPH’s internal debug UI and logged in a graph-based structure for long-term memory modules.

---

## 6. Depth, Resonance, and Integration

### Measuring Resonance:
- **Deep Nucleus Anchoring**: The central Nucleus is tracked across trees to observe if ideas gain consistent satellite support (resonance) or degrade (dispersal).
- **Cohesion Tracking**: Consistent use of satellites like Elaboration or Example signals increasing depth of thought.

### Integration with Other Modules:
- **Resonance Engine**: Connects the tree structure to the echo patterns identified in long-term learning.
- **Memory Layer**: RST trees are indexed by discourse situation and retrieved during query-time for thematic continuity.
- **Discourse Goal Modeling**: Allows ALEPH to reason about user intent, progression, and goal fulfillment via the discourse structure.

---

## 7. Error Handling and Fallback

When ambiguity is too high:
- **User Clarification Loop**: ALEPH generates clarifying questions based on competing RST trees.
- **Fallback to Coherence Modeling**: If RST parsing fails, fallback coherence models (e.g., entity grid) are used to maintain continuity.

---

## 8. Summary

The integration of RST in ALEPH provides:
- Deep modeling of user intent, structure, and semantic priorities.
- Real-time feedback for maintaining or redirecting cognitive flow.
- A basis for resonance, insight detection, and thematic development.

RST is not an isolated tool in ALEPH but a central piece in the orchestration between cognition, discourse, memory, and reasoning.

