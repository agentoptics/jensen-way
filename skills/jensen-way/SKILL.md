---
name: jensen-way
description: Physics-of-reality decision framework. Tests whether a product, feature, or spec obeys the laws of friction, inertia, cause-and-effect, and hard constraints — producing a defensible build/pivot/kill verdict backed by evidence. Use when evaluating product ideas, feature specs, or build-vs-buy decisions.
license: MIT
---

# Jensen Way

A decision framework derived from Jensen Huang's framing of Physical AI — extended to product and engineering decisions.

> "The next wave requires us to understand things like the laws of physics — friction, inertia, cause and effect. The fact that I tip that thing over, it's going to fall. When I set the bottle down, it's not going to go through the table. All of these common sense physical reasoning abilities that children have, that our pets have — most AIs don't have."
>
> — Jensen Huang, [Hill & Valley Forum 2025](https://www.youtube.com/watch?v=nkhrEnuZi20&t=485s), interviewed by Jacob Helberg, May 3, 2025

Jensen was describing Physical AI. The same observation applies to most product plans: they operate in a frictionless vacuum — a fantasy where users adopt because you ship, teams align because you scheduled a meeting, and systems scale because the diagram says so.

**The core test:** if you need 10 pages to convince someone this will work, the physics are probably against you. A child should be able to follow the causal chain.

## When to activate

- Evaluating whether to build a product or feature
- Build-vs-buy decisions
- "Should we do X?" or "Is X worth building?"
- Feature spec validation before committing engineering time
- User says "jensen", "evaluate this", "should we build", "is this feasible"

## Workflow

### Phase 1 — Frame and trace the causal chain

State what's being evaluated:

```
EVALUATING: [product/feature/spec]
DECISION TYPE: [build / continue / choose A vs B]
TIME HORIZON: [weeks / months / quarters]
```

Then write the full chain from "we start building" to "this matters":

```
1. We build [X]       → because [reason]
2. Which causes [Y]   → because [mechanism]
3. Which leads to [Z] → because [mechanism]
...
N. Which results in [outcome that matters]
```

**The toddler test:** read each `→ because`. Would a child accept that explanation? If you need jargon or "if everything goes right" qualifiers, mark it as a weak link. Every weak link is where the plan assumes a frictionless vacuum — these become the focus of research.

### Phase 2 — Research (evidence, not gut feel)

Gather evidence for the weak links. Use available web search tools.

- Prefer: official docs, benchmarks, case studies, post-mortems > blog posts > opinions
- For market questions: search volume, waitlists, competitor traction, pricing, reviews
- **Search for failure.** "Why X failed" and "problems with X" reveal more than success stories.

For broad evaluations, launch 3 research subagents in parallel:
1. Market + user reality (demand, competitor traction, user pain)
2. Technical reality (scaling limits, dependency risks, hard constraints)
3. Org + economic + temporal reality (team capacity, costs, entropy)

### Phase 3 — Evaluate against the 6 laws

#### 1. Gravity of demand
Gravity only pulls things with mass. Is there measurable evidence people want this?

- Demand signal: search volume, waitlists, competitor traction, people paying for bad alternatives
- TAM: not "if everyone in the world...", the number actively in pain today
- Timing force: what changed *recently* that makes this possible now? If nothing — why hasn't it been built?

*Evidence required: ≥2 sources on demand. "I think people want this" is not a force.*

#### 2. Friction of adoption
Users are heavy objects at rest. Moving them requires force greater than friction.

- Current inertia: how are users solving this today? Even a bad solution has workflow + data + mental-model mass
- Switching friction: signup, learning curve, migration, behavior change, team buy-in, procurement
- Hair-on-fire test: painkillers sell themselves; vitamins need marketing budgets
- Time to value: every minute between "start" and "value" dissipates force

#### 3. Competitive gravity
If this works, large bodies nearby will be pulled toward it.

- Existing mass: who already does this? Funding, users, revenue, data, distribution. Name them.
- Defensive gravity: what creates a gravity well? Data effects, integration depth, switching costs, regulatory capture. "We'll execute better" is velocity, not gravity — velocity fades.
- Incumbent threat: if a big player copies in 6 months, what can't they replicate?

*Evidence required: name specific competitors. Search three ways before concluding "no one does this."*

#### 4. Hard constraints (the table test)
The bottle doesn't go through the table. What are the immovable constraints?

- Physics floors: speed of light, human attention, regulatory, mathematical limits
- Dependency gravity: list every critical 3rd-party. What if it disappears, reprices, throttles?
- Scaling cliff: at what scale does the current approach hit a wall? What changes there?
- Rug-pull risk: find precedents of the platform changing terms, pricing, APIs

#### 5. Organizational inertia
The software mirrors the actual communication structure, not the org chart.

- Structural alignment: if the spec requires teams A and B to integrate perfectly, do they talk today?
- Team mass: a project with N people has N(N-1)/2 communication channels. Scope down before staffing up.
- Skill gravity: acquiring new skills has months of friction. "We'll learn it" is not a free resource.
- Decision friction: how many approvals sit between "code complete" and "shipped"?

#### 6. Entropy and economics
Every system loses energy to heat. The question isn't "does it work" — it's "does output exceed total input, including waste heat, at 12 months?"

- Unit economics: cost to serve one unit of value at 10x scale. Do costs grow faster than revenue?
- Waste heat: is the spec 10x more complex than the problem? Complexity consumes engineering time with no output.
- Maintenance tax: what's the monthly cost of dependencies updating, APIs shifting, people leaving?
- Reversibility: if this fails at month 6, can we cleanly unwind it? Irreversible bets need a higher bar.
- Opportunity cost: every joule spent here is not spent elsewhere. Is this the best use of the team?

### Phase 4 — The friction budget

```
FORCE AVAILABLE:
- Engineering time: [X person-months]
- Budget: [$X]
- User patience: [X minutes to first value]
- Org willpower: [political capital]
- Runway: [time before results required]

FRICTION INVENTORY (each consumes force):
- [Friction 1]: [force consumed] — [source]
- [Friction 2]: [force consumed]
- TOTAL: [sum]

REMAINING FORCE: [available - total]
```

If remaining force is near zero or negative, the plan doesn't have enough energy to reach its destination. This is the most common failure mode — not that the physics are impossible, but that the budget runs out before arrival.

### Phase 5 — Score and synthesize

Rate each law:

| Score | Meaning |
| :--- | :--- |
| **Aligned** | Follows physics — evidence confirms reality supports it |
| **Fighting** | Soft violation — possible but consuming force |
| **Broken** | Hard violation — the bottle is going through the table |

**Verdict rules:**
- **BUILD** — No Broken, ≤2 Fighting, Fighting items have named mitigations, friction budget is positive
- **PIVOT** — 1-2 Broken that dissolve if you change scope, approach, or timeline
- **KILL** — 3+ Broken, OR Broken on Demand Gravity, OR friction budget is deeply negative

### Phase 6 — Deliver the report

```markdown
# Jensen Evaluation: [Name]
*Date: [date] | Sources: [N] | Confidence: [High/Medium/Low]*

## Verdict: [BUILD / PIVOT / KILL]
[2-3 sentences grounded in physics — forces in favor, forces opposed]

## The Causal Chain
[Full chain with weak links marked]

## Scorecard
| Law | Rating | One-line evidence |
| :--- | :--- | :--- |
| 1. Demand Gravity | Aligned/Fighting/Broken | — |
| 2. Adoption Friction | — | — |
| 3. Competitive Gravity | — | — |
| 4. Hard Constraints | — | — |
| 5. Org Inertia | — | — |
| 6. Entropy & Economics | — | — |

## Friction Budget
[Force available vs. total friction]

## Key Findings
### Aligned (green lights)
- [Finding] ([source](url))

### Fighting (yellow — manageable)
- [Risk] — Mitigation: [how] ([source](url))

### Broken (red — hard constraints)
- [Violation] — Why it's immovable ([source](url))

## If We Build: Critical Conditions
1. [Must be true for the chain to hold]
2. [Must be true]

## If We Pivot: What Changes the Physics
[Specific change that removes a Broken law]

## The Single Biggest Risk
"The single biggest reason this fails is: ___"

## Sources
1. [Title](url) — [one-line summary]
```

## Quality rules

1. **Every claim needs a source.** Gut feel is flagged `[unverified]`.
2. **Cross-reference.** Single-source claims are flagged.
3. **Search for failure.** For every "this could work", do a "this failed because" search.
4. **Acknowledge gaps.** No evidence → rate Fighting minimum, not Aligned.
5. **Name the biggest risk.** Always end with the single-biggest-reason line.

## Anti-patterns

- **Frictionless vacuum** — evaluating as if every step works perfectly
- **Confirmation gravity** — searching only for supporting evidence
- **Competitor blindness** — "no one does this" (search three ways; someone tried)
- **Happy path inertia** — what breaks first? That's the real plan
- **Sunk cost mass** — "we've already built Y" doesn't change whether Z's physics work
- **Premature precision** — unit economics to two decimals before you know anyone wants it
- **Abstraction anesthesia** — the table is still there under five layers of middleware
- **Force hallucination** — "we'll hire for that" is not a force, it's a plan to acquire one
