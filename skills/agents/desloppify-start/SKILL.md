---
name: desloppify-start
description: >-
  Initialize codebase health campaigns, configure monorepo boundaries, create isolated git branches, and execute baseline desloppify scans. Use when starting desloppify on a project, running an initial baseline scan, setting up codebase health tracking, or onboarding a repository. Also triggered by `/desloppify-start`.
---

# Desloppify Start: Project Onboarding & Baseline Protocol

Use this skill to establish a deterministic baseline and prepare a repository for structured technical debt cleanup.

---

## 1. Pre-Flight Checklist

Before running scans, enforce these non-negotiable operational hygiene rules:

1. **Branch Isolation**:
   Never execute technical debt cleanup on `main` or `master`.
   ```bash
   git checkout -b desloppify/code-health
   ```
2. **Monorepo / Multi-Project Boundaries**:
   If the workspace contains multiple distinct programs (e.g., `./frontend` and `./backend`), **do not scan the parent repository root**. Target each application individually with `--path` and `--lang`:
   ```bash
   desloppify --lang typescript scan --path ./frontend
   desloppify --lang python scan --path ./backend
   ```
3. **Zone Classification**:
   Verify that test code, vendored packages, and build artifacts do not pollute production scoring:
   ```bash
   desloppify zone show
   # To reclassify unscored test/config directories:
   desloppify zone set test <path>
   desloppify zone set vendor <path>
   ```

---

## 2. Step-by-Step Execution Runbook

### Step 1: Upstream Tool Verification
Run detectors require local toolchains to function without coverage degradation. Inspect that package managers and linters exist:
- **TypeScript/JavaScript**: Ensure `node_modules` are installed (`npm install` or `pnpm install`) and ESLint is executable.
- **Python**: Ensure virtualenv is active and linters/typecheckers are accessible.

### Step 2: Execute Baseline Scan
Run the comprehensive multi-detector scan:
```bash
desloppify scan --path .
```
*Note for large repositories:* Use `desloppify scan --skip-slow` if initial mechanical passes stall on heavy duplication clusters.

### Step 3: Inspect Parser & Tool Warnings
If the output contains `Coverage reduced (eslint_warning)` or parser errors:
- Resolve the underlying toolchain misconfiguration first (e.g., missing parser plugin in `.eslintrc.js`).
- Rerun `desloppify scan` until mechanical detectors run cleanly.

### Step 4: Baseline Triage Assessment
Check the resulting scorecard:
```bash
desloppify status
```
- **If Subjective Dimensions are 0% (unassessed)**:
  Route immediately to **`desloppify-review`** (`/desloppify-review`) to assess the 75% subjective pool.
- **If Subjective Dimensions are already assessed**:
  Route to **`desloppify-plan`** (`/desloppify-plan`) to shape the triage queue, or jump straight to **`desloppify-next`** (`/desloppify-next`) to begin fixing issues.

### Step 5: Embed Scorecard Badge (Optional)
Check if `scorecard.png` was generated. Offer to embed the status badge in the repository `README.md`:
```markdown
<img src="scorecard.png" width="100%" alt="Desloppify Codebase Health Scorecard">
```
