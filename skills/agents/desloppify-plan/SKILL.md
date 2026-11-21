---
name: desloppify-plan
description: >-
  Strategic living plan and backlog triage engine for desloppify. Triage codebase health issues across observe, reflect, organize, and strategy stages; cluster related findings; prioritize high-leverage refactorings; and manage technical debt backlogs. Use when triaging findings, organizing cleanup batches, or managing the living plan. Also triggered by `/desloppify-plan`.
---

# Desloppify Plan: Strategic Triage & Queue Management

The living plan bridges raw detector output and tactical execution. It shapes what `desloppify next` surfaces, groups related defects into batchable refactors, and manages conscious debt trade-offs.

---

## 1. Structured Multi-Stage Triage Protocol

When `desloppify next` surfaces triage stages following a scan or review, execute the 4-phase triage protocol:

```bash
# 1. Observe: Identify broad systemic patterns, smell clusters, and hotspot directories
desloppify plan triage --stage observe \
  --report "Observed high concentration of unused imports in legacy services and duplicate validation logic in auth middleware."

# 2. Reflect: Compare current state against historical fixes and architectural invariants
desloppify plan triage --stage reflect \
  --report "Recent auth refactor resolved session leaks, but error handling across downstream handlers remains unstandardized."

# 3. Organize: Categorize by impact and blast radius into logical clusters
desloppify plan triage --stage organize \
  --report "Prioritizing security issues and contract clarity before addressing non-blocking code elegance."

# 4. Strategy: Lock final prioritization strategy
desloppify plan triage --complete \
  --strategy "Execute Batch 1: Security sanitization; Batch 2: Contract cleanup; Batch 3: Dead code elimination."
```

*Automated triage option (if available):*
```bash
desloppify plan triage --run-stages --runner codex # or claude / rovodev
```

---

## 2. Queue Shaping & Clustering

Do not work on findings randomly. Group related findings into clusters so an engineer or agent can resolve them in a single mental context:

### Create & Manage Clusters
```bash
# View active execution queue
desloppify plan queue

# Group related findings into a named cluster
desloppify plan cluster create "auth-contracts" --matching "contracts::auth/*"

# Scope execution exclusively to a single cluster
desloppify plan focus "auth-contracts"

# Clear cluster focus when complete
desloppify plan focus --clear
```

### Reorder Execution Priorities
Move highest-leverage blockers to the top of the queue:
```bash
# Move a whole cluster to the front of the queue
desloppify plan reorder "auth-contracts" top

# Move specific findings before another item
desloppify plan reorder "<finding_a>" before -t "<finding_b>"
```

---

## 3. Debt Acceptance & Backlog Management

### Defer vs. Permanent Skip (`wontfix`)
- **Temporary Deferral**: Defer low-priority findings out of the immediate execution queue:
  ```bash
  desloppify plan skip "elegance::*"
  ```
- **Conscious Debt Acceptance (`wontfix`)**:
  When an architectural constraint prevents resolving a finding, permanently skip it with explicit rationale and attestation:
  ```bash
  desloppify plan skip --permanent "<finding_id>" \
    --note "Intentional coupling due to third-party SDK constraint" \
    --attest "I have evaluated the architectural trade-off and accepted this debt."
  ```
  > [!WARNING]
  > Permanent skips widen the gap between your **lenient score** and **strict score**. Strict score will penalize this debt until rescinded.

### Inspecting the Broader Backlog
`desloppify next` only pulls items from the active execution queue. To review items not currently staged for execution:
```bash
desloppify backlog --count 10
```
To reopen previously skipped or deferred items:
```bash
desloppify plan reopen "<finding_id>"
```
