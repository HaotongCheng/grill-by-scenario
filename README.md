# grill-by-scenario

An agent skill that aligns a human and a coding agent on a decision by working through concrete scenarios, instead of asking a list of questions in the agent's own vocabulary.

## The problem

Grilling skills such as Matt Pocock's [`grill-me`](https://github.com/mattpocock/skills) are great at the start of a project. The agent walks a design tree and asks one decision at a time, and you answer.

A few weeks in, it stops working. The agent has built up project context and coined its own terms, often on purpose, in a glossary. Its questions now arrive in that vocabulary. You were not in every session, so you can no longer tell what you are being asked to decide, let alone whether the recommended answer is right.

The goal of a grilling session was never to get through the question list. It was to make the agent's model of this part of the project match yours. `grill-by-scenario` is built around that goal.

## How it works

1. **Establish the situation.** The agent looks up the facts itself, then describes the current state and the decision in plain terms. It opens with one small, concrete scenario: who does what, and what happens next. Project terms are explained where they come up.
2. **You go first.** The agent holds back its recommendation until you have said what you would expect. A partial idea, a question or a request for options all count.
3. **Same scenarios, both proposals.** Your proposal and the agent's run through the same scenarios with the same starting facts. Disagreements get located in facts, desired behavior or trade-offs, and either side can change.
4. **Clearest representation.** Short prose, a table, a diagram, an example or counterexample, or an interactive visual, whichever makes the difference visible.
5. **The agent gets tested, not you.** Once a rule emerges, the agent applies it to a related case you have not discussed and predicts the outcome. If you would correct the prediction, you are not aligned yet.

The session closes with the agreed behavior, its boundaries, the scenarios that show it, and anything explicitly deferred. Silence is not agreement.

## How it differs from `grill-me`

| | `grill-me` / `grilling` | `grill-by-scenario` |
|---|---|---|
| Unit of a round | A numbered question | A concrete scenario |
| Recommendation | Given with every question | Held back until you have expressed a view |
| Comparison | One recommended answer per question | Both proposals run through the same scenarios |
| Done when | Every branch of the design tree is visited | The agent correctly predicts an unsettled variation and you confirm the summary |
| Built for | Stress-testing a plan before building | A human who lacks the agent's accumulated context |

Several grilling variants use scenarios as one probing tactic. Here the scenario is the unit of discussion.

## When to use which

- Use `grilling` for a plan with many independent decisions, where you already share the vocabulary.
- Use `grill-by-scenario` when one decision needs real shared understanding, or when the agent's questions have stopped making sense to you.

## Example

> **Agent:** Right now, when a contact import hits a row with no email address, the whole import stops and nothing is saved. That's verified in the code. Here's a hypothetical: someone imports 300 contacts, and 12 rows have no email. They open the import results. What would you expect them to see and be able to do? A partial idea is fine.
>
> **You:** Import the 288 good ones, and show me the 12 bad ones so I can fix them.
>
> **Agent:** So the 288 are saved straight away, and the 12 are listed with the reason. Mine was close, but I'd held all 300 until the 12 were fixed. Same scenario, both ways: with yours, the 288 contacts can get this afternoon's campaign. With mine, nobody gets it until someone fixes 12 rows. One more variation we haven't discussed: a row has an email but no name. By your rule I'd import it and flag it, not reject it. Does that match what you'd expect?

## Install

With the [skills CLI](https://skills.sh):

```bash
npx skills@latest add HaotongCheng/grill-by-scenario
```

Or copy `skills/grill-by-scenario/` into your agent's skills directory, for example `~/.claude/skills/` for Claude Code. `agents/openai.yaml` provides display metadata for Codex.

The skill is model-invoked. Ask for "grill by scenario" or "grill by example", or let the agent pick it up when a design discussion is hard to follow.

## Credits

Inspired by the grilling skills in [mattpocock/skills](https://github.com/mattpocock/skills) (MIT). The skill text here is original.

## License

[MIT](LICENSE)
