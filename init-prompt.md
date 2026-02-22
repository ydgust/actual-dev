Do NOT write or modify any code.

I want a high-level understanding of the system slice relevant to this feature.

Given this codebase and the files I am looking at, explain:

1. Entry points
   - What starts this process?
   - What triggers this flow?

2. Execution flow (happy path only)
   - Step-by-step, which components call which
   - Where control decisions are made

3. Boundaries & side effects
   - External systems involved
   - IO, network, database, filesystem interactions

4. State
   - What state is persisted?
   - What state is derived or transient?
   - What must survive restarts or failures?

5. Failure & retry behavior
   - What can fail?
   - What is safe to retry?
   - What must happen exactly once?

6. Invariants
   - What assumptions must always hold true?
   - What would break if violated?

7. Phase mapping
   - Break the flow into clear phases (validate, execute, persist, cleanup, etc.)

Keep explanations conceptual and concise.
Avoid implementation details and code snippets unless absolutely necessary.
