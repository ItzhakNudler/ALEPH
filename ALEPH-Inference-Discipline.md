# ALEPH Methodology Appendix: Assumption & Inference Discipline

## Purpose
This appendix defines the structured methodology for managing assumptions, inferred information, and completion tendencies within ALEPH’s cognitive and agentic architecture. It ensures that all outputs remain traceable, auditable, and aligned with project guardrails.

---

## 1. Core Principles

### 1.1 Explicit Assumptions
All assumptions must be clearly declared in a dedicated section labeled **"Assumptions"** with a rationale for why they are necessary.

### 1.2 Separation of Channels
Responses must be structured into separate, clearly labeled channels:

1. **Facts** – Verified information from reliable sources.
2. **Assumptions** – Hypotheses or inferred details not explicitly provided.
3. **Options/Alternatives** – Viable alternative approaches, each with pros/cons.
4. **Decision Proposal** – A conditional recommendation based on available evidence.
5. **Risks & Tests** – Known risks, uncertainties, and the tests/metrics to mitigate them.

### 1.3 No Unstated Inferences
Inferences are only allowed if explicitly marked as such. No gap-filling without clear identification.

### 1.4 Guardrail Compliance
All responses must respect the configured guardrail flags for the project/session.

---

## 2. Guardrail Configuration (YAML Example)

```yaml
guardrails:
  NO_GAP_FILLING: ENFORCE
  ASSUMPTIONS_REQUIRED: ENFORCE
  VERIFY_WITH_SOURCES: ENFORCE
  CITE_LEVEL: STRICT
  UNCERTAINTY_DISCLOSURE: PREFER
  ASK_CLARIFYING_QUESTIONS: "THRESHOLD:0.6"
  SCOPE_LOCK: "ALEPH.TIME_MODEL"
  EVIDENCE_DIVERSITY: "REQUIRE:≥2_TYPES"
  SAFETY_STRICT: true
```

---

## 3. Example Response Template

```markdown
## Facts
[List verified facts with sources]

## Assumptions
[List assumptions + justification]

## Options/Alternatives
[Option A: Description, pros, cons]
[Option B: Description, pros, cons]

## Decision Proposal
[Recommendation, conditional on evidence]

## Risks & Tests
[List of risks and proposed verification tests]
```

---

## 4. Enforcement in ALEPH

- **Meta-Teacher Agent**: Validates output structure against the channel schema.
- **Curator Agent**: Collects and filters evidence for Facts and Assumptions.
- **Verifier Agent**: Confirms the validity of Facts and flags unverified claims.
- **Scope Classifier**: Ensures content stays within the defined project scope.
- **Guardrail Monitor**: Enforces YAML guardrail rules per response.

---

## 5. Benefits of This Discipline

- Prevents unverified or speculative content from entering the main knowledge graph.
- Maintains transparency between known facts, assumptions, and proposed actions.
- Facilitates decision-making by showing alternatives with documented trade-offs.
- Increases reliability and trust in ALEPH outputs.
- Ensures that risk management is embedded in every stage of reasoning.

---

## 6. Future Enhancements

- Automated scoring of assumption density and risk level.
- Integration with GitHub for version-tracking assumption changes.
- Visualization of inference chains for improved traceability.
