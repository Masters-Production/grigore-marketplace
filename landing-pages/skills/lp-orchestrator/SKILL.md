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
5. **Use TodoWrite** - Create todos for ALL steps at the beginning
6. **All files in project folder** - Everything goes in `[project-folder]/`

## Required Sub-Skills

- `landing-pages:lp-brainstorming` - Step 1
- `landing-pages:lp-design-dna` - Step 2
- `landing-pages:lp-text-composing` - Step 3
- `landing-pages:lp-planning` - Step 4
- `landing-pages:lp-building` - Step 5 (uses subagent-driven development)
- `landing-pages:lp-qa-review` - Step 6
- `superpowers:finishing-a-development-branch` - Final completion

## Workflow Sequence

```
Step 0: Project Setup → Create [project-folder]/ and [project-folder]/docs/
    ↓
Step 1: lp-brainstorming → [project-folder]/docs/brainstorm-brief.md
    ↓
Step 2: lp-design-dna → [project-folder]/docs/design-dna.md
    ↓
Step 3: lp-text-composing → [project-folder]/docs/copy-sections.md
    ↓
Step 4: lp-planning → [project-folder]/docs/implementation-plan.md
    ↓
Step 5: lp-building → [project-folder]/index.html, style.css, script.js
    ↓
Step 6: lp-qa-review → [project-folder]/docs/qa-report.md (score >= 80)
    ↓
Step 7: finishing-a-development-branch → Complete
```

## Step 0: Project Setup (MANDATORY FIRST STEP)

**1. Ask user for folder name:**
```
Use AskUserQuestion:
Question: "Cum să numesc folderul pentru acest landing page?"
Header: "Folder Name"
Options:
- "product-landing"
- "service-landing"
- "campaign-landing"
(User can also type custom name via "Other")
```

**2. Create project structure:**
```bash
mkdir [project-folder]
mkdir [project-folder]/docs
```

**3. Create TodoWrite with ALL steps:**
```
TodoWrite todos:
- Step 0: Project Setup - COMPLETED
- Step 1: Brainstorming - pending
- Step 2: Design DNA - pending
- Step 3: Text Composing - pending
- Step 4: Planning - pending
- Step 5: Building - pending
- Step 6: QA Review - pending
- Step 7: Finish Development - pending
```

**4. Confirm structure:**
```
[project-folder]/
└── docs/
```

**All subsequent skills will use `[project-folder]/` as the base path.**

## Execute Skills in Sequence

For each step, invoke the corresponding skill. **Mark TodoWrite as in_progress before starting, completed after finishing.**

**Step 1: Brainstorming**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-brainstorming

Input: None (skill will ask questions)
Output: [project-folder]/docs/brainstorm-brief.md
Verify: File exists and contains all required sections
```

**Step 2: Design DNA**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-design-dna

Input: [project-folder]/docs/brainstorm-brief.md (for context)
Output: [project-folder]/docs/design-dna.md
Verify: File contains color palette, typography, spacing, components
```

**Step 3: Text Composing**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-text-composing

Input: [project-folder]/docs/brainstorm-brief.md
Output: [project-folder]/docs/copy-sections.md
Verify: File contains copy for all planned sections
```

**Step 4: Planning**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-planning

Input: [project-folder]/docs/brainstorm-brief.md, design-dna.md, copy-sections.md
Output: [project-folder]/docs/implementation-plan.md
Verify: File contains task breakdown with steps
```

**Step 5: Building (Subagent-Driven)**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-building

This step uses SUBAGENT-DRIVEN DEVELOPMENT:
- Dispatch fresh subagent for each task from implementation-plan.md
- Use superpowers:code-reviewer after each task
- Use frontend-design-o for visual sections

Input: All [project-folder]/docs/* files
Output: [project-folder]/index.html, [project-folder]/style.css, [project-folder]/script.js
Verify: All three files exist and are valid
```

**Step 6: QA Review**
```
REQUIRED SUB-SKILL: Use landing-pages:lp-qa-review

Input: All [project-folder]/ output files
Output: [project-folder]/docs/qa-report.md
Verify: Score >= 80

If score < 80:
  - Identify critical issues
  - Fix issues using lp-building
  - Re-run QA
  - Repeat until score >= 80
```

**Step 7: Finish Development**
```
REQUIRED SUB-SKILL: Use superpowers:finishing-a-development-branch

After QA passes, complete the development cycle.
```

## Progress Tracking

Use TodoWrite to track progress. After each step, update status:

```markdown
## Landing Page Progress

| Step | Status | Artifact |
|------|--------|----------|
| 0. Project Setup | ✅ Complete | [project-folder]/ created |
| 1. Brainstorming | ✅ Complete | [project-folder]/docs/brainstorm-brief.md |
| 2. Design DNA | ✅ Complete | [project-folder]/docs/design-dna.md |
| 3. Text Composing | 🔄 In Progress | [project-folder]/docs/copy-sections.md |
| 4. Planning | ⏳ Pending | [project-folder]/docs/implementation-plan.md |
| 5. Building | ⏳ Pending | [project-folder]/index.html, style.css, script.js |
| 6. QA Review | ⏳ Pending | [project-folder]/docs/qa-report.md |
| 7. Finish | ⏳ Pending | Complete development |
```

## Completion

When QA passes (score >= 80), run `superpowers:finishing-a-development-branch`, then provide summary:

```markdown
## Landing Page Complete!

**Project:** [project-folder]/
**QA Score:** [X]/100

### Files Created
- `[project-folder]/index.html` - [X] lines
- `[project-folder]/style.css` - [X] lines
- `[project-folder]/script.js` - [X] lines

### Documentation
- `[project-folder]/docs/brainstorm-brief.md`
- `[project-folder]/docs/design-dna.md`
- `[project-folder]/docs/copy-sections.md`
- `[project-folder]/docs/implementation-plan.md`
- `[project-folder]/docs/qa-report.md`

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
