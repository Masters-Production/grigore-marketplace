# Landing Pages Plugin

Professional landing page creation workflow with brainstorming, design system, copywriting, and automated building.

## Installation

### Step 1: Add the marketplace

**From GitHub:**
```
/plugin marketplace add Masters-Production/grigore-marketplace
```

**From local path:**
```
/plugin marketplace add /path/to/grigore-marketplace
```

### Step 2: Install the plugin

```
/plugin install landing-pages@grigore-marketplace
```

**Installation scopes:**
- Default (user): Available across all projects
- `--scope project`: Shared with team via `.claude/settings.json`
- `--scope local`: Project-specific, gitignored

## Updating

**Update marketplace listings:**
```
/plugin marketplace update grigore-marketplace
```

**Update the plugin:**
```
/plugin update landing-pages@grigore-marketplace
```

## Management Commands

| Command | Purpose |
|---------|---------|
| `/plugin marketplace list` | View all marketplaces |
| `/plugin` | Interactive plugin management UI |
| `/plugin disable landing-pages@grigore-marketplace` | Disable without uninstalling |
| `/plugin uninstall landing-pages@grigore-marketplace` | Remove plugin |

## Usage

```
/landing
```

This launches an interactive workflow that creates a complete, production-ready landing page.

## Workflow Steps

| Step | Skill | Description |
|------|-------|-------------|
| 0 | Setup | Create project folder (user specifies name) |
| 1 | lp-brainstorming | Define goals, audience, value proposition |
| 2 | lp-design-dna | Create design system using `frontend-design-o` |
| 3 | lp-text-composing | Write copy using 4U, PAS, AIDA frameworks |
| 4 | lp-planning | Generate implementation plan with bite-sized tasks |
| 5 | lp-building | Build with subagent-driven development |
| 6 | lp-qa-review | Verify quality (minimum score: 80) |

## Output Structure

```
[project-name]/
├── index.html           # Landing page markup
├── style.css            # Styling following design-dna
├── script.js            # Interactions and animations
└── docs/
    ├── brainstorm-brief.md
    ├── design-dna.md
    ├── copy-sections.md
    ├── implementation-plan.md
    └── qa-report.md
```

## Key Features

- **Organized Structure** - All files in a dedicated project folder
- **Subagent-Driven Development** - Fresh context for each task
- **Code Review After Each Task** - Uses `superpowers:code-reviewer`
- **Anti-Generic Design** - Uses `frontend-design-o` for distinctive visuals
- **Quality Gate** - QA must pass with 80+ score

## Plugin Contents

### Skills

| Skill | Purpose |
|-------|---------|
| lp-orchestrator | Main workflow coordinator |
| lp-brainstorming | Requirements gathering |
| lp-design-dna | Design system creation |
| lp-text-composing | Copywriting with frameworks |
| lp-planning | Implementation task breakdown |
| lp-building | Subagent-driven implementation |
| lp-qa-review | Quality assurance scoring |

### Agents

| Agent | Purpose |
|-------|---------|
| lp-section-builder | Implements individual sections |
| lp-reviewer | Reviews implementations against specs |

### Templates

| Template | Purpose |
|----------|---------|
| design-dna-template.md | Design system structure |
| copy-sections-template.md | Copy document structure |
| qa-checklist.md | QA scoring criteria |

## Dependencies

This plugin uses skills from `superpowers`:

- `superpowers:subagent-driven-development` - Development pattern
- `superpowers:code-reviewer` - Code review after each task
- `superpowers:finishing-a-development-branch` - Completion workflow

And the `frontend-design-o` skill for distinctive visual design.

## Copywriting Frameworks

The text composing step uses proven frameworks:

- **4U** - Headlines: Urgent, Unique, Useful, Ultra-specific
- **PAS** - Problem sections: Problem, Agitate, Solution
- **AIDA** - Page flow: Attention, Interest, Desire, Action
- **FAB** - Benefits: Feature, Advantage, Benefit

## QA Scoring

Landing pages are scored across 4 categories (100 points total):

| Category | Points |
|----------|--------|
| Responsive | 25 |
| Accessibility | 25 |
| Performance | 25 |
| SEO Basics | 25 |

**Passing score: 80+**

## Author

Grigore Lipcanu
contact@grigorelipcanu.com
