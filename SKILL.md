---
name: jensen-way
description: Research-backed decision framework grounded in Jensen Huang's "physics of reality" philosophy. Tests whether a product, feature, or spec obeys the laws of friction, inertia, cause-and-effect, and hard constraints that children intuitively understand but most plans ignore. Produces a defensible build/pivot/kill verdict with evidence. Use when evaluating product ideas, feature specs, or build-vs-buy decisions.
origin: custom
---

# Skill: Jensen Huang Theory Validator (Deep Context Edition)

## The Jensen Philosophy

> "The next wave requires us to understand things like the laws of physics — friction, inertia, cause and effect. The fact that I tip that thing over, it's going to fall. When I set the bottle down, it's not going to go through the table. All of these common sense physical reasoning abilities that children have, that our pets have — most AIs don't have."

This is not a metaphor. Most product plans, feature specs, and technical designs operate in a **frictionless vacuum** — a fantasy world where users adopt because you ship, teams align because you scheduled a meeting, and systems scale because the architecture diagram says so.

Children don't need equations. They understand that:
- **If you push something off the table, it falls.** (Cause has effect. Every action produces consequences — not the ones you intended, the ones physics dictates.)
- **If you stack blocks too high, they topple.** (Complexity has weight. Every layer added makes the structure less stable, not more.)
- **The bottle doesn't go through the table.** (Hard constraints exist. No amount of cleverness, funding, or willpower removes them. You must go around.)
- **Heavy things are hard to move.** (Inertia is real. Users, teams, codebases, and markets resist change in proportion to their mass.)
- **Sliding on carpet is harder than sliding on ice.** (Friction is real. Every handoff, integration, approval, and context switch dissipates energy.)

**The core test:** If you have to write a 10-page document to convince someone this will work, the physics are probably against you. A child should be able to follow the causal chain.

## Purpose

Determine if a product, feature, or spec **obeys reality** — not just technically, but across the full causal chain from "we build it" to "it matters." Produce a research-backed verdict: **Build, Pivot, or Kill.**

## When to Activate

- User wants to evaluate whether to build a product or feature
- Build-vs-buy decisions
- "Should we do X?" or "Is X worth building?"
- Feature spec validation before committing engineering time
- Competitive analysis tied to a build decision
- User says "jensen", "evaluate this idea", "should we build", "is this feasible"

---

## Workflow

### Phase 0: Frame the Decision

Before evaluating, get clarity on what's being judged and why.

**Ask 1-3 clarifying questions (skip if already clear):**
- "What's the thing we're evaluating? A whole product, a feature, or a technical approach?"
- "What's your goal — deciding whether to start, deciding whether to continue, or choosing between options?"
- "What's the time horizon — MVP in weeks, or production system in months?"

Then state the frame:

```
EVALUATING: [product/feature/spec name]
DECISION TYPE: [build / continue / choose between A vs B]
TIME HORIZON: [weeks / months / quarters]
CONTEXT: [what we already know]
```

### Phase 1: Trace the Causal Chain (The Toddler Test)

**Before researching anything**, write out the full cause-and-effect chain from "we start building" to "this matters." Every step must follow from the previous one the way gravity follows from letting go.

```
CAUSAL CHAIN:
1. We build [X]           → because [reason]
2. Which causes [Y]       → because [mechanism]
3. Which leads to [Z]     → because [mechanism]
...
N. Which results in [outcome that matters]
```

**Then apply the Toddler Test:** Read each arrow (`→ because`). Would a child accept that explanation? If you need jargon, abstractions, or "if everything goes right" qualifiers — that link is weak. Mark it.

```
WEAK LINKS IN THE CHAIN:
- Step 3→4: "Users will switch" — WHY would they? What force overcomes their inertia?
- Step 5→6: "Teams will integrate" — WHO makes them? What friction exists?
```

Every weak link is a place where the plan **assumes a frictionless vacuum.** These become the focus of research.

### Phase 2: Research (Evidence Gathering)

Do NOT evaluate from gut feel. Gather evidence, especially for the weak links identified in Phase 1.

**Research strategy:**
- Use available web search tools (exa, firecrawl, web search) to find evidence
- Use 2-3 keyword variations per question
- Prefer: official docs, benchmarks, case studies, post-mortems > blog posts > opinions
- For market questions: look for TAM data, competitor funding, pricing pages, user reviews
- For technical questions: look for benchmarks, architecture post-mortems, scaling stories
- **Critically:** Search for failure cases. "Why X failed" and "problems with X" are more revealing than success stories.

