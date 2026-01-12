---
name: landing
description: Create a professional landing page through an automated workflow including brainstorming, design system, copywriting, and implementation
---

# /landing Command

Create a professional landing page with a guided workflow.

## Usage

```
/landing
```

## What it does

This command launches the Landing Page creation workflow which includes:

1. **Brainstorming** - Define goals, audience, and value proposition
2. **Design DNA** - Create a complete design system
3. **Text Composing** - Write conversion-optimized copy
4. **Planning** - Generate implementation plan
5. **Building** - Implement with subagents
6. **QA Review** - Verify quality before delivery

## Output

Creates a complete landing page with:
- `index.html` - Landing page markup
- `style.css` - Styling following design-dna
- `script.js` - Interactions and animations
- `docs/` - All artifacts (brief, design-dna, copy, plan)

---

**REQUIRED SKILL:** Use `landing-pages:lp-orchestrator` to execute this command.
