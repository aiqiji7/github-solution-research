# PRD: Replace "Codex" with "coding agent" for platform-agnostic skill

## Goal

Replace all product-specific references to "Codex" with the platform-agnostic term "coding agent" in the skill's own documentation files. Remove Codex-specific installation paths in favor of generic guidance.

## Scope

### Files to change

| File | Change |
|---|---|
| `README.md` | "Codex" → "coding agent" (concept refs); delete Codex-specific install paths |
| `AGENTS.md` | "Codex" → "coding agent" (Trellis-managed block, 2 occurrences) |

### Files NOT to change

| File | Reason |
|---|---|
| `SKILL.md` (root) | No "Codex" references |
| `agents/openai.yaml` | No "Codex" references |
| `.trellis/**` | Trellis infrastructure, uses "Codex" as literal platform identifier |
| `.opencode/**` | Trellis infrastructure, platform detection code |

## Detailed changes

### README.md

**Concept references** — Replace "Codex" with "coding agent":
- "A Codex skill" → "A coding agent skill"
- "Codex skill" → "coding agent skill" (all occurrences in EN + ZH)
- "Codex 集成" → "coding agent 集成"
- "在 Codex 中调用 skill" → "在 coding agent 中调用 skill"
- "Codex integration" → "coding agent integration"
- "Invoke the skill in Codex" → "Invoke the skill in your coding agent"
- "Codex skill entrypoint/主入口" → "coding agent skill entrypoint/主入口"

**Badge** — Update alt text and badge URL label from "Codex-skill" to a generic label.

**Installation paths** — Remove Codex-specific paths (`~/.codex/skills`), replace with generic guidance:
- ZH: "clone 到你的 coding agent 的 skills 目录"
- EN: "clone into your coding agent's skills directory"
- Remove `gh auth status` block (not installation-related)

### AGENTS.md

Two occurrences in Trellis-managed block:
- "If you're using Codex or another agent-capable tool" → "If you're using a coding agent"
- "`.codex/agents/` — optional custom subagents" → "`.codex/agents/` — optional custom subagents" (keep literal path)

## Verification

- [ ] `README.md` contains zero "Codex" references
- [ ] `README.md` contains no Codex-specific install paths
- [ ] `AGENTS.md` contains zero "Codex" references
- [ ] `SKILL.md` frontmatter unchanged
- [ ] `.trellis/` and `.opencode/` files untouched
