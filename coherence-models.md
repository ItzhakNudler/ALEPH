# Coherence Models in ALEPH

This document outlines the primary coherence models integrated into the ALEPH system, describing their structure, theoretical underpinnings, algorithmic foundations, and practical applications.

---

## 🧠 What is Deep Coherence?

Coherence is not merely the grammatical or logical sequence of sentences. It encapsulates the structural, thematic, rhetorical, cognitive, and emotional alignment that gives a conversation its "flow" and intelligibility.

---

## 🔍 1. Entity Grid Models

Entity grids track the behavior of discourse entities across sentences.

### Example Table:

| Sentence | "Brain" | "Model" | "System" |
|----------|---------|---------|----------|
| 1        | subj    | obj     | —        |
| 2        | —       | subj    | obj      |
| 3        | obj     | —       | subj     |

- Features are derived from syntactic role transitions.
- Classification models assess coherence (e.g., Logistic Regression, SVM).
- In ALEPH, this reveals neglected topics and signals drift.

---

## 🔄 2. Centering Theory

Tracks the focus of discourse across utterances:

- **Cb**: Backward-looking center (previous topic).
- **Cf**: Forward-looking centers (potential upcoming topics).

| Transition | Description                                     | Coherence |
|------------|-------------------------------------------------|-----------|
| Continue   | Same Cb and highest-ranked Cf                   | ✅✅✅     |
| Retain     | Same Cb, but new top-ranked Cf                  | ✅         |
| Shift      | New Cb and Cf                                   | ❌         |

Used in ALEPH to track cognitive shifts and flag disjoint transitions.

---

## 🧠 3. Neural Coherence Models

Use transformers (e.g., BERT) to model coherence directly.

### Tasks:
- Next Sentence Prediction (NSP)
- Sentence Ordering
- Cloze-style completion

Embedded into ALEPH for real-time coherence scoring using a sliding window.

---

## 🔗 4. RST-Based Coherence Models

Relies on rhetorical structures like elaboration, contrast, explanation.

- Analyzes RST trees from discourse units (EDUs).
- Detects "support chains" for Nucleus ideas.
- Flags unconnected branches as "abandoned" threads.

---

## 🧭 Model Comparison

| Feature \ Model     | Entity Grid | Centering | Neural (BERT) | RST-Based |
|---------------------|-------------|-----------|----------------|-----------|
| Syntactic Reliance  | High        | High      | Moderate       | High      |
| Semantic Depth      | Low         | Medium    | High           | High      |
| Explainability      | High        | Medium    | Low            | High      |
| Use in ALEPH        | ✅✅        | ✅✅✅    | ✅✅✅✅    | ✅✅✅✅  |

---

## 🧩 Use Case in ALEPH

Example dialogue:
1. "I have a question about fractals in the universe."
2. "Could that relate to consciousness?"
3. "I feel like structures in nature mirror thought patterns."

- Grid and Centering show topic progression.
- Neural model scores as Medium+ coherence.
- RST tree: Analogy → Elaboration → Question.

Outcome: consistent thematic evolution, no mental drift.

---

## ✅ Summary

By integrating multiple coherence frameworks, ALEPH achieves:

- Deep comprehension of discourse.
- Tracking of thematic stability.
- Enhanced resonance detection and adaptive response.