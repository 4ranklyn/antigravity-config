---
name: desloppify-review
description: >-
  Holistic subjective quality evaluation engine for desloppify. Prepare review packets, run blind multi-dimension assessments (design elegance, contracts, error handling, clarity), orchestrate subagents, enforce anti-gaming integrity rules, format findings JSON, and import review scores. Use when subjective dimensions are unassessed (0%), scores need refreshing, or performing code quality reviews. Also triggered by `/desloppify-review`.
---

# Desloppify Review: Subjective Dimension Assessment Protocol

Subjective quality dimensions constitute **75% of the total desloppify health score**. Without subjective assessment, overall and strict scores remain capped at low values regardless of mechanical cleanups.

---

## 1. Integrity & Anti-Gaming Mandates

1. **Strict Blind Scoring**:
   - Assess code quality purely from observed codebase evidence.
   - **Never anchor** to target thresholds, past scores, or lenient targets.
   - Target-matching clustering triggers desloppify auto-resets.
2. **Conservative When Uncertain**:
   - If evidence is mixed or code clarity is ambiguous, score lower and articulate uncertainty in the findings.
3. **Assess All Requested Dimensions**:
   - Every dimension requested in `query.json` must receive an explicit numeric assessment (`0 - 100`).

---

## 2. Review Execution Workflows

### Option A: Subagent / Agent Delegation Protocol (Recommended in Antigravity)

#### 1. Generate Review Packet
```bash
desloppify review --prepare
```
This updates `query.json`, detailing:
- The active dimensions to score (e.g., `high_elegance`, `contracts`, `error_resilience`, `clarity`).
- Dimension descriptions, guidelines, and rubric.
- The required JSON findings schema.

#### 2. Run Review Waves
Delegate dimensions to focused subagents in small waves (3–5 concurrent tasks or sequential runs):
- Subagent System Prompt:
  > You are a code quality reviewer. You will be given a codebase path, a set of dimensions to score, and what each dimension means. Read the code, score each dimension 0-100 from evidence only, and return JSON in the required format. Do not anchor to target thresholds. When evidence is mixed, score lower and explain uncertainty.

#### 3. Output Schema Specification
Consolidate review results into a structured JSON file (e.g., `review_findings.json`):

```json
{
  "assessments": {
    "contracts": 75,
    "error_resilience": 60,
    "clarity": 70
  },
  "findings": [
    {
      "dimension": "contracts",
      "identifier": "missing_precondition_guard",
      "summary": "Public API route handler accepts raw payload without schema validation",
      "related_files": ["src/api/handler.ts"],
      "evidence": ["req.body passed directly to downstream database query on line 42"],
      "suggestion": "Introduce Zod/Joi schema validation before handler execution",
      "confidence": "high"
    }
  ]
}
```
*Note: If no defects are found in a dimension, pass `"findings": []` for that dimension.*

#### 4. Import & Apply Review
```bash
desloppify review --import review_findings.json \
  --attested-external \
  --attest "I validated this review was completed without awareness of overall score and is unbiased."
```
Once imported, run:
```bash
desloppify scan
```
This binds findings to the living plan and recalculates the weighted strict score.

---

### Option B: Automated CLI Runner (When Codex/Claude/Rovodev runners configured)
```bash
desloppify review --run-batches --runner codex --parallel --scan-after-import
```

---

## 3. Review Troubleshooting & Safeguards

- **Batch Output Extensions**: Keep raw agent outputs as `batch-N.raw.txt`. Reserve `.json` extensions strictly for the merged final import file.
- **Fail-Closed Import**: Desloppify validates findings against `query.system_prompt`. If a batch contains invalid dimensions or missing keys, the import aborts to protect state integrity. Use `--allow-partial` only if salvage is strictly necessary.
- **Resetting Baselines**: To discard corrupted or compromised subjective baselines:
  ```bash
  desloppify scan --reset-subjective
  ```
