# AI-Safe Development Structure (Framework & Language Independent)

## Purpose
Build real understanding and transferable skill while using AI under tight deadlines.

---

## 1. Fixed Mental Model
Every system has these layers, regardless of language or framework:

- **Orchestration**: flow, state, decisions, retries
- **Execution**: side effects, IO, external calls
- **State**: what must survive crashes or restarts
- **Boundaries**: what must be deterministic vs what may not be

**Rule**: logic that *decides* lives in orchestration, logic that *acts* lives in execution.

---

## 2. One-Page Feature Design (before coding)
Write this every time, in plain text.

- Feature name
- Goal / Non-goals
- Responsibilities (what decides, what executes)
- Steps / phases
- Inputs / Outputs
- Failure modes (retryable vs non-retryable)
- Retry + idempotency strategy

If this is unclear, do not use AI yet.

---

## 3. Determinism & Side-Effect Check
Ask explicitly:
- Does this rely on time, randomness, IO, or external state?
- If yes, isolate it behind a boundary

This applies to all systems, not just workflows.

---

## 4. Coding Loop (Mandatory)
1. **You** write structure only (modules, functions, classes)
2. **AI** fills logic
3. **You** close code and write from memory:
   - control flow
   - data flow
   - failure handling

If you cannot reconstruct it, reopen and repeat.

---

## 5. Phase Mapping
Break any feature into clear phases.

Example pattern:
1. Validate
2. Prepare
3. Execute
4. Transform
5. Persist
6. Verify
7. Cleanup

Each unit of code should map to exactly one phase.

---

## 6. Unit Design Rules
Each unit (function, class, module) must be:
- Single responsibility
- Safe to retry or safely fail
- Free of hidden side effects

If a unit needs to decide *what next*, that logic belongs higher.

---

## 7. Error Handling Template
- Local failure:
  - retryable → retry mechanism
  - non-retryable → fail fast with context
- Global failure:
  - update state
  - notify / surface error

Never improvise error logic.

---

## 8. AI Usage Rules
**Use AI for**:
- reviews
- edge cases
- tradeoff analysis
- explaining why something works

**Do not use AI for**:
- first-pass design
- system structure
- core decision logic

---

## 9. Daily Skill Anchor (15 min)
Answer one in writing:
- What breaks if this process restarts?
- Which parts are safe to retry and why?
- What state is essential vs derived?

---

## 10. Weekly Deepening (30–60 min)
- Pick one shipped feature
- Rebuild pseudocode from memory
- Redraw flow + failure paths
- Compare with implementation

Discomfort = understanding returning.

