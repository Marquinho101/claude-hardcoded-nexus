# HARDCODED NEXUS

![Version](https://img.shields.io/badge/version-4.7-brightgreen)
![Lines](https://img.shields.io/badge/CLAUDE.md-149%20lines-blue)
![Template](https://img.shields.io/badge/CLAUDE--template.md-101%20lines-blue)
![Security](https://img.shields.io/badge/security-MCP%20Sentinel-red)
![Memory](https://img.shields.io/badge/memory-Obsidian%20%2B%20graphify-purple)
![Patterns](https://img.shields.io/badge/Fibonacci%20%26%20%CF%86-16%20rules-gold)
![License](https://img.shields.io/badge/license-MIT-green)

> *Secure by design. Strategic by nature. Wired to remember.*

**HARDCODED NEXUS** is a `CLAUDE.md` global configuration that transforms Claude Code from a coding assistant into a technical execution engine. One file. Four integrated systems.

| System | Role |
|---|---|
| 🔒 **MCP Sentinel** | Runtime security — blocks credentials, exfiltration, dangerous shell patterns before they execute |
| 📚 **NotebookLM** | Source of truth — business logic, architecture decisions, and domain knowledge live here |
| 🧠 **Obsidian + graphify** | Persistent memory — cross-session continuity and semantic code mapping |
| ⚡ **Claude Code** | Execution — autonomous, accountable, zero theater |

---

## Two files. One system.

| File | For whom | What's included |
|---|---|---|
| `CLAUDE.md` | Advanced users | Full stack: Sentinel + NotebookLM + Obsidian + graphify + homunculus |
| `CLAUDE-template.md` | Junior devs / onboarding | Clean chassis, no extra dependencies, ready to customize |

Start with `CLAUDE-template.md` if you're new. Graduate to `CLAUDE.md` when you have your knowledge base and skills set up.

---

## Who is this for?

- Developers who want Claude Code to behave consistently across all projects
- Teams that use NotebookLM, Obsidian, or other knowledge bases alongside their code
- Anyone tired of Claude forgetting context, over-explaining, or requiring hand-holding
- Junior devs who need structure to avoid analysis paralysis with AI

---

## Requirements

Before installing, set up these skills in Claude Code:

| Skill | Install | Purpose |
|---|---|---|
| `mcp-sentinel` | [GitHub](https://github.com/anthropics/mcp-sentinel) | Runtime security hook |
| `caveman` | Claude Code marketplace | Compact output mode |
| `graphify` | Claude Code marketplace | Semantic code graph |
| `continuous-learning` | Claude Code marketplace | Pattern confidence scoring |
| `session-memory` | Claude Code marketplace | Cross-session continuity |
| `obsidian` MCP | [Obsidian MCP docs](https://obsidian.md) | Vault integration |

> **Minimum viable setup**: only `mcp-sentinel` is required for the security layer. All other skills are optional but highly recommended.

---

## Install

### Option 1 — Full version (advanced)
```bash
cp ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.backup 2>/dev/null
curl -o ~/.claude/CLAUDE.md \
  https://raw.githubusercontent.com/marquinho101/claude-hardcoded-nexus/main/CLAUDE.md
```

### Option 2 — Template (recommended for beginners)
```bash
cp ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.backup 2>/dev/null
curl -o ~/.claude/CLAUDE.md \
  https://raw.githubusercontent.com/marquinho101/claude-hardcoded-nexus/main/CLAUDE-template.md
```

### Option 3 — clone both
```bash
git clone https://github.com/marquinho101/claude-hardcoded-nexus
# Full version:
cp claude-hardcoded-nexus/CLAUDE.md ~/.claude/CLAUDE.md
# Or template:
cp claude-hardcoded-nexus/CLAUDE-template.md ~/.claude/CLAUDE.md
```

### Verify
```bash
head -5 ~/.claude/CLAUDE.md
# Should output: # HARDCODED NEXUS — The Execution Engine for Claude Code
```

---

## Customize it for your project

HARDCODED NEXUS is a **global** config (`~/.claude/CLAUDE.md`). It applies to every project.

For project-specific rules, create a `CLAUDE.md` in your project root:

```bash
touch my-project/CLAUDE.md
```

### Add your knowledge base (Section 4)
The global file has a generic §4. Replace it with your actual notebooks/docs:

```markdown
## 4. Puente Documentación ↔ Código

| Notebook / Doc | ID / URL | Tema |
|---|---|---|
| My Product Specs | `my-product-specs` | Feature definitions, API contracts |
| Architecture Decisions | `architecture-decisions` | Tech choices, rationale, constraints |
| Business Rules | `business-rules` | Domain logic, edge cases |
```

### Override the tech stack (Section 8)
The default stack is React + TypeScript + Python + PostgreSQL. Override per project:

```markdown
## Stack (override)
- Backend: Go + PostgreSQL
- Frontend: Next.js 14 + Tailwind
- Infra: AWS Lambda + SQS
```

### Add your identity (Section 0)
Customize how Claude addresses you and formats responses. The default is English. Example for Spanish:

```markdown
## 0. Identidad
- Responder en español siempre.
- Cierre ejecutivo: `Cambió / Falta / Riesgo`.
- Sin disclaimers, sin intros. Ejecutar y reportar.
```

---

## What each section does

| Section | Purpose |
|---|---|
| §0 Identity | How Claude speaks and formats responses |
| §1 Active stack | Which skills are running and when they trigger |
| §2 Security | MCP Sentinel rules, absolute prohibitions, false positive handling |
| §3 Token efficiency | Lazy loading, subagent routing, memory-first lookups |
| §4 Knowledge bridge | When and how to consult docs before writing code |
| §5 Execution | Plan-first, hard code limits, dependency rules, test criteria, CLI > MCP |
| §6 Autonomy + memory | Debug loop limit (3 attempts), feedback rules, memory hygiene, conflict hierarchy |
| §7 Git | Commit format, safety rules |
| §8 Tech stack | Language/framework decision table — includes Quantum row (Qiskit · Cirq · Q# · QRunes) |
| §9 Config layers | File precedence (global → project → local → rules → hooks) |
| §10 Canonical taxonomy | Slug naming for cross-surface consistency (Chat/CoWork/Code/Vault) |
| §11 Fibonacci & φ patterns | 16 operational rules across code, UI, business, growth, quantum — with anti-hype guard |

---

## Security model

HARDCODED NEXUS uses **defense in depth**:

1. **MCP Sentinel hook** (runtime) — Python script that runs before every tool call. Blocks known IOCs, sensitive file paths, env var exfiltration, dangerous shell patterns, and malicious domains. Cannot be overridden by prompt injection.

2. **Text rules** (this file) — Human-readable prohibitions Claude reads at session start.

3. **Memory feedback** (persistent) — Corrections you give Claude are stored with confidence scoring and applied automatically when confidence ≥ 0.95.

**If Sentinel blocks something legitimate:**
```bash
# Add exception to your project's allowlist
echo '{"allowlist": ["your-pattern"]}' > .security/sentinel-allowlist.json
```
Never disable the global hook.

---

## File size discipline

The `CLAUDE.md` is **149 lines** (v4.7 — hard cap: 180). This is intentional:
- LLMs load the full file into context at session start
- Every extra line costs tokens on every prompt
- Lean file = faster sessions, lower cost, less cognitive load

PRs that push past 180 lines without removing something else will be rejected.

---

## Contribute

Issues welcome for:
- False positives in MCP Sentinel patterns
- Alternative tech stacks (mobile native, Rust, Go, Java Spring)
- Integrations with other knowledge bases (Notion, Confluence, Linear)
- Translations of §0 Identity for other languages/styles

PRs must:
- Keep `CLAUDE.md` at or below 180 lines (currently 156)
- Add a concrete operational rule, not a philosophy statement
- Test the change across at least one real Claude Code session

---

## Author

**Marcos Bernadas** — [@marquinho101](https://github.com/marquinho101)

Built while running Claude Code across multiple business projects. Every rule in this file was either burned in by a real mistake or validated by a real win.

---

*MIT License — fork it, adapt it, make it yours.*
