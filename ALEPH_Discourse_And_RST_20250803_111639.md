# ALEPH - Discourse Structuring & RST Foundation

This document expands on key components of discourse-level understanding and rhetorical structuring in the ALEPH system.

---

## 1. Textual Units and Rhetorical Functions

### 1.1 Textual Unit (Rhetorical Segment)
**Definition**: A distinguishable segment of text or dialogue that conveys an intentional communicative act.
- May be a sentence, clause, phrase, or question.
- Forms the base for rhetorical analysis.

**Representation**:
```json
{
  "id": "unit_023",
  "text": "לכן אפשר לראות בתודעה ביטוי חלקי של דעת.",
  "type": "declarative_statement",
  "tokens": [...],
  "embedding": [...],
  "rhetorical_function": "Conclusion",
  "discourse_position": {
    "start_char": 1021,
    "end_char": 1062
  }
}
```

**Examples**:
- Assertion: "דעת היא יותר מתודעה."
- Question: "מהי מהות פנימית?"

---

### 1.2 Rhetorical Functions
Defined as the intended discourse-level function a textual unit serves.
- Examples: **Background**, **Elaboration**, **Contrast**, **Justification**, **Conclusion**, **Evaluation**

---

## 2. EDU Identification

**Elementary Discourse Units** (EDUs) are the atomic segments used in RST analysis.

**Algorithms**:
- Rule-Based parsing of clauses and sentence boundaries
- BIO Tagging using models like BERT
- BiLSTM w/ Attention Segmenters

---

## 3. Nucleus and Satellite Detection

**Definitions**:
- **Nucleus**: The central, meaning-carrying unit.
- **Satellite**: Provides support or detail.

**Techniques**:
- RST Tree Parsers (Tree-LSTM, Transition-based)
- Attention scoring models
- Contextual Embedding Comparison

---

## 4. Discourse Focus and Topical Drift

### 4.1 Focus of Attention
Focus tracked through:
- Topic continuity
- Central term recurrence
- Rhetorical emphasis

### 4.2 Mental Drift
Sudden shifts in concept clusters or rhetorical structures.

Detection via:
- Embedding cluster shifts
- Topic segmentation
- Discourse anomaly scores

---

## 5. Coherence & Plausibility

**Definition**: Probability that a given textual segment follows naturally from its predecessor.

Examples:
- High coherence: Explanation → Conclusion
- Low coherence: Disconnected assertions

Models used:
- NSP (Next Sentence Prediction)
- Entity Grid
- GPT-based scoring

---

## 6. Implementation Context in ALEPH

RST is partially implemented using:
- Custom segmenters
- Multi-layer context embedding
- Flow-based graph propagation

Future components will include:
- Full rhetorical relation detection
- Real-time discourse map generation