**Parallel research with subagents (for broad evaluations):**
```
Launch up to 3 research agents in parallel:
1. Agent 1: Market + User reality (demand evidence, competitor traction, user pain)
2. Agent 2: Technical reality (scaling limits, dependency risks, hard constraints)
3. Agent 3: Org + Economic + Temporal reality (team capacity, costs, entropy)
```

Each agent searches, reads 2-3 key sources in full, and returns findings with source URLs.

### Phase 3: Evaluate Against the 8 Laws of Reality

Run every law. Check every box. Skip nothing. For each, ask: **"What does a child's intuition say?"**

---

#### 1. Gravity of Demand (Market Physics)
*If you build it, they will come — said every failed startup ever. Gravity only pulls things that have mass. Does demand for this have mass, or is it weightless?*

- [ ] **Demand Signal:** Is there measurable evidence that people want this? (Search volume, waitlists, forum complaints, competitor traction, RFPs, people paying for bad alternatives)
- [ ] **TAM Reality:** What's the realistic addressable market? Not the "if everyone in the world..." number — the number of people who are actively in pain today. Cite it.
- [ ] **Timing Force:** What changed *recently* that makes this possible now when it wasn't before? If nothing changed, ask why no one built it yet — they probably tried and the physics didn't work.

*The toddler version: "Do people actually want this, or do you just wish they did?"*
*Evidence required: at least 2 sources on demand. "I think people want this" is not a force — it's a hope.*

---

#### 2. Friction of Adoption (User Physics)
*Users are heavy objects at rest. Moving them requires force greater than friction. How much friction exists between "user hears about this" and "user's life is better"?*

- [ ] **Current Inertia:** How are users solving this today? Even a bad solution has inertia — they know it, they've built workflows around it, their data is in it. What's the mass of that inertia?
- [ ] **Switching Friction:** Map every friction point: signup, learning curve, data migration, behavior change, team buy-in, procurement. Each one dissipates adoption force. If total friction > total pain, the object doesn't move.
- [ ] **"Hair on Fire" Test:** Is the pain so intense that users will push through friction on their own? Or does this require you to push them? Painkillers sell themselves. Vitamins need marketing budgets.
- [ ] **Time to Value:** How many minutes/hours/days between "user starts" and "user gets value"? Every minute is friction. If it's days, most users will stop pushing.

*The toddler version: "Is this solving something that actually hurts, or just something that's slightly annoying?"*

---

#### 3. Competitive Gravity (Moat Physics)
*If this works, every large body in the vicinity will be pulled toward it. What keeps them from crushing you?*

- [ ] **Existing Mass:** Who already does this (or something close)? What's their mass? (Funding, users, revenue, data, distribution) Name them with links.
- [ ] **Gravitational Defense:** What creates a gravity well that keeps users in your orbit? (Data network effects, integration depth, switching costs, regulatory capture, proprietary data) If the answer is "we'll execute better" — that's velocity, not gravity. Velocity fades; gravity doesn't.
- [ ] **Incumbent Inertia (for you):** If a big player copies this in 6 months, they have more mass. What do you have that they can't replicate? (Usually: speed, focus, or a specific insight about the problem they'd never prioritize)

*The toddler version: "If someone bigger takes your toy, can you get it back?"*
*Evidence required: name specific competitors. "No one does this" is almost always wrong — search three different ways before concluding.*

---

#### 4. The Law of Scaling (Amdahl's Law)
*You can't speed up a horse by adding more horses — unless the road is wide enough for all of them. Is this task actually parallelizable, or is there a hard sequential bottleneck?*

- [ ] **Parallel Efficiency:** If we throw 10x the compute/people/money at this, do we get 10x the output? What's the actual scaling curve? Where does it flatten?
- [ ] **Sequential Floor:** What part of this *cannot* be parallelized? Identify it explicitly. That is the true speed limit — the rest is just noise.
- [ ] **Scale Cliff:** At what scale does the current approach hit a wall? (10x users? 100x data? 1000x requests?) What changes at that cliff — a rewrite, a new architecture, or a fundamental redesign?

*The toddler version: "If you push harder, does it actually go faster, or does it just get stuck?"*

---

#### 5. The Table Test (Hard Constraints)
*The bottle doesn't go through the table. What are the tables — the immovable constraints that no amount of engineering routes through?*

- [ ] **Physics Floors:** What are the hard lower bounds? (Speed of light for latency, human attention span for UX, regulatory requirements for compliance, mathematical limits for algorithms)
- [ ] **Dependency Gravity:** List every critical 3rd-party dependency. For each: what happens if it disappears, reprices, or throttles? The table under your bottle is someone else's platform.
- [ ] **Underlying Reality:** Do we understand the actual mechanism beneath our abstractions? (How the DB locks, how the LLM tokenizes, how the CDN caches, how the payment processor settles) Abstractions hide tables — until you slam into them.
- [ ] **Rug-Pull Risk:** Are we building on a surface that could be pulled away? Find precedents of the platform changing terms, pricing, or APIs.

