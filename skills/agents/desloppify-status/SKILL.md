---
name: desloppify-status
description: >-
  Inspect codebase health scores, track progress toward the strict score target (85+), audit wontfix debt gaps, identify top weighted drags, and generate interactive treemaps or visual scorecards. Use when checking desloppify progress, auditing technical debt metrics, or viewing status dashboards. Also triggered by `/desloppify-status`.
---

# Desloppify Status: Health Telemetry & Dashboard

`desloppify-status` surfaces deep diagnostic metrics, evaluates debt gaps between lenient and strict scores, isolates high-leverage weighted drags, and produces visual reports.

---

## 1. Key Metric Definitions

| Metric | Calculation | Purpose / Role |
| :--- | :--- | :--- |
| **Strict Score** | `25% Mechanical + 75% Subjective` *(wontfix counts as open)* | **The North Star**. Represents true uncompromised production health. Target is **≥ 85.0**. |
| **Overall Score** | `25% Mechanical + 75% Subjective` *(lenient — ignores wontfix)* | Shows potential score if all skipped/wontfix debt is accepted. |
| **Objective Score** | `100% Mechanical Detectors` | Pure automated analysis (linters, smells, duplication, security). |
| **Verified Score** | Strict score crediting only scan-verified fixes | Prevents premature credit before full detector re-runs. |
| **Wontfix Gap** | `Overall Score - Strict Score` | Direct quantification of accepted technical debt cost. |

---

## 2. Status & Visualization Commands

### 1. View Full Dashboard
```bash
desloppify status
```
Inspect:
- Progress bar per dimension (File health, Code quality, Security, Elegance, Contracts).
- **Biggest weighted drags**: Pinpoints which specific dimensions are costing the most points on the strict score.
- Coaching recommendations surfaced by the engine.

### 2. Generate Interactive Visualizations
- **Interactive HTML Treemap**:
  ```bash
  desloppify viz
  ```
  Generates an interactive treemap visualizing file sizes, hotspots, and defect density across the codebase.
- **Annotated Terminal Tree**:
  ```bash
  desloppify tree
  desloppify tree --focus src/controllers   # Zoom into a specific directory
  ```

### 3. PR & Commit Telemetry
If tracking a pull request for a cleanup campaign:
```bash
# Preview auto-formatted PR description showing health improvements
desloppify plan commit-log pr

# View history of recorded resolution commits
desloppify plan commit-log history
```

---

## 3. Interpreting Weighted Drags

When `desloppify status` outputs:
```text
Biggest weighted drags:
  - High elegance: -13.41 pts (score 0.0%, 17.9% of subjective pool)
  - Security: -12.50 pts (score 0.0%, 25.0% of mechanical pool)
  - File health: -8.75 pts (score 30.0%, 50.0% of mechanical pool)
```
**Take immediate action**:
1. If top drags are **subjective dimensions at 0.0%**: Trigger `desloppify-review` immediately.
2. If top drags are **security or file health**: Prioritize those clusters in `desloppify-plan` or run `desloppify next` focusing on security.
