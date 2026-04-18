# Jensen Way

A physics-of-reality decision framework for AI coding assistants. Tests whether a product, feature, or spec **obeys reality** before you commit engineering time — and produces a defensible **Build / Pivot / Kill** verdict backed by evidence.

> "The next wave requires us to understand things like the laws of physics — friction, inertia, cause and effect. The fact that I tip that thing over, it's going to fall. When I set the bottle down, it's not going to go through the table. All of these common sense physical reasoning abilities that children have, that our pets have — most AIs don't have."
>
> — Jensen Huang, [Hill & Valley Forum 2025](https://www.youtube.com/watch?v=nkhrEnuZi20&t=485s), interviewed by Jacob Helberg, May 3, 2025

Jensen was describing **Physical AI** — the next wave after perception, generative, and agentic AI. We noticed the same observation applies to most product plans: they operate in a frictionless vacuum where users adopt because you ship, teams align because you scheduled a meeting, and systems scale because the architecture diagram says so.

Jensen Way ports that insight to product decisions. A child shouldn't need equations to follow your causal chain — if they can't, the physics are probably against you.

## Install

```bash
/plugin marketplace add agentoptics/jensen-way
```

Or drop the single-file skill into your project:

```bash
mkdir -p .claude/skills/jensen-way
curl -o .claude/skills/jensen-way/SKILL.md \
  https://raw.githubusercontent.com/agentoptics/jensen-way/main/skills/jensen-way/SKILL.md
```

Then:

```
/jensen-way Should we add real-time collaboration to our docs product?
```

## What you get back

1. A framed decision (what, why, time horizon)
2. A **causal chain** from "we build it" to "it matters" — with weak links marked
3. Evidence-backed evaluation against **6 laws of reality**
4. A **friction budget** — force available vs. friction total
5. A verdict: **BUILD / PIVOT / KILL** with the single biggest risk named

See [EXAMPLES.md](EXAMPLES.md) for two worked evaluations — one PIVOT, one KILL.

## The 6 laws

| # | Law | The toddler version |
|---|-----|---------------------|
| 1 | **Gravity of demand** | "Do people actually want this, or do you just wish they did?" |
| 2 | **Friction of adoption** | "Is this solving something that hurts, or just something slightly annoying?" |
| 3 | **Competitive gravity** | "If someone bigger takes your toy, can you get it back?" |
| 4 | **Hard constraints** (the table test) | "What's the thing that absolutely cannot happen no matter how hard you try?" |
| 5 | **Organizational inertia** (Conway's Law) | "Do the people who need to work together actually talk to each other?" |
| 6 | **Entropy & economics** | "If you stop paying attention to this, does it break? Is it worth the effort?" |

Each law scores **Aligned / Fighting / Broken**.

- **BUILD** — no Broken, at most 2 Fighting with named mitigations, friction budget positive
- **PIVOT** — 1-2 Broken that dissolve if scope / approach / timeline changes
- **KILL** — 3+ Broken, OR Broken on Demand Gravity, OR friction budget deeply negative

## Example prompts

```
/jensen-way Should we add AI-powered search to our documentation platform?
```

```
/jensen-way We're deciding between building our own auth vs. using Auth0. Evaluate both.
```

```
/jensen-way Our PM wants to ship a mobile app in 8 weeks. 3-person team, no mobile experience. Feasible?
```

```
/jensen-way Fork an open-source project and maintain our own version, or contribute upstream?
```

## Philosophy

Most product failures aren't caused by bad engineering — they're caused by **ignoring physics**:

- Building something nobody wants (ignoring demand gravity)
- Underestimating how hard it is to change user behavior (ignoring friction)
- Assuming teams will coordinate perfectly (ignoring organizational inertia)
- Planning for the happy path only (ignoring entropy)
- Not knowing what can't be done (ignoring hard constraints)

A child wouldn't make these mistakes. They have an intuitive understanding of cause and effect, friction, and hard limits. Jensen Way brings that intuition to product decisions — with evidence attached.

## Works with any AI assistant

The framework is in a single Markdown file: [skills/jensen-way/SKILL.md](skills/jensen-way/SKILL.md). Model-agnostic. Copy it into your system prompt, paste it into a conversation, or reference it as a project file. It works with any assistant that can follow a structured workflow.

## Contributing

Issues and PRs welcome. If you've used Jensen Way to make a decision (build *or* kill), open an issue — real-world runs make the framework better.

## License

MIT

## Credits

Built by [Agent Optics](https://github.com/agentoptics). The physics framing is drawn directly from Jensen Huang's Hill & Valley Forum 2025 remarks on Physical AI. The extension from Physical AI to product decisions is ours.
