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

## Available Plugins

### landing-pages

Professional landing page creation workflow with 6 automated steps:

1. **Brainstorming** - Gather requirements through guided questions
2. **Design DNA** - Create a complete design system
3. **Text Composing** - Write conversion-optimized copy
4. **Planning** - Break down into implementation tasks
5. **Building** - Implement the landing page
6. **QA Review** - Quality assurance with scoring

**Usage:**
```
/landing
```

**Output:**
- `index.html`, `style.css`, `script.js`
- `docs/` folder with design specs and QA reports

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
