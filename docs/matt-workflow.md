# Using grill-by-scenario with Matt Pocock's skills

`grill-by-scenario` works on its own. If you already use [Matt Pocock's skills](https://github.com/mattpocock/skills), you can also use it at the start of his workflow or to clarify a decision during an existing grilling session.

Both approaches aim for shared understanding. This skill adds a specific way to inspect it: compare the human's and agent's proposals using the same scenarios, then have the agent apply the agreed intent to a related case.

## Start with scenarios

Ask your agent:

> Use grill-by-scenario to decide how contact imports should handle invalid rows. Use our existing project terminology and explain it as it comes up. Also use domain-modeling to record the meanings and decisions we agree on in our configured project documents.

The document-maintenance sentence is optional. It authorizes that work for this example; omit it when you only want a discussion. The installed agent reference explains how the two skills share responsibilities.

Once the intended scope is ready, you can continue through Matt's workflow:

```text
grill-by-scenario
    + domain-modeling, if you want project documents maintained
    -> to-spec
    -> to-tickets
    -> implement
```

His [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md) reads the current conversation, and [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md) accepts a plan, spec, or conversation. They do not require the discussion to have been produced by `grilling`. Follow Matt's project setup for the downstream skills, including the issue tracker and document conventions.

Keep the discussion context when moving to the next step. If you change sessions, carry over the agreed behavior, boundaries, scenario outcomes, and unresolved items. A decision about invalid rows may be settled while duplicate handling still blocks the wider import feature. Resolve that blocker or narrow the next step's scope first.

## Clarify one decision during grilling

You can switch methods without restarting the whole plan:

> Use grill-by-scenario for the duplicate-contact decision we are discussing. Keep our previous decisions and the rest of the plan. Work through concrete cases with me, then return the result and any remaining questions to the original discussion.

While that topic is being discussed, the scenario process controls the interaction. The outer workflow retains the remaining decisions and their dependencies. This matters because Matt's current `grilling` normally attaches a recommendation to each question, whereas this skill first gives you an opportunity to express your expectation or ask for help.

You can repeat this for other decisions in a large plan. The focus is one coherent uncertainty at a time; the number of scenarios and turns can vary.

## What installation changes

Matt's current [grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md) explicitly calls `grilling`. His [grill-with-docs](https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md) explicitly calls `grilling` and `domain-modeling`.

Installing this skill adds a separate entry. It does not rewrite those commands or change what `ask-matt` recommends. Select `grill-by-scenario` explicitly for either recipe above. The integration instructions travel with the skill in [references/matt-pocock-workflow.md](../skills/grill-by-scenario/references/matt-pocock-workflow.md).

## What confirming a discussion means

The closing summary distinguishes agreed behavior from deferred choices and unknown facts. You can agree on a local decision while leaving other work open.

Saving documents, publishing a spec or tickets, and implementing a change follow the work you have actually requested. Matt's `to-spec` and `to-tickets` can publish to your configured tracker, so choose those steps when you want that work to happen. Existing authorization still applies; the skill should not ask you to approve the same action again.

## Compatibility scope

These recipes are based on upstream source inspected on 2026-10-24. They describe conversation and result handoffs, with no automatic replacement of upstream skills. Matt's skills can change; compare the installed versions with the linked sources when their behavior differs. Installation discovery and simulated discussions do not establish compatibility with every agent, model, or downstream publishing workflow.
