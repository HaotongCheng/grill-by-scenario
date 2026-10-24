---
name: grill-by-scenario
description: Align human and agent expectations about a project decision through concrete scenarios. Use for scenario-based or example-based grilling, including requests called grill-by-example, or when missing background and project jargon make a design discussion hard to follow.
---

# Grill by Scenario

Build a shared model of how the relevant part of a project should behave. Make the consequences understandable enough for the human to shape the decision and for the agent to apply that intent to a related situation.

Keep the session focused on the decision at hand. Track dependencies yourself and discuss one coherent uncertainty at a time; the human does not need to reconstruct the whole project or answer an entire decision tree.

## Establish the situation

Look up relevant facts in available code, documents, and tools yourself. Distinguish verified current behavior, assumptions, unknowns, and hypothetical examples. Explain the current situation, the problem that needs a decision, and who or what the decision affects.

Introduce a small, concrete scenario with enough context to reason about its outcome. Use familiar descriptions of actors, events, and observable behavior. Explain essential project terms where they arise; connect them to the scenario instead of requiring the human to learn a glossary first.

The opening helps the human understand and invites their expectations. Withhold your recommendation until they have had an opportunity to express a view or explicitly ask for suggestions. Present hypothetical facts and consequences neutrally; do not hide a preferred solution in the scenario or a preselected answer.

For example, if this is hypothetical, say so: "Someone imports a spreadsheet of three hundred contacts, and twelve rows have no email address. They open the import results. What would you expect them to see and be able to do? A partial idea is enough, and I can offer options if that helps."

Then wait for their response. If they already supplied a view or requested recommendations, use that contribution and continue without making them repeat it.

## Let the human express a view

Human-first is an opportunity to participate, not an obligation to solve the problem unaided. Welcome partial suggestions, questions, uncertainty, and requests for examples or options. Answer requests for missing context before pressing for a decision. When they ask for help choosing, offer options and consequences, and a recommendation when useful.

Reflect their proposal as observable behavior, and clarify ambiguities that would materially change the outcome. Acknowledge corrections and carry forward established understanding without requiring a separate sign-off on every paraphrase.

## Compare through the same scenarios

After understanding the human's view, give your own assessment and recommendation, with the constraints or evidence behind it. Explain meaningful differences honestly. Revise your view when the human supplies better context; explain overlooked consequences when their proposal needs revision. If the proposals already agree, check the shared assumption instead of inventing an opposing position.

Run the human's proposal and your proposal through the **same scenarios**, using the same starting facts and comparison criteria. Describe what each would cause people or systems to observe or do. Choose ordinary cases and relevant variations that expose a material difference; keep hypothetical variations clearly labeled.

Locate disagreements in facts, desired behavior, or trade-offs. Investigate factual uncertainty when possible. Let the human shape goals and priorities with the consequences in view. Either proposal can change, and a third proposal may combine what the discussion reveals. Explain what changed your recommendation when it changes.

## Choose the clearest representation

Use short prose for a simple case, a diagram for sequence or relationships, a table for contrasting consequences, and an example or counterexample for a rule's boundary. Use an interactive visual when exploring variations would help and suitable tools are available. Text is a sufficient fallback.

Match the human's language and level of context. Keep visuals focused on the current uncertainty, and expose implementation details only when they affect the decision. Adapt the format and number of rounds to the discussion.

## Check alignment and close

Once a rule or expectation emerges, apply it yourself to a meaningful related variation that has not yet been directly settled. Explain the predicted behavior and invite correction. This checks whether you can use the human's intent; it is not a quiz for the human.

Close with a concise account of the agreed behavior, its boundaries, the scenario outcomes that demonstrate it, and any explicitly deferred decisions or unresolved facts. Treat the session as aligned when the human confirms that account, including any stated uncertainty, and no material contradiction remains within the agreed scope. A deferred choice stays deferred; silence is not agreement. If the human wants to stop earlier, summarize what is settled and what remains open.

Keep implementation and saving decisions within the user's existing authorization. Agreement on the model alone does not authorize editing project files, posting decisions, or implementing the result; when those actions are already authorized, continue without asking again.
