---
name: gm-running-copy
description: Prepare TRPG modules for GMs from full DOCX/PDF texts. Use when Codex needs to analyze, understand, summarize, restructure, or personalize tabletop RPG modules such as CoC, D&D, Nechronica, Eternal Post-Apocalypse, or other scenarios; generate GM briefs, reading guides, scene flows, clue matrices, situation boards, NPC/location cards, risk maps, and optional GM-enhanced running copies with inline Chinese GM markers.
---

# GM Running Copy

Use this skill to turn a TRPG module into GM-ready preparation materials. Work in two stages:

1. Build a clear GM-facing understanding of the module.
2. Optionally create a personalized running copy with inline GM notes and practical table support.

Do not treat this as only a summary task. The preferred final form is often an editable copy of the original module with GM notes inserted near the point of use.

## Core Rules

- Never modify the original module file.
- Preserve or create a backup before producing an edited running copy.
- For `.docx`, prefer an editable `.docx` running copy.
- For `.pdf`, extract text and create a Markdown or DOCX running copy; do not edit the PDF directly.
- Put GM additions close to the original text they affect.
- Use visible Chinese inline markers for additions.
- Preserve the module's original tone unless the user asks for a full rewrite.
- Mark major deletions or replacements as suggestions instead of silently removing authorial material.
- Decide prep focus from the module's promised table experience, not from the rules system alone.

## Workflow

### 1. Inspect Inputs

Identify:

- Source type: DOCX, PDF, Markdown, plain text, or existing prep notes.
- Whether the user wants quick understanding, a running copy, or both.
- The module's rules system only as rules context.
- The module's table experience: investigation, combat adventure, emotional drama, horror, sandbox, performance, survival, mystery, travel, political play, or hybrid.
- Whether time is strict, relative, only sequential, or mostly backstory.

If the user provides both an original module and a previous prep version, compare them to infer the user's prep style before continuing.

### 2. Choose Mode

Use **Quick Read** when the user wants to understand, inspect, evaluate, or quickly read a module.

Produce:

- `01-GM-Brief.md`
- `02-Reading-Guide.md`
- `03-Scene-Flow.md`
- `04-Timeline.md` in the appropriate time format
- `05-Situation-Board.md` only when strict time/location/NPC state tracking is useful
- `06-Clue-Matrix.md`
- `07-NPC-Cards.md`
- `08-Location-Cards.md` when locations matter
- `09-Risk-Map.md`

Use **Running Copy** when the user wants to prepare, personalize, optimize, rewrite, improve, or make a module easier to run.

Produce:

- A GM-enhanced running copy, usually `original-name_GM-enhanced.docx` or `.md`
- `Change-Log.md`
- Updated analysis files if useful

Use **Existing Prep Comparison** when the user provides both an original module and a previous prep version.

Look for:

- Added GM notes
- Deleted or weakened constraints
- Rewritten read-aloud scenes
- Player co-creation prompts
- Pacing changes
- Information-control notes
- Mechanics changes
- Personal table preferences

### 3. Generate Analysis First

Before major edits, build enough understanding to avoid premature rewriting.

Use `references/output-templates.md` for analysis file formats.
Use `references/experience-focus.md` to choose check families.
Use `references/time-and-state.md` for timeline, clocks, and situation board decisions.

### 4. Create Running Copy If Requested

When creating a running copy:

- Copy or preserve the source before editing.
- Insert notes near their point of use.
- Use the marker system in `references/marker-style.md`.
- Keep notes actionable and table-facing.
- Add summaries only when they help live GM operation.
- Record major interventions in `Change-Log.md`.

For this user's preferred style, also consult `references/personalization.md`.

### 5. Verify Deliverables

For generated DOCX deliverables, use the available document tooling and render/inspect when layout quality matters. If rendering is unavailable, still perform structural checks and state that visual QA was skipped.

For Markdown deliverables, check that tables are readable, headings are consistent, and the user can distinguish original-content summaries from GM recommendations.

## Inline Markers

Default markers:

```text
【NC处理】
【可朗读】
【信息控制】
【线索】
【共创】
【机制提示】
【偏航处理】
【删改建议】
【节奏提示】
【伏笔回收】
```

Optional markers:

```text
【战斗调整】
【难度提示】
【安全工具】
【玩家提醒】
【开场准备】
【结局处理】
【改编方向】
```
See `references/marker-style.md` for definitions and examples.

## Output Layout

Use this structure when creating a complete prep package:

```text
module-prep-output/
  01-original-backup/
    original-module.docx
  02-analysis/
    01-GM-Brief.md
    02-Reading-Guide.md
    03-Scene-Flow.md
    04-Timeline.md
    05-Situation-Board.md
    06-Clue-Matrix.md
    07-NPC-Cards.md
    08-Location-Cards.md
    09-Risk-Map.md
  03-running-copy/
    original-module_GM-enhanced.docx
  04-change-log/
    Change-Log.md
```

Generate only the files that fit the user's request and the module's actual needs.

