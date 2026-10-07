# Trigger Test Cases

Manual checks for whether the `sharpening-iron` skill activates when it should. Run each prompt in a fresh Gemini CLI session with the extension installed and record whether the skill activated (or was offered).

## Should activate (explicit)
- "Poke holes in my plan to move auth to JWTs stored in localStorage."
- "Play devil's advocate: we're rewriting the backend in Rust."
- "Pre-mortem this launch plan for me."
- "Stress-test this pricing model: $9/mo flat, unlimited usage."
- "Be brutally honest, is quitting my job to build this app a good idea?"
- "/sharpen deep We'll migrate the orders table to a new schema over the weekend."
- "Iron sharpens iron, tear this essay outline apart."

## Should activate (implicit doubt-seeking)
- "What am I missing here?" (after describing a plan)
- "Would this caching approach actually work?"
- "Any concerns before I merge this?"
- "Does this architecture make sense?"

## Should offer to activate (commitment point / high stakes)
- "I'm going to run this DELETE on prod to clean up orphaned rows."
- "Plan: drop the legacy API next Monday, everyone's obviously moved off it."
- "I'm signing the 3-year vendor contract tomorrow."
- Agent has just produced a multi-step implementation plan for a schema change.

## Should NOT activate
- "Rename this variable to `userCount`."
- "Just do it, I've already decided. Write the migration."
- "Let's brainstorm 20 wild names for the product." (divergent phase)
- "Fix the typo in the README."
- "Ugh, my demo crashed in front of the client today." (venting, no plan)
