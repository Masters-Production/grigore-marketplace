# Grigore Marketing Marketplace

A Claude Code plugin marketplace for marketing and automation workflows.

## Installation

### Step 1: Add the Marketplace

In Claude Code, register the marketplace:

```
/plugin marketplace add Masters-Production/grigore-marketplace
```

### Step 2: Install Plugins

Install plugins from this marketplace:

```
/plugin install landing-pages@grigore-marketplace
```

## Updating

Updates are **not automatic** by default. After changes are pushed to GitHub:

**Update marketplace listings:**
```
/plugin marketplace update grigore-marketplace
```

**Update installed plugins:**
```
/plugin update landing-pages@grigore-marketplace
```

**Enable auto-update (optional):**
- Run `/plugin` → "Marketplaces" tab → toggle "Enable auto-update"
- Or set environment variable: `FORCE_AUTOUPDATE_PLUGINS=true`

## Available Plugins

### landing-pages

Professional landing page creation workflow with 7 automated steps:

0. **Project Setup** - Create dedicated folder (user specifies name)
1. **Brainstorming** - Gather requirements through guided questions
2. **Design DNA** - Create a complete design system
3. **Text Composing** - Write conversion-optimized copy
4. **Planning** - Break down into implementation tasks
5. **Building** - Implement with subagent-driven development
6. **QA Review** - Quality assurance with scoring (minimum 80 points)

**Usage:**
```
/landing
```

**Output:**
```
[project-name]/
├── index.html
├── style.css
├── script.js
└── docs/
    ├── brainstorm-brief.md
    ├── design-dna.md
    ├── copy-sections.md
    ├── implementation-plan.md
    └── qa-report.md
```

See [landing-pages/README.md](landing-pages/README.md) for full documentation.

### presetation

Professional sales presentation creation for webinars, marathons, and workshops. Uses embedded **Hristosenko methodology** for high-converting presentations.

**Usage:**
```
/presentation
```

**Workflow (8 Steps):**
1. **Brainstorming** - Gather requirements (event type, audience, product)
2. **Structure** - Generate presentation structure with timing
3. **Content** - Write script (WHY, not HOW methodology)
4. **CTA & Emotional** - Add 15+ CTAs, emotional triggers
5. **Slides** - Create slide outlines
6. **Emails** - Generate pre/post event email sequences
7. **QA Review** - Score against methodology (pass: 80+)
8. **Delivery** - Final package ready

**Event Types:**
| Type | Duration | Conversion |
|------|----------|------------|
| Webinar | 60-90 min | 5-15% |
| Marathon | 3-5 days | 8-20% |
| Workshop | 2-4 hours | 10-25% |

**Output:**
```
project/{project-name}/
├── brainstorming.md
├── structure.md
├── script.md
├── slides.md
├── emails.md
└── qa-review.md
```

**Embedded Methodology:**
- Ladder of Conviction (5 steps to sale)
- Content-Sales Paradox (WHY, not HOW)
- 15+ Unique CTAs with 5 emotional hook types
- 3-Tier Tariff Structure
- Dark Future Technique
- Minimal Contact Principle for emails
- Value Formula: (Result × Probability) / (Time × Effort)

See [presetation/README.md](presetation/README.md) for full documentation.

## Adding New Plugins

To add a new plugin to this marketplace:

1. Create a folder with your plugin at the root level
2. Add `.claude-plugin/plugin.json` inside your plugin folder
3. Add your plugin entry to `.claude-plugin/marketplace.json`

### Plugin Structure

```
your-plugin/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   └── your-command.md
├── agents/
│   └── your-agent.md
└── skills/
    └── your-skill/
        └── SKILL.md
```

### marketplace.json Entry

```json
{
  "name": "your-plugin",
  "description": "What your plugin does",
  "version": "1.0.0",
  "author": {
    "name": "Your Name",
    "email": "your@email.com"
  },
  "source": "./your-plugin",
  "category": "development",
  "tags": ["tag1", "tag2"]
}
```

## License

MIT
