# Agent Memory: sharpening-iron

Gemini CLI extension that provides a constructive devil's-advocate skill ("Sharpening Iron") for stress-testing plans, ideas and decisions in any domain.

## Layout
- `GEMINI.md`: always-loaded extension context. Holds the activation cues (when to activate, when to offer, when not to). Ships to end users, so keep developer notes out of it.
- `skills/sharpening-iron/SKILL.md`: the full method. Its `description` front matter drives automatic activation, so keep trigger phrases in it.
- `skills/sharpening-iron/references/lenses.md`: domain question banks, loaded on demand.
- `commands/sharpen.toml`: the `/sharpen [quick|standard|deep] <plan>` command.
- `tests/trigger-cases.md`: manual prompts for checking activation (should, should offer, should not).
- `gemini-extension.json` and `package.json`: keep their versions in sync.

## Conventions
- When you change activation cues, update `SKILL.md` (description), `GEMINI.md`, `README.md` and `tests/trigger-cases.md` together.
- Keep `SKILL.md` lean. Put long question lists in `references/`.
- The skill must never manufacture objections. Every challenge needs a concrete consequence and a fix or a cheap test.

## Change log
- **v1.1.0 (PR #1, merged 2026-10-17):** broadened the skill from software-only to any plan or idea. Added a step-by-step method (restate, steelman, premise check, assumptions, pre-mortem, lenses, Fatal/Serious/Minor ranking, fix per flaw, repeated rounds ending in a verdict) and `quick`/`standard`/`deep` intensity. Also added the lens question banks, the `/sharpen` command, activation cues in `GEMINI.md`, and the trigger test cases. Removed `main` from `package.json` because it pointed to a file that doesn't exist.

## Open items
- `gemini-extension.json` has `"mcpServers": []`. Gemini CLI may expect `{}` or no field at all. Verify this against the Gemini CLI docs.
- The skill hasn't been run in the Gemini CLI yet. Run `tests/trigger-cases.md` after installing.

## Gotchas
- Pushes from Claude cloud sessions failed with a 403 ("Resource not accessible by integration") until the owner reconnected GitHub at https://claude.ai/connect-github.
