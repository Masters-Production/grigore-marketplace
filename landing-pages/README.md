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

| Step | Skill | Output |
|------|-------|--------|
| 0 | Setup | Create project folder (user specifies name) |
| 1 | lp-brainstorming | brainstorm-brief.md |
| 2 | lp-design-dna | design-dna.md |
| 3 | lp-text-composing | copy-sections.md |
| 4 | lp-planning | implementation-plan.md |
| 5 | lp-image-prompts | image-prompts.json |
| 6 | lp-image-generation | assets/images/*.webp |
| 7 | lp-image-integration | implementation-plan.md (updated with image refs) |
| 8 | lp-building | index.html, style.css, script.js |
| 9 | lp-qa-review | qa-report.md |
| 10 | Finish | Final delivery |

## Output Structure

```
[project-name]/
├── index.html
├── style.css
├── script.js
├── assets/
│   └── images/
│       ├── hero-bg.webp
│       ├── icon-*.webp
│       └── *.webp
└── docs/
    ├── brainstorm-brief.md
    ├── design-dna.md
    ├── copy-sections.md
    ├── implementation-plan.md
    ├── image-prompts.json
    └── qa-report.md
```

## Key Features

- **Organized Structure** - All files in a dedicated project folder
- **Subagent-Driven Development** - Fresh context for each task
- **Code Review After Each Task** - Uses `superpowers:code-reviewer`
- **Anti-Generic Design** - Uses `frontend-design-o` for distinctive visuals
- **AI-Generated Images** - Custom visuals created based on design context
- **Quality Gate** - QA must pass with 80+ score

## Image Generation

The workflow includes AI-powered image generation:

- **Context-Aware** - Images generated based on brainstorm, design DNA, and copy
- **Flexible Generation** - Supports MCP tools, APIs, or browser automation
- **Optimized Output** - All images saved as WebP for fast loading
- **Automatic Integration** - Generated images referenced in implementation plan

### Image Generation Setup

At Step 0 (Project Setup), the plugin automatically checks for image generation configuration.

**Option 1: Automatic Setup (Recommended)**

When you run `/landing`, if no image generation is detected:
1. Choose "Configurează Recraft MCP"
2. Enter your API key (get one at https://recraft.ai/settings/api)
3. Plugin creates `.mcp.json` in your project
4. Restart Claude Code
5. Run `/landing` again - configuration is detected automatically

**Option 2: Manual Configuration**

Create `.mcp.json` in your project root:

```json
{
  "mcpServers": {
    "recraft": {
      "command": "npx",
      "args": ["-y", "@recraft-ai/mcp-recraft-server@latest"],
      "env": {
        "RECRAFT_API_KEY": "your-api-key"
      }
    }
  }
}
```

Then restart Claude Code for the MCP server to activate.

**Option 3: Environment Variable**

```bash
export RECRAFT_API_TOKEN=your-api-key
```

The skill will use Bash + curl to make API calls directly.

**No Configuration Required**

The plugin works without any image generation setup. It falls back to:
1. Browser automation (if claude-in-chrome available)
2. Placeholder images (last resort)

You can replace placeholder images manually after generation.

## Plugin Contents

### Skills

| Skill | Purpose |
|-------|---------|
| lp-orchestrator | Main workflow coordinator |
| lp-brainstorming | Requirements gathering |
| lp-design-dna | Design system creation |
| lp-text-composing | Copywriting with frameworks |
| lp-planning | Implementation task breakdown |
| lp-image-prompts | Creates JSON with image generation prompts |
| lp-image-generation | Generates images using configured model (MCP/API/Browser) |
| lp-image-integration | Integrates generated images into implementation plan |
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
