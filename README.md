# ⚔️ Sharpening Iron: The Constructive Devil's Advocate

> "As iron sharpens iron, so one person sharpens another." (Proverbs 27:17)

**Sharpening Iron** is a Gemini CLI extension that pressure-tests your plans, ideas, and decisions, then works with you to refine them until they are as close to flawless as the stakes justify. It covers software architecture and bug fixes, and also product ideas, business strategy, writing, and personal decisions.

It is a sparring partner, not a naysayer. It understands and steelmans your plan first, grounds every challenge in evidence, ranks issues by severity, pairs every flaw with a fix or a cheap test, and keeps iterating until nothing serious is left open.

## 🌟 Key Features

- **Premise first**: asks whether you are solving the right problem, and whether "do nothing" or a different approach would win.
- **Assumption excavation**: finds the load-bearing assumptions and rates each by confidence and impact.
- **Pre-mortem**: imagines the plan has failed and works back to the plausible causes and early warning signs.
- **Domain lenses**: question banks for software, architecture, migrations, product, business, personal decisions, writing, and operations, plus a bias check on its own critique.
- **Severity-ranked Iron List**: Fatal / Serious / Minor, each with why it matters and how to resolve it.
- **Iterative convergence**: tracks each item as Resolved, Mitigated, Accepted, or Open across rounds, re-attacks your revisions, and ends with a verdict.
- **Calibrated intensity**: `quick`, `standard`, or `deep`. It never manufactures objections, and says so when a plan is sound.

## 🚀 Installation

```bash
gemini extensions install https://github.com/g-programs/sharpening-iron.git
```

## 📋 Usage

### Explicit invocation
```
/sharpen <your plan or idea>
/sharpen deep We're migrating the orders table to a new schema this weekend.
/sharpen quick                  # sharpens the most recent plan in the conversation
```

### Natural-language cues
The skill activates on phrases like *"poke holes in this"*, *"play devil's advocate"*, *"stress-test"*, *"pre-mortem"*, *"red-team"*, *"sanity check"*, *"what am I missing?"*, *"what could go wrong?"*, *"is this a good idea?"*, and *"be brutally honest"*.

### Proactive offers
When a costly or hard-to-reverse plan is about to be committed to (production data changes, migrations, launches, contracts, career moves), or a plan is stated with untested certainty ("obviously", "just", "can't fail"), the agent offers a pressure-test. It also self-checks its own non-trivial plans before presenting them.

It stays quiet for trivial tasks, "just do it" requests, early brainstorming, and venting.

## Example

> **User**: "I'm going to add a Redis cache in front of user profiles. Should be simple."
>
> **Agent (Sharpening Iron)**:
>
> **Understanding:** cache profile reads in Redis to cut DB load and p95 latency. Success means lower p95 with no stale-profile complaints.
> **Strongest case for it:** profile reads dominate traffic and rarely change, which is the ideal cache shape.
>
> | # | Severity | Challenge | Resolve it by |
> |---|---|---|---|
> | 1 | Serious | Invalidation runs after the DB write. A crash in between serves stale profiles until the TTL expires. | Delete on write inside the same unit of work, plus a short TTL as a backstop. |
> | 2 | Serious | No evidence that the DB is the bottleneck. Latency may come from the N+1 in `ProfileSerializer`. | Profile one request first (30 min) before building anything. |
> | 3 | Minor | Cold-start stampede after a deploy. | Request coalescing, or jittered TTLs. |
>
> **Verdict:** Not ready. Verify #2 first, because it may remove the need for a cache entirely.

## Repository layout

```
GEMINI.md                                 # always-loaded activation cues
commands/sharpen.toml                     # /sharpen command
skills/sharpening-iron/SKILL.md           # the full method
skills/sharpening-iron/references/lenses.md   # domain question banks
tests/trigger-cases.md                    # prompts for checking activation
```

## 📝 License

MIT. See [LICENSE](LICENSE).

---
*Developed by the Focus Fire Team*
