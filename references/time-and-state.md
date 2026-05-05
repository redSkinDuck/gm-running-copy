# Time and State Displays

Do not force every module into a strict clock. Choose the time format based on how time actually functions in the module.

## Timeline Formats

### Sequence Track

Use when events only need to happen in order.

Best for:

- Linear modules
- Emotional or relationship-forward modules
- Performance or stage-like modules
- Dreamlike modules
- Atmosphere-forward modules

Track:

- Scene order
- Required reveals
- Emotional beats
- Optional detours
- Return points
- What must happen before the climax

### Strict Clock

Use when exact dates, hours, deadlines, travel time, timed clue differences, or offscreen NPC actions matter.

Best for:

- Pursuit
- Investigation with timed clues
- Faction action
- Disaster countdown
- Ritual deadline
- Sandbox modules
- Modules where locations change by time of day

Track:

- Exact date and time
- Event
- Location
- Actor
- Clue changes
- Consequences of delay
- Next fixed time point

### Relative Clock

Use when time matters, but only relative to PC actions.

Best for:

- Dungeons
- Heists
- Chases
- Escalating horror
- Alarm or suspicion systems
- "After X scenes/rooms/failures" structures

Track:

- Trigger
- Elapsed segment
- Escalation
- NPC response
- Next pressure point

### Backstory Timeline

Use for historical truth, secret causes, NPC past actions, and mystery reconstruction. This is often paired with one of the above session-facing formats.

Track:

- What really happened
- Who caused it
- What evidence remains
- What lies or misunderstandings exist
- Which present-day clues reveal each past event

## 04-Timeline.md

Use this filename for the chosen timeline format: sequence track, strict clock, relative clock, backstory timeline, or a combined timeline where needed.

## 05-Situation-Board.md

Purpose: show the GM, at a glance, what each important character, faction, and location is doing at the current time.

Use when the GM would otherwise need to mentally cross-reference multiple clocks, locations, and NPC actions.

Do not generate a full situation board for every module. If a module only needs ordered scenes, mention that the board is unnecessary and use a sequence track instead.

## Situation Board Formats

Time-slice table:

```text
| Time | Major NPC 1 | Major NPC 2 | Faction | Location A | Location B | Location C | GM Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
```

Location state table:

```text
| Location | Before PCs arrive | If PCs arrive early | If PCs arrive late | Clues available | Active NPCs | Danger | Next change |
| --- | --- | --- | --- | --- | --- | --- | --- |
```

Active NPC tracker:

```text
| NPC/Faction | Goal | Current location | Current state | Knows | Next action | Trigger to update |
| --- | --- | --- | --- | --- | --- | --- |
```

## Include

- Current date and time blocks
- Important NPC and faction locations
- Location states and clue availability
- Events that happen without PC intervention
- What changes if PCs arrive early, on time, or late
- Which entries are fixed and which are adjustable by GM judgment
- Immediate next update trigger

## Examples of Fit

- Strict, multi-location pursuit module: use `Strict Clock + Situation-Board + Backstory Timeline`.
- Light atmosphere-forward module: use `Sequence Track + Backstory Timeline`, usually no situation board.
- Dungeon with escalating alarm: use `Relative Clock`, optionally a small faction/NPC tracker.
