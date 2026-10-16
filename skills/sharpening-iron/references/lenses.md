# Sharpening Iron: Lens Question Banks

Pick the bank that matches the domain. These are prompts for your own thinking, not a checklist to paste at the user. Surface only questions that reveal a concrete, plausible risk for *this* plan.

## Universal (any plan or idea)
- What problem does this solve, for whom, and how do we know it is real?
- What is the user's *actual* goal, and is this the shortest path to it?
- What would have to be true for this to succeed? Which of those things is least certain?
- What is the cheapest experiment that would prove or kill the riskiest assumption?
- What does "done" look like, and what is the kill criterion?
- What is the worst realistic outcome, and can we survive it?
- How reversible is this, and what is the rollback or exit plan?
- What is being given up (time, money, focus, goodwill) to do this?
- Who else is affected, and have they been consulted?
- What would a smart critic, competitor, or regulator say about this?
- If we were starting from scratch, would we still choose this approach?

## Software: implementation and bug fixes
- **Root cause**: does the fix address the cause or mask a symptom? Can we reproduce the bug *before* fixing it, and write a test that fails first?
- **Happy-path bias**: network/IO failures, timeouts, locked or unavailable resources, read-only filesystems, partial writes, retries that aren't idempotent.
- **State**: what happens if the process dies mid-operation? Are writes atomic and transactional? Can a crash leave orphaned or inconsistent data?
- **Input**: null, empty, huge, malformed, unicode, negative, duplicate, out-of-order, or schema-drifted data.
- **Concurrency**: race conditions, deadlocks, double submission, stale reads, lost updates, cache coherence.
- **Scale**: 100x input, N+1 queries, unbounded memory or loops, hot keys, pagination, rate limits.
- **Security**: injection, authz gaps (who can call this?), secrets in logs or errors, SSRF, path traversal, unsafe deserialization, supply chain.
- **Where else?**: are there other call sites with the same bug pattern? Other consumers of a changed interface?
- **Tests**: do tests cover the failure modes, or only the happy path? Would the tests have caught the original bug?
- **Observability**: if this fails in production, how will we know, and how fast?

## Software: architecture and design
- What are the expected load, latency, and consistency requirements? Are they written down?
- Is this solving today's problem or an imagined future one? (YAGNI vs. painting into a corner.)
- Which components are single points of failure? What happens when each dependency is down?
- What is the data model's migration story? Backward and forward compatibility? Zero-downtime deploys?
- How does this get tested, deployed, monitored, and debugged at 3 a.m.?
- What is the operational and cognitive cost for the team? Who owns it long-term?
- Is there an existing, boring, proven solution (library, managed service, standard pattern)?
- What lock-in (vendor, framework, data format) does this create, and what does it cost to leave?

## Data migrations and irreversible operations
- Is there a verified backup, and has a restore actually been tested?
- Can it run as a dry run? Can it run incrementally or on a sample first?
- What is the rollback plan once new writes have happened?
- How is correctness verified afterwards (row counts, checksums, invariants)?
- What is the downtime or lock impact on live traffic?

## Product and features
- Who specifically has this problem, how often, and how painful is it? What do they do today?
- What evidence exists beyond "I would use it" (behavior, payments, waitlists, support tickets)?
- How will users discover, understand, and adopt it? What is the activation moment?
- What metric moves if this works, by how much, and by when?
- What does it cost to maintain, support, and explain, forever?
- What existing behavior or user does this break or annoy?

## Business and strategy
- Why will customers pay, and why *you* rather than alternatives (including doing nothing)?
- Unit economics: CAC, margin, payback period. Which number is the guess?
- Why now? What changed that makes this possible or necessary?
- How will competitors respond? What is defensible after they copy it?
- Distribution: how do you reach the first 100 customers, concretely?
- Regulatory, legal, or reputational exposure?
- What is the runway impact if it takes twice as long and earns half as much?

## Personal and career decisions
- What is the decision *really* optimizing for: money, growth, freedom, security, relationships, meaning? Are those weighted honestly?
- What is the realistic downside, and is it survivable financially and emotionally?
- Is this reversible? Can it be trialed first (a contract role, sabbatical, side project, visit)?
- Whose input matters, and have they been asked?
- Is the decision driven by escaping something or moving toward something?
- In 5 years, which choice is more likely to be regretted?
- What information would change your mind, and can you get it before deciding?

## Writing, arguments, and research
- What is the single core claim? Can it be stated in one sentence?
- What is the strongest counterargument, and is it addressed fairly?
- Which claims rest on evidence and which rest on assertion? Are sources primary and current?
- Is causation being inferred from correlation? Is there selection or survivorship bias?
- Would the conclusion survive a different (reasonable) dataset, sample, or framing?
- Who is the audience, and what do they need to believe or do afterwards?

## Process, operations, and teams
- Who owns each step? What happens when that person is out?
- Where are the handoffs, and what gets lost at each one?
- How does the process fail under pressure (deadlines, incidents, turnover)?
- What incentives does this create, and how could it be gamed?
- What is the cost of compliance vs. the cost of the problem it prevents?

## Cognitive bias checks (apply to your own critique too)
- **Confirmation bias**: is evidence only being gathered for the preferred option?
- **Sunk cost**: is past investment driving the decision?
- **Planning fallacy**: compare estimates to a reference class of similar past projects.
- **Optimism and overconfidence**: what is the base rate of success for things like this?
- **Anchoring**: is the first idea being refined instead of alternatives being compared?
- **Availability**: is a recent vivid event distorting risk perception?
- **Contrarian bias (yours)**: are you objecting because the plan is flawed, or because your role is to object?
