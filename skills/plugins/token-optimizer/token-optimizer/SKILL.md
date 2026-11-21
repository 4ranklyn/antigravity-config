---
name: token-optimizer
description: Audits Antigravity sessions for token usage, context waste, and context limits. Use when the user asks to check token consumption, audit context window, or optimize session tokens.
---

# Token Optimizer for Antigravity

Inspects Antigravity conversation stores, decodes `gen_metadata`, and reports token usage across inputs, outputs, cache reads, and context fill.

## Quick Reports

Run from PowerShell or terminal:

```powershell
$env:TOKEN_OPTIMIZER_RUNTIME="antigravity"
python C:/Users/jasso/.gemini/antigravity/scratch/token-optimizer/skills/token-optimizer/scripts/measure.py antigravity-summary
```

## Readiness Doctor

```powershell
$env:TOKEN_OPTIMIZER_RUNTIME="antigravity"
python C:/Users/jasso/.gemini/antigravity/scratch/token-optimizer/skills/token-optimizer/scripts/measure.py antigravity-doctor
```

## Web Dashboard

To run the local browser dashboard on port 24847:

```powershell
$env:TOKEN_OPTIMIZER_RUNTIME="antigravity"
python C:/Users/jasso/.gemini/antigravity/scratch/token-optimizer/skills/token-optimizer/scripts/measure.py dashboard --port 24847
```
Then open http://localhost:24847.
