# Jensen Way

> "The next wave requires us to understand things like the laws of physics — friction, inertia, cause and effect. The fact that I tip that thing over, it's going to fall. When I set the bottle down, it's not going to go through the table. All of these common sense physical reasoning abilities that children have, that our pets have — most AIs don't have."
>
> — Jensen Huang

A decision framework for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that tests whether your product, feature, or spec **obeys reality** before you commit engineering time.

Most product plans operate in a frictionless vacuum — a fantasy world where users adopt because you ship, teams align because you scheduled a meeting, and systems scale because the architecture diagram says so.

Jensen Way forces you to trace the actual causal chain and check it against 8 laws of reality, producing a defensible **Build, Pivot, or Kill** verdict backed by evidence.

## The Toddler Test

The core insight: a child doesn't need equations to know that if you push something off a table, it falls. If you stack blocks too high, they topple. The bottle doesn't go through the table.

Before any research, Jensen Way makes you write out the full cause-and-effect chain from "we start building" to "this matters" — then asks: **would a child accept each link?** If you need jargon or "if everything goes right" qualifiers, that link is weak.

## The 8 Laws of Reality

| # | Law | The Toddler Version |
|---|-----|---------------------|
| 1 | **Gravity of Demand** (Market Physics) | "Do people actually want this, or do you just wish they did?" |
| 2 | **Friction of Adoption** (User Physics) | "Is this solving something that actually hurts, or just something slightly annoying?" |
| 3 | **Competitive Gravity** (Moat Physics) | "If someone bigger takes your toy, can you get it back?" |
| 4 | **The Law of Scaling** (Amdahl's Law) | "If you push harder, does it actually go faster, or does it just get stuck?" |
| 5 | **The Table Test** (Hard Constraints) | "What's the thing that absolutely cannot happen no matter how hard you try?" |
| 6 | **Organizational Inertia** (Conway's Law) | "Do the people who need to work together actually talk to each other?" |
| 7 | **Economic Thermodynamics** (Energy vs. Output) | "Is this worth the effort, or are you working really hard for something small?" |
| 8 | **Entropy** (Temporal Physics) | "If you stop paying attention to this, does it break?" |

## The Verdict

Each law gets a P-Level score:

| Score | Meaning | Signal |
|-------|---------|--------|
| **P-Level 1** | Follows physics — evidence confirms it | Forces are aligned |
| **P-Level 2** | Soft violation — possible but fighting friction | Needs more force or less friction |
| **P-Level 3** | Hard violation — the bottle is going through the table | Redesign or kill |

**BUILD** — No P3s, at most 2 P2s with mitigations, friction budget is positive

**PIVOT** — 1-2 P3s that dissolve if you change scope, approach, or timeline

**KILL** — 3+ P3s, OR P3 on Demand Gravity (no demand = nothing moves), OR friction budget is deeply negative

---

## Installation

### For Claude Code (CLI / Desktop / Web)

**Option A: Add as a skill directory (recommended)**

```bash
# From your project root
mkdir -p .claude/skills/jensen-way
curl -o .claude/skills/jensen-way/SKILL.md \
  https://raw.githubusercontent.com/agentoptics/jensen-way/main/SKILL.md
```

Then in your project's `CLAUDE.md`, add:

```markdown
# Skills
- **jensen-way** (`.claude/skills/jensen-way/SKILL.md`) — Physics-of-reality decision framework. Trigger: `/jensen-way`
When the user types `/jensen-way`, invoke the Skill tool with `skill: "jensen-way"` before doing anything else.
```

**Option B: Add as a custom slash command**

```bash
# From your project root
mkdir -p .claude/commands
curl -o .claude/commands/jensen-way.md \
  https://raw.githubusercontent.com/agentoptics/jensen-way/main/SKILL.md
```

This makes `/jensen-way` available as a slash command in Claude Code.

**Option C: Copy into your global config (available in all projects)**

```bash
mkdir -p ~/.claude/skills/jensen-way
curl -o ~/.claude/skills/jensen-way/SKILL.md \
  https://raw.githubusercontent.com/agentoptics/jensen-way/main/SKILL.md
```

Then in your global `~/.claude/CLAUDE.md`, add the same skill reference as Option A.

### For other AI coding assistants

The framework is in a single Markdown file ([SKILL.md](SKILL.md)). You can:

1. Copy the contents into your system prompt or custom instructions
2. Reference it as a file in your project that the assistant can read
3. Paste it into any conversation when you need to evaluate an idea

The framework is model-agnostic — it works with any AI assistant that can follow structured workflows.

## Usage

### Quick start

Just ask your AI assistant:

```
Should we build [your idea here]? Use the Jensen Way framework.
```

Or if installed as a skill:

```
/jensen-way

Evaluate whether we should build a real-time collaboration feature for our note-taking app.
```

### What you'll get

1. **A framed decision** — what exactly is being evaluated and why
2. **A causal chain** — every step from "we build it" to "it matters," with weak links identified
3. **Evidence-backed evaluation** — each of the 8 laws scored with real sources
4. **A friction budget** — force available vs. friction total (if negative, the plan runs out of energy)
5. **A verdict** — BUILD, PIVOT, or KILL with specific conditions and the single biggest risk

### Example prompts

```
/jensen-way Should we add AI-powered search to our documentation platform?
```

```
/jensen-way We're deciding between building our own auth system vs using Auth0. Evaluate both options.
```

```
/jensen-way Our PM wants to build a mobile app. We're a 3-person team with no mobile experience.
The timeline is 8 weeks. Is this feasible?
```

```
/jensen-way Evaluate whether we should fork an open-source project and maintain our own version
vs contributing upstream.
```

## How it works

```
Phase 0: Frame the Decision
    │  What are we evaluating? Why? Time horizon?
    ▼
Phase 1: Trace the Causal Chain (The Toddler Test)
    │  Write every step from "build" to "matters"
    │  Mark weak links where the chain assumes a frictionless vacuum
    ▼
Phase 2: Research (Evidence Gathering)
    │  Search for real data — especially failure cases
    │  Focus on weak links from Phase 1
    ▼
Phase 3: Evaluate Against the 8 Laws of Reality
    │  Every law, every checkbox, skip nothing
    │  Each law has a "toddler version" — if you can't answer it, you don't understand the physics
    ▼
Phase 4: The Friction Budget
    │  Force available vs. friction total
    │  If negative, the plan dies before arrival
    ▼
Phase 5: Score and Synthesize
    │  P-Level per law → overall verdict
    ▼
Phase 6: Deliver the Report
       Verdict, scorecard, friction budget, sources, biggest risk
```

## Philosophy

Jensen Way is built on the observation that most product failures aren't caused by bad engineering — they're caused by **ignoring physics**:

- Building something nobody wants (ignoring demand gravity)
- Underestimating how hard it is to change user behavior (ignoring friction)
- Assuming teams will coordinate perfectly (ignoring organizational inertia)
- Planning for the happy path only (ignoring entropy)
- Not knowing what can't be done (ignoring hard constraints)

A child wouldn't make these mistakes. They have an intuitive understanding of cause and effect, friction, and hard limits. This framework brings that intuition to product decisions.

## Contributing

Issues and PRs welcome. If you've used Jensen Way to make a decision (build or kill), we'd love to hear about it — open an issue with your experience.

## License

MIT

## Credits

Built by [Agent Optics](https://github.com/agentoptics). Inspired by Jensen Huang's philosophy on the physics of computation.
