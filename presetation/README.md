# Presentation Plugin

Professional sales presentation creation for webinars, marathons, and workshops that sell online courses.

Uses embedded **Hristosenko methodology** for high-converting presentations.

## Installation

Copy the `presetation` folder to your Claude plugins directory:

```bash
# macOS/Linux
cp -r presetation ~/.claude/plugins/

# Or add to your project's .claude/plugins/ folder
cp -r presetation .claude/plugins/
```

## Quick Start

```
/presentation
```

This launches the orchestrator which guides you through the complete workflow.

## What It Creates

For each presentation project, you get:

| File | Description |
|------|-------------|
| `brainstorming.md` | Requirements, audience, product details |
| `structure.md` | Presentation structure with timing |
| `script.md` | Complete script with CTAs |
| `slides.md` | Slide outlines with visual recommendations |
| `emails.md` | Pre/post event email sequences |
| `qa-review.md` | Quality score and issues |

All files saved to: `project/{project-name}/`

## Workflow (8 Steps)

```
1. Brainstorming    → Gather requirements (AskUserQuestion)
2. Structure        → Generate presentation structure
3. Content          → Write script (WHY, not HOW)
4. CTA & Emotional  → Add 15+ CTAs, emotional triggers
5. Slides           → Create slide outlines
6. Emails           → Generate email sequences
7. QA Review        → Score against methodology (pass: 80+)
8. Delivery         → Final package ready
```

## Event Types Supported

| Type | Duration | Conversion |
|------|----------|------------|
| **Webinar** | 60-90 min | 5-15% |
| **Marathon** | 3-5 days | 8-20% |
| **Workshop** | 2-4 hours | 10-25% |

## Skills Reference

Use these directly if needed:

| Skill | Purpose |
|-------|---------|
| `presentation:pres-orchestrator` | Main workflow coordinator |
| `presentation:pres-brainstorming` | Collect requirements |
| `presentation:pres-structure` | Generate structure |
| `presentation:pres-content` | Write script |
| `presentation:pres-cta-emotional` | Add CTAs & emotions |
| `presentation:pres-slides` | Outline slides |
| `presentation:pres-emails` | Email sequences |
| `presentation:pres-qa-review` | Quality validation |

## Embedded Methodology

All Hristosenko principles are embedded in the skills:

- **Ladder of Conviction** (5 steps to sale)
- **Content-Sales Paradox** (teach WHY, not HOW)
- **15+ Unique CTAs** with 5 emotional hook types
- **3-Tier Tariff Structure** with proper price gaps
- **Dark Future Technique** (FROM motivation > TO motivation)
- **Minimal Contact Principle** for emails
- **Value Formula**: (Result × Probability) / (Time × Effort)
- **4 Value Depths**: Have → Do → Feel → Be

## Quality Standards

QA Review scores presentations on 100 points:

| Category | Points |
|----------|--------|
| Structure & Flow | 20 |
| Content Methodology | 25 |
| Emotional Triggers | 15 |
| CTAs & Conversion | 20 |
| Bonuses & Materials | 20 |

**Pass threshold: 80 points**

## Example Usage

```
User: /presentation

Claude: I'm using the pres-orchestrator skill to create your presentation.

        What type of sales event are you creating?
        - Webinar (60-90 min)
        - Marathon (3-5 days)
        - Workshop (2-4 hours)

User: Webinar

Claude: What language should the presentation be in?
        ...

[Continues through all 8 steps]
```

## File Structure

```
presetation/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   └── presentation.md
├── agents/
│   ├── pres-reviewer.md
│   └── pres-section-builder.md
├── skills/
│   ├── pres-orchestrator/SKILL.md
│   ├── pres-brainstorming/SKILL.md
│   ├── pres-structure/SKILL.md
│   ├── pres-content/SKILL.md
│   ├── pres-cta-emotional/SKILL.md
│   ├── pres-slides/SKILL.md
│   ├── pres-emails/SKILL.md
│   └── pres-qa-review/SKILL.md
├── templates/
│   ├── webinar-structure.md
│   ├── marathon-structure.md
│   ├── workshop-structure.md
│   ├── cta-examples.md
│   └── email-sequences.md
└── docs/
    └── plans/
        └── *.md
```

## License

Private - methodology is proprietary (Hristosenko).

---

*Created with Claude Code*
