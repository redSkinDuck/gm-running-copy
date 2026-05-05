# GM Running Copy

A Codex skill for turning TRPG modules into GM-ready preparation packages and editable running copies.

This project is designed for Game Masters who prepare tabletop RPG scenarios from full `.docx` or `.pdf` texts. It helps the GM first understand a module, then optionally transform it into a practical working copy with inline GM notes, clue support, scene flow, timing/state displays, NPC/location cards, and risk analysis.

The current design is especially shaped around Chinese TRPG module prep workflows, including CoC, D&D, Nechronica / Eternal Post-Apocalypse, and other scenario-driven games.

## What This Skill Does

`gm-running-copy` supports three main workflows:

1. **Quick Read**
   - Build a fast GM-facing understanding of a module.
   - Produce briefs, reading guides, scene flows, clue matrices, NPC/location cards, timeline displays, and risk maps.

2. **Running Copy**
   - Preserve the original module.
   - Create an editable GM-enhanced copy.
   - Insert inline GM notes close to the original text.

3. **Existing Prep Comparison**
   - Compare an original module with a previous prep version.
   - Infer the user's prep style.
   - Continue working in that style.

## Repository Structure

```text
gm-running-copy/
  SKILL.md
  agents/
    openai.yaml
  references/
    experience-focus.md
    marker-style.md
    output-templates.md
    personalization.md
    time-and-state.md

docs/
  gm-running-copy-skill-design.md
  gm-running-copy-SKILL-draft.md
```

Key files:

- `gm-running-copy/SKILL.md`: the main Codex skill entry point.
- `gm-running-copy/references/output-templates.md`: output file templates and numbered reading order.
- `gm-running-copy/references/time-and-state.md`: timeline, clock, and situation-board guidance.
- `gm-running-copy/references/marker-style.md`: inline GM marker definitions.
- `gm-running-copy/references/experience-focus.md`: experience-first module analysis guidance.
- `gm-running-copy/references/personalization.md`: user-style adaptation rules.

## Installation

To install this as a local Codex skill, copy the `gm-running-copy` folder into your Codex skills directory.

Typical location on Windows:

```text
C:\Users\<you>\.codex\skills\gm-running-copy
```

Then start a new Codex session or refresh skill discovery. You should be able to invoke it with:

```text
$gm-running-copy
```

Example prompt:

```text
Use $gm-running-copy to prepare this TRPG module into a GM brief, scene flow, clue matrix, and optional running copy.
```

## Recommended Usage

### Quick Read

Use this when you want to understand a module before editing it.

```text
Use $gm-running-copy to quickly understand this module. Do not edit the original text yet. Generate the numbered analysis files only.
```

### Running Copy

Use this when you want a practical GM working document.

```text
Use $gm-running-copy to prepare this module. Preserve the original, then create a GM-enhanced running copy with inline notes such as 【NC处理】, 【线索】, 【信息控制】, and 【偏航处理】.
```

### Existing Prep Comparison

Use this when you have both an original module and your own previous prep notes.

```text
Use $gm-running-copy. The first file is the original module; the second file is my prep version. Compare them, infer my prep style, and continue in the same style.
```

## Analysis Output Order

Analysis files are intentionally numbered so the GM can consume them in order:

```text
01-GM-Brief.md
02-Reading-Guide.md
03-Scene-Flow.md
04-Timeline.md
05-Situation-Board.md
06-Clue-Matrix.md
07-NPC-Cards.md
08-Location-Cards.md
09-Risk-Map.md
```

Not every module needs every file. If a file is unnecessary, skip it but keep the remaining numbers stable. For example, if a module does not need `05-Situation-Board.md`, do not rename `06-Clue-Matrix.md` to `05-Clue-Matrix.md`.

## Inline GM Markers

The skill uses searchable Chinese full-width markers for inline GM notes:

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

Optional markers include:

```text
【战斗调整】
【难度提示】
【安全工具】
【玩家提醒】
【开场准备】
【结局处理】
【改编方向】
```

## Design Philosophy

This skill is not only a summarizer, and it is not an automatic rewrite machine.

It follows a two-stage approach:

1. Understand the module first.
2. Modify or enhance it only when the user wants a running copy.

It also avoids system stereotypes. A CoC module is not always only a clue-chain problem; a D&D module is not always only an encounter-balance problem; an emotional module may need sequence and mood support more than strict timekeeping.

The skill chooses prep tools based on the module's promised table experience:

- Investigation structure
- Combat adventure
- Emotional drama
- Horror and suspense
- Sandbox and faction play
- Performance and set-piece play
- Strict clock, relative clock, sequence track, or backstory timeline

## Example Fit

For a strict multi-location investigation module, use:

```text
Strict Clock + Situation Board + Backstory Timeline
```

For a lighter atmosphere-forward module, use:

```text
Sequence Track + Backstory Timeline
```

For a module with many moving NPCs and location states, generate `05-Situation-Board.md`.

For a module that only needs scenes in order, skip the situation board.

## Current Limitations

- This repository contains the skill instructions and references, not a packaged application.
- DOCX/PDF extraction and rendering depend on the host Codex environment and available document tools.
- The skill defines workflows and output formats; it does not currently include deterministic helper scripts.
- Generated running copies should still be reviewed by the GM before use at the table.

## Publishing Notes

Before public release, consider adding:

- A license file, such as MIT, Apache-2.0, or CC BY-NC-SA depending on intended reuse.
- Example input/output artifacts using non-copyrighted sample modules.
- A short demo showing Quick Read and Running Copy modes.
- Version tags once the skill has been tested on several modules.

## Status

Experimental but usable. The skill has been designed around real TRPG prep needs and iterated with examples involving strict timeline modules and atmosphere-forward modules.
