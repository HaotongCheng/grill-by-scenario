# grill-by-scenario

Align with your AI agent through concrete scenarios. Compare your proposal and the agent's using the same cases, then check how the agent applies the agreed intent to a new one.

Use it on its own or as part of [Matt Pocock's workflow](docs/matt-workflow.md). It requires no other skills, issue tracker, or glossary.

## Why scenarios

You and an agent can agree on a phrase while picturing different behavior. "Support partial imports" might mean saving valid rows immediately, or letting someone fix the errors before saving anything. A concrete case makes that difference easier to discuss.

This skill helps you reason about those consequences together. It is useful when you are choosing between approaches, exploring a boundary, or catching up on project context. It also works within a larger plan: discuss one coherent uncertainty at a time and carry the decisions forward.

## Try it

After installing, ask:

> Use grill-by-scenario to help me decide what should happen when a contact import contains invalid rows. Explain the situation first and let me describe what I would expect.

You can also invoke `/grill-by-scenario` in Claude Code or `$grill-by-scenario` in Codex. Automatic selection depends on your agent's support and settings.

You can bring a partial idea, ask for context, or request options. The skill gives you an opportunity to express a view; it does not require you to solve the problem unaided.

## How it works

1. **Establish the situation.** The agent checks available evidence and explains the decision through a concrete case. It separates verified behavior from assumptions and hypothetical examples, explaining project terms where they arise.
2. **Hear your expectations.** You have an opportunity to express a view before the agent recommends an approach. If you already gave your view or asked for advice, the conversation continues from there.
3. **Compare on equal terms.** Your proposal and the agent's run through the same scenarios, starting facts, and comparison criteria. Either proposal can change. If you agree already, the agent checks the shared assumption.
4. **Check the agent's understanding.** The agent applies the emerging rule to a related variation that has not been settled and invites correction.
5. **Close with a usable account.** You confirm the agreed behavior, its boundaries, supporting scenario outcomes, and any unresolved or deferred decisions.

A short explanation may be enough; tables, diagrams, or interactive visuals can help when the available tools support them. The number of scenarios and rounds follows the decision.

See the [illustrative contact-import conversation](examples/contact-import.md) for a complete example, including a remaining blocker. It is a constructed demonstration, not a recorded user session or evidence of measured performance.

## Use it with Matt's workflow

The same core supports three paths:

| Path | How it fits |
| --- | --- |
| Standalone | Discuss a decision and finish with a shared account in the conversation. |
| Start a workflow | Use scenario discussion, optionally maintain domain documents, then continue into `to-spec`, `to-tickets`, and `implement` when the intended scope is ready. |
| Resolve a sticking point | Pause an existing grilling session, work through one uncertainty using scenarios, then return the decision and remaining questions to the original flow. |

Installing this skill does not replace Matt's entry points. The [integration guide](docs/matt-workflow.md) explains how to select the active discussion method, use `domain-modeling` alongside it, and preserve unresolved decisions when handing work onward.

## Relationship to grill-me

Both approaches aim for shared understanding. In Matt's [current `grilling` instructions](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md), the agent works through the available decisions in rounds and supplies a recommendation with each question. This skill changes the interaction:

| Aspect | grill-by-scenario |
| --- | --- |
| Discussion focus | One coherent uncertainty, explored through as many scenarios as useful |
| Recommendations | After you have had an opportunity to express a view, or when you request advice |
| Comparison | Both proposals use the same cases, starting facts, and criteria |
| Alignment check | The agent applies the agreed intent to a related new case; you can correct its interpretation |

Scenario questions and human-first discussion have precedents. This project's contribution is the combination above, particularly the paired comparison and the check on the agent's interpretation. It can complement a broader grilling workflow without restricting use to people who lack technical background.

## Install

With the [skills CLI](https://skills.sh):

```bash
npx skills@latest add HaotongCheng/grill-by-scenario --skill grill-by-scenario
```

This installs for the current project. Add `-g` for a personal installation across projects. Use `-a claude-code` or `-a codex` to select an agent, or choose one when prompted. See the [skills CLI documentation](https://github.com/vercel-labs/skills) for installation options.

For manual installation, copy the entire `skills/grill-by-scenario/` directory, including its supporting files, into `.claude/skills/` for a Claude Code project or `.agents/skills/` for a Codex project. The included `agents/openai.yaml` provides Codex display metadata.

## Credits and license

Created by Eric Cheng, inspired by Matt Pocock's [`grill-me`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md) and [`grilling`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) in [mattpocock/skills](https://github.com/mattpocock/skills).

[MIT License](LICENSE). See [third-party notices](THIRD_PARTY_NOTICES.md) for the upstream attribution and license.