*The toddler version: "What's the thing that absolutely cannot happen no matter how hard you try?"*

---

#### 6. Organizational Inertia (Conway's Law)
*Organizations are heavy objects. They move slowly. They resist changes to their trajectory. The software will mirror the communication structure — not the org chart, the actual one.*

- [ ] **Structural Alignment:** If the spec requires two systems to talk perfectly, do the two teams actually talk to each other today? If not, adding a Slack channel won't create alignment — that's like expecting two heavy objects to suddenly synchronize because you put them closer together.
- [ ] **Team Mass (Brooks' Law):** If this falls behind, can we simplify scope? Or does adding people create more coordination friction than productive force? A project with N people has N(N-1)/2 communication channels — that's physics.
- [ ] **Skill Gravity:** Does the team have the skills this requires? Acquiring new skills has enormous friction (months, not days). Plans that assume "we'll learn X" are assuming frictionless skill transfer.
- [ ] **Decision Friction:** How many approvals, reviews, or sign-offs sit between "code complete" and "shipped"? Each one is a friction point that dissipates momentum.

*The toddler version: "Do the people who need to work together actually talk to each other?"*

---

#### 7. Economic Thermodynamics (Energy vs. Output)
*Every system loses energy to heat. The question isn't "does it work" but "does the useful output exceed the total energy input, including all the waste heat?"*

- [ ] **Unit Economics:** What does it cost to serve one unit of value? (Include: compute, API calls, storage, support, on-call, maintenance) Does that math work at 10x scale, or do costs grow faster than revenue?
- [ ] **Waste Heat:** Is the spec 10x more complex than the problem requires? Complexity is waste heat — it doesn't produce output, but it consumes energy (engineering time, cognitive load, debugging).
- [ ] **Build vs. Buy Thermodynamics:** Could we get 80% of the value at 20% of the energy by buying/integrating? What's the honest comparison? "But we'd own it" is not a thermodynamic argument.
- [ ] **Opportunity Cost:** Every joule of energy spent here is not spent elsewhere. What's the most valuable thing this team could be doing instead? Is this it?

*The toddler version: "Is this worth the effort, or are you working really hard for something small?"*

---

#### 8. Entropy (Temporal Physics)
*Everything decays. Order requires constant energy. The question isn't "will it work on day one" but "what does it look like after 12 months of entropy?"*

- [ ] **Bit Rot Resistance:** Dependencies update. APIs change. Platforms shift. People leave. Will this survive on autopilot, or does it require constant energy to maintain? What's the monthly maintenance "tax"?
- [ ] **Broken Window Effect:** Are we building on top of disorder? If the existing codebase/ecosystem is messy, friction will be 2-3x higher than estimated. Disorder compounds — each broken window invites the next.
- [ ] **Reversibility:** If this fails at month 6, can we cleanly unwind it? Or does it create irreversible commitments — data migrations, public APIs, contractual obligations, user expectations? Irreversible bets should clear a higher bar.
- [ ] **Entropy Direction:** Is this making the overall system more ordered or more disordered? Adding another microservice to a system that already has too many is adding entropy, regardless of how clean the new one is.

*The toddler version: "If you stop paying attention to this, does it break?"*

---

### Phase 4: The Friction Budget

Every plan has a finite amount of **force** (time, money, energy, willpower, user patience). Friction eats that force. This step makes the budget explicit.

```
FORCE AVAILABLE:
- Engineering time: [X person-months]
- Budget: [$X]
- User patience: [X minutes to first value]
- Org willpower: [how much political capital to spend]
- Runway: [how long before we need results]

FRICTION INVENTORY (each item consumes force):
- [Friction 1]: [estimated force consumed] — [source/evidence]
- [Friction 2]: [estimated force consumed]
- ...
- TOTAL FRICTION: [sum]

REMAINING FORCE AFTER FRICTION: [available - total]
```

**If remaining force is near zero or negative, the plan doesn't have enough energy to reach its destination.** This is the most common failure mode — not that the physics are impossible, but that the force budget runs out before arrival.

### Phase 5: Score and Synthesize

#### The "Jensen" Execution Score

Rate each law independently, then compute the overall verdict.

| Law | Rating | Evidence Summary |
| :--- | :--- | :--- |
| 1. Demand Gravity | P1 / P2 / P3 | [one line] |
| 2. Adoption Friction | P1 / P2 / P3 | [one line] |
| 3. Competitive Gravity | P1 / P2 / P3 | [one line] |
| 4. Scaling (Amdahl's) | P1 / P2 / P3 | [one line] |
| 5. Hard Constraints (Table Test) | P1 / P2 / P3 | [one line] |
| 6. Org Inertia (Conway's) | P1 / P2 / P3 | [one line] |
| 7. Economic Thermodynamics | P1 / P2 / P3 | [one line] |
| 8. Entropy (Temporal) | P1 / P2 / P3 | [one line] |

**Rating key:**
| Score | Meaning | Signal |
| :--- | :--- | :--- |
| **P-Level 1** | Follows physics — evidence confirms reality supports it | Green: forces are aligned |
| **P-Level 2** | Soft violation — possible but fighting friction | Yellow: needs more force or less friction |
| **P-Level 3** | Hard violation — the bottle is going through the table | Red: redesign or kill |

**Overall verdict rules:**
- **BUILD** — No P3s, at most 2 P2s, P2s have named mitigations, friction budget is positive
- **PIVOT** — 1-2 P3s that dissolve if you change scope, approach, or timeline
- **KILL** — 3+ P3s, OR P3 on Demand Gravity (no demand = no force = nothing moves), OR friction budget is deeply negative

### Phase 6: Deliver the Report

```markdown
# Jensen Evaluation: [Product/Feature Name]
*Date: [date] | Sources: [N] | Confidence: [High / Medium / Low]*

## Verdict: [BUILD / PIVOT / KILL]
[2-3 sentence summary grounded in physics — what forces support this, what forces oppose it]

## The Causal Chain
[From Phase 1 — the full chain with weak links marked]

## Scorecard
[The table from Phase 5]

## The Friction Budget
[From Phase 4 — force available vs. friction total]

## Key Findings

### Forces in Favor (Green Lights)
- [Finding 1] ([source](url))
- [Finding 2] ([source](url))

### Friction to Manage (Yellow Lights)
- [Risk 1] — Mitigation: [how to reduce friction] ([source](url))
- [Risk 2] — Mitigation: [plan]

### Fighting Physics (Red Lights)
- [Violation 1] — Why it's a hard constraint: [explanation] ([source](url))
- [Violation 2] — Why it's a hard constraint: [explanation]

## If We Build: Critical Conditions
1. [Must be true for the causal chain to hold]
2. [Must be true for the causal chain to hold]
3. [Must be true for the causal chain to hold]

## If We Pivot: What Changes the Physics
- [Specific change that removes a hard constraint or eliminates major friction]

## The Single Biggest Risk
"The single biggest reason this fails is: ___"

## Sources
1. [Title](url) — [one-line summary]
2. ...

## Methodology
Evaluated [N] sources across [search tools used]. Sub-questions: [list].
Laws with insufficient evidence are flagged — absence of evidence is not evidence of absence.
```

---

## Quality Rules

1. **Every claim needs a source.** Gut feel gets flagged as `[unverified]`.
2. **Cross-reference.** If only one source says it, flag as unverified.
3. **Recency matters.** Prefer sources from the last 12 months. Flag stale data.
4. **Acknowledge gaps.** If you couldn't find evidence for a law, say so. Rate it P2 minimum.
5. **No hallucination.** "Insufficient data found" is a valid and respected answer.
6. **Separate fact from inference.** Label estimates, projections, and opinions clearly.
7. **Search for failure.** For every "this could work" search, do a "this failed because" search.
8. **Name the biggest risk.** Always end with: "The single biggest reason this fails is: ___"

## Anti-Patterns (Common Ways People Ignore Physics)

- **The Frictionless Vacuum:** Evaluating the plan as if every step works perfectly. Reality has friction at every joint.
- **Confirmation Gravity:** Searching only for evidence that supports building. The universe doesn't care about your hypothesis — search for disconfirmation.
- **Competitor Blindness:** "No one does this." Search three different ways. Someone almost certainly tried. Find out why they stopped.
- **Happy Path Inertia:** Evaluating only the case where everything goes right. What breaks first? That's the real plan.
- **Sunk Cost Mass:** "We've already built Y, so we should build Z." Sunk cost adds mass to your current trajectory (inertia), but it doesn't change whether Z's physics work. Evaluate Z on its own.
- **Premature Precision:** Calculating unit economics to two decimal places when you don't know if anyone wants it. Demand Gravity first — if nobody's pulling, the rest doesn't matter.
- **Abstraction Anesthesia:** Hiding hard constraints behind layers of abstraction. The table is still there even if you can't see it through five layers of middleware.
- **Force Hallucination:** Assuming resources (time, money, talent, willpower) that don't concretely exist yet. "We'll hire for that" is not a force — it's a plan to acquire force, which itself has friction.
