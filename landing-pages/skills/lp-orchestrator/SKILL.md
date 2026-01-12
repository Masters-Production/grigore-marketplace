---
name: lp-orchestrator
description: Main orchestrator for landing page creation - coordinates all skills in sequence from brainstorming to final QA review
---

# Landing Page Orchestrator

You are orchestrating the creation of a professional landing page. This is a multi-step workflow that must be executed in sequence.

## CRITICAL RULES

1. **Execute skills in order** - Do not skip steps
2. **Use AskUserQuestion throughout** - Never assume, always ask
3. **Wait for each skill to complete** - Check artifacts exist before proceeding
4. **Quality gates matter** - If QA fails (<80 score), iterate

## Workflow Sequence

```
Step 1: lp-brainstorming → docs/brainstorm-brief.md
    ↓
Step 2: lp-design-dna → docs/design-dna.md
    ↓
Step 3: lp-text-composing → docs/copy-sections.md
    ↓
Step 4: lp-planning → docs/implementation-plan.md
    ↓
Step 5: lp-building → index.html, style.css, script.js
    ↓
Step 6: lp-qa-review → docs/qa-report.md (score >= 80)
```

## Starting the Workflow

### 1. Initial Setup

First, ask the user for a project name:

```
Use AskUserQuestion:
Question: "What should we name this landing page project?"
Header: "Project Name"
Options:
- "Let me type a name" → freeform input
- "Suggest based on my description" → you'll suggest after hearing about it
```

Create the project folder structure:
```
[project-name]/
├── index.html
├── style.css
├── script.js
└── docs/
    ├── brainstorm-brief.md
    ├── design-dna.md
    ├── copy-sections.md
    └── implementation-plan.md
```

### 2. Execute Skills in Sequence

For each step, invoke the corresponding skill:

**Step 1: Brainstorming**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-brainstorming

Input: None (skill will ask questions)
Output: docs/brainstorm-brief.md
Verify: File exists and contains all required sections
```

**Step 2: Design DNA**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-design-dna

Input: docs/brainstorm-brief.md (for context)
Output: docs/design-dna.md
Verify: File contains color palette, typography, spacing, components
```

**Step 3: Text Composing**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-text-composing

Input: docs/brainstorm-brief.md
Output: docs/copy-sections.md
Verify: File contains copy for all planned sections
```

**Step 4: Planning**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-planning

Input: docs/brainstorm-brief.md, docs/design-dna.md, docs/copy-sections.md
Output: docs/implementation-plan.md
Verify: File contains task breakdown with steps
```

**Step 5: Building**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-building

Input: All docs/* files
Output: index.html, style.css, script.js
Verify: All three files exist and are valid
```

**Step 6: QA Review**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-qa-review

Input: All output files
Output: docs/qa-report.md
Verify: Score >= 80

If score < 80:
  - Identify critical issues
  - Fix issues using lp-building
  - Re-run QA
  - Repeat until score >= 80
```

## Progress Tracking

After each step, report progress to user:

```markdown
## Landing Page Progress

| Step | Status | Artifact |
|------|--------|----------|
| 1. Brainstorming | ✅ Complete | brainstorm-brief.md |
| 2. Design DNA | ✅ Complete | design-dna.md |
| 3. Text Composing | 🔄 In Progress | copy-sections.md |
| 4. Planning | ⏳ Pending | implementation-plan.md |
| 5. Building | ⏳ Pending | index.html, style.css, script.js |
| 6. QA Review | ⏳ Pending | qa-report.md |
```

## Completion

When QA passes (score >= 80), provide summary:

```markdown
## Landing Page Complete!

**Project:** [project-name]
**QA Score:** [X]/100

### Files Created
- `index.html` - [X] lines
- `style.css` - [X] lines
- `script.js` - [X] lines

### Documentation
- `docs/brainstorm-brief.md`
- `docs/design-dna.md`
- `docs/copy-sections.md`
- `docs/implementation-plan.md`
- `docs/qa-report.md`

### Next Steps
1. Add real images to replace placeholders
2. Connect form to backend
3. Deploy to hosting

Would you like to make any adjustments before considering this complete?
```

## Error Handling

If any skill fails:
1. Report the specific error to user
2. Ask if they want to retry or provide different input
3. Do not proceed to next step until current step succeeds

## Important Notes

- **Never skip user interaction** - Each skill uses AskUserQuestion
- **Artifacts are source of truth** - Always read docs/ files, don't rely on memory
- **Quality over speed** - Better to iterate than deliver subpar landing page
- **Design-DNA drives implementation** - All styling must follow design-dna.md exactly
