# Examples

Two worked examples showing Jensen Way applied end-to-end. The first is a realistic PIVOT, the second a decisive KILL. Both are illustrative — use them as templates, not evidence.

---

## Example 1 — PIVOT: "Should we add a real-time collaborative editor to our docs tool?"

**Evaluating:** feature addition to an existing B2B SaaS docs product
**Decision type:** build vs. don't build vs. integrate
**Time horizon:** 1 quarter

### Causal chain

1. We build a CRDT-based real-time editor → because users ask for "Google Docs-like" collaboration
2. Which causes users to invite teammates into docs → because real-time editing makes async handoffs feel slow
3. Which leads to higher seat expansion per account → because every invited editor becomes a potential paid seat
4. Which results in +20% ARR expansion from existing accounts

**Weak links flagged:**
- 2 → 3: "teammates get invited" — *who makes that happen? What's the activation path?*
- 3 → 4: "invited editor becomes a paid seat" — *our pricing is per-workspace, not per-seat today. This whole chain assumes a pricing change we haven't committed to.*

### Scorecard

| Law | Rating | Evidence |
|---|---|---|
| 1. Demand Gravity | **Aligned** | 34 support tickets last quarter asking for multiplayer; Notion/Coda dominant in G2 reviews of competitors |
| 2. Adoption Friction | **Fighting** | Users already have Google Docs habits; switching means re-establishing trust in a second editor surface |
| 3. Competitive Gravity | **Fighting** | Notion, Coda, Confluence all have real-time. Our wedge ("docs tied to code") doesn't become stronger just because we add multiplayer |
| 4. Hard Constraints | **Broken** | CRDT correctness at scale is a 6-12 month engineering problem. Our 1-quarter horizon is the table the bottle is trying to go through |
| 5. Org Inertia | **Fighting** | We have no real-time expertise on staff. "We'll learn CRDTs" is a force hallucination |
| 6. Entropy & Economics | **Fighting** | Every future feature (comments, suggestions, revision history) now has to be CRDT-aware. Maintenance tax compounds |

### Friction budget

```
FORCE AVAILABLE:
- Engineering: 3 engineers × 3 months = 9 person-months
- User patience: migration must be invisible
- Runway: 2 quarters until Series B

FRICTION (estimated):
- CRDT research + prototype: 3 person-months
- Production-grade CRDT (offline, conflicts): 6+ person-months (per Figma/Linear post-mortems)
- Migrating existing docs to new data model: 2 person-months
- Rebuilding comments/revisions on CRDT: 3 person-months

TOTAL FRICTION: 14 person-months vs. 9 available
REMAINING FORCE: −5 person-months
```

### Verdict: **PIVOT**

The demand is real but the time horizon makes the hard-constraints law Broken. Options that change the physics:

- **Integrate Liveblocks/Yjs** as a vendor → removes the CRDT engineering problem (Hard Constraints becomes Aligned)
- **Ship async "suggestions" + live cursor presence only** → 80% of the perceived value at 20% of the engineering cost (Friction budget turns positive)
- **Defer one quarter** → unchanged physics, just later; not a real option

### Single biggest risk

> "The single biggest reason this fails is: CRDT correctness is not a code problem, it's a physics problem, and shipping it in a quarter with no in-house expertise means we will ship a system that loses user data under conflict — the one failure mode that destroys trust in a docs product."

---

## Example 2 — KILL: "Should we build our own vector database?"

**Evaluating:** whether a 4-person AI startup should build a custom vector DB instead of using Pinecone/Weaviate/pgvector
**Decision type:** build vs. buy
**Time horizon:** 2 months (before next funding milestone)

### Causal chain

1. We build a custom vector DB → because off-the-shelf vendors are "too expensive at scale"
2. Which causes our cost-per-query to drop below Pinecone's → because we control the storage layer
3. Which leads to better gross margins → because inference costs dominate our P&L
4. Which results in a healthier unit economics story for the Series A

**Weak links flagged:**
- 1 → 2: "cost drops below Pinecone" — *at what query volume? We're at 50k queries/month. Pinecone's free tier covers this.*
- 2 → 3: "better gross margins" — *vector storage is currently 3% of our costs. LLM API calls are 82%. We're optimizing the wrong line.*

### Scorecard

| Law | Rating | Evidence |
|---|---|---|
| 1. Demand Gravity | **Broken** | No customer has ever asked about our vector backend. Our users care about answer quality, not storage layer |
| 2. Adoption Friction | n/a | Internal tool, no external adoption |
| 3. Competitive Gravity | **Broken** | Pinecone ($100M+ raised), Weaviate, Qdrant, pgvector all exist. "We'll execute better" against companies with 100x the resources and 3-year head starts is velocity, not gravity |
| 4. Hard Constraints | **Broken** | ANN index correctness + crash-safe persistence + multi-tenant isolation is a multi-year engineering problem. Our 2-month horizon is the table |
| 5. Org Inertia | **Broken** | Nobody on the team has built a database. "We'll learn distributed systems" with 2 months of runway is force hallucination |
| 6. Entropy & Economics | **Broken** | Build: 4 engineers × 2 months = 8 person-months. Buy: $200/month for pgvector on managed Postgres. Payback period for building is literally infinite at our scale |

### Friction budget

```
FORCE AVAILABLE:
- Engineering: 4 engineers × 2 months = 8 person-months (entire team, zero other work)
- Runway: 4 months
- User patience: users already complaining about answer quality

FRICTION:
- Build a correct ANN index: 3+ person-months
- Production-grade persistence + backup: 2 person-months
- Ops (monitoring, scaling, on-call): ongoing, 20% of team forever

TOTAL: 5+ person-months of upfront + permanent 20% ops tax
REMAINING FORCE: near zero, and the team stops shipping features during this period
```

### Verdict: **KILL**

Five of six laws are Broken. Demand Gravity is Broken (no one asked), which alone triggers KILL. This is a textbook sunk-cost-of-ego decision masquerading as a cost-optimization decision.

### Single biggest risk

> "The single biggest reason this fails is: we will spend two months building infrastructure nobody asked for, miss our Series A milestone because we stopped shipping user-facing features, and still not have matched Pinecone's correctness on our first release."

### What would change the physics

Nothing in this quarter. If we ever reach a scale where vector storage is 30%+ of our costs (not 3%), re-evaluate. Until then, use pgvector.

---

## How to read these examples

Both evaluations look boring — short, direct, grounded in arithmetic and competitor names. That's the point. When the output is short, the thinking was rigorous. When the output is a 20-slide deck with a "we believe" section, the physics are probably being hidden.

The whole framework is one question asked six times: **what force is available, what friction opposes it, and does the math leave enough energy to reach the destination?**
