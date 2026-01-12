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

0. **Project Setup** - Create dedicated folder for the landing page (user specifies name)
1. **Brainstorming** - Define goals, audience, and value proposition
2. **Design DNA** - Create a complete design system using frontend-design-o skill
3. **Text Composing** - Write conversion-optimized copy using proven frameworks
4. **Planning** - Generate detailed implementation plan
5. **Building** - Implement with subagent-driven development (fresh subagent per task, code review after each)
6. **QA Review** - Verify quality before delivery (minimum score: 80)

## Output

Creates a dedicated project folder with all landing page files:

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

---

**REQUIRED SKILL:** Use `landing-pages:lp-orchestrator` to execute this command.
