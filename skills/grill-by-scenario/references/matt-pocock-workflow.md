# Working with Matt Pocock's workflow

Read this when the user wants to combine `grill-by-scenario` with Matt Pocock's skills. Use the skills actually available in the session. The scenario discussion remains usable when none of them are installed.

## Enter or return to a discussion

The upstream `grill-me` entry calls `grilling`; `grill-with-docs` calls `grilling` and `domain-modeling`. Installing this skill leaves those entry points unchanged. Use an explicit request for `grill-by-scenario` to select this discussion method.

When starting a discussion, use the scenario process in `SKILL.md`. When entering from an ongoing grilling session, retain its scope, settled decisions, and unresolved dependencies. Focus on the selected uncertainty and reuse views the user has already supplied.

During that segment, the scenario process controls the exchange: explain the situation, give the human an opportunity to express a view, compare proposals using the same scenarios, and apply the emerging rule to a fresh variation. Pause the upstream requirement to attach a recommendation to every question for this segment. The outer workflow can continue tracking the other decisions without asking them all in the same round.

When the selected topic is settled or explicitly deferred, return its outcome and dependency effects to the surrounding discussion. Reopen a settled question only when new evidence or a changed dependency gives a reason.

## Use domain modeling when requested

Respect the project's existing terminology and explain it within the current scenario. Treat a proposed new term or changed meaning as a proposal until the human has had a chance to shape it.

When maintaining project documents is already in scope and `domain-modeling` is available, use it to record agreed meanings and qualifying decisions in the project's configured documents. Distinguish current behavior from a chosen future behavior, assumptions, and unresolved questions. Let the project's conventions determine document names and locations.

If that skill is unavailable, continue the discussion and summarize the concepts that may need recording. No installation or document creation is required to finish the scenario discussion.

## Continue into specifications or implementation

Matt's `to-spec` synthesizes the current conversation; `to-tickets` accepts a plan, spec, or conversation. Preserve the agreed behavior, scope, scenario outcomes, important trade-offs, and unresolved items so the next step has the context it needs. Keep the conversation available across the handoff, or provide that account when changing sessions.

Before a requested downstream step, distinguish questions deferred outside its scope from questions that still block it. Resolve blocking gaps or agree a narrower scope before treating the work as ready. Confirmation of one decision does not establish readiness for an entire feature.

Use downstream skills only within the user's requested workflow and existing authorization. In particular, `to-spec` and `to-tickets` can publish to the configured tracker; they are not implicit consequences of confirming a scenario summary.

## Upstream references

These links describe the upstream behavior inspected on 2026-10-24. Check the installed versions when they differ.

- [grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md)
- [grilling](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md)
- [grill-with-docs](https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md)
- [domain-modeling](https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/SKILL.md)
- [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md)
- [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md)
