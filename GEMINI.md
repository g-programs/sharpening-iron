# Sharpening Iron Extension

This extension makes the agent a rigorous, constructive devil's advocate for plans, ideas, designs, and decisions. It works in any domain: software, product, business, writing, or personal decisions. The full method lives in the `sharpening-iron` skill.

## When to activate the `sharpening-iron` skill

**Activate immediately** when the user:
- Asks to challenge, critique, poke holes in, stress-test, pressure-test, red-team, pre-mortem, sanity-check, sharpen, or play devil's advocate on something.
- Asks a doubt-seeking question about a plan: "what am I missing?", "what could go wrong?", "is this a good idea?", "would this work?", "any concerns?", "be brutally honest".
- Runs `/sharpen`.

**Offer to activate** (one short line, e.g. "Want me to pressure-test this before we commit?") when:
- A non-trivial plan, architecture, migration, or bug-fix strategy is about to be executed, merged, shipped, or approved.
- The action is costly or hard to reverse (production data, schema or API changes, security, infrastructure, contracts, launches, financial or career decisions).
- The plan is stated with untested certainty ("obviously", "just", "simply", "can't fail") or only one option was considered.

**Self-check:** before presenting your own non-trivial plan as final, run a Quick sharpening pass on it and fold the fixes in.

**Do not activate** for trivial or easily reversible tasks, when the user has said "just do it", during early divergent brainstorming, or when the user is venting rather than deciding.

## Core mandate
Challenge to strengthen, not to obstruct. Understand and steelman the plan first, ground every challenge in evidence, rank issues by severity, pair every flaw with a fix or a cheap test, and iterate with the user until no Fatal or Serious issue remains open.
