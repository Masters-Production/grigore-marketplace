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
7. **Use subagents for complex steps** - Steps 2-7 MUST dispatch subagents

## Subagent Dispatch Pattern

**CRITICAL:** Complex steps (2-7) MUST be executed in separate subagents, NOT in the orchestrator's context.

| Steps | Execution | Reason |
|-------|-----------|--------|
| 0, 1 | Direct | Simple setup and user questions |
| 2-7 | Subagent | Complex work, fresh context needed |

**Why subagents for Steps 2-7:**
- Fresh context for each step
- Orchestrator context not consumed
- Each skill can be complex without limitations

**Dispatch Pattern:**
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute [step-name] step"
  prompt: |
    SKILL TO USE: landing-pages:lp-[skill-name]
    PROJECT FOLDER: [project-folder]

    Input: [list input files]
    Output: [expected artifact path]

    Follow the skill instructions completely.
    When complete, confirm artifact was created.
```

## Required Sub-Skills

| Step | Skill | Execution |
|------|-------|-----------|
| 1 | `landing-pages:lp-brainstorming` | Direct (no subagent) |
| 2 | `landing-pages:lp-design-dna` | **Subagent** |
| 3 | `landing-pages:lp-text-composing` | **Subagent** |
| 4 | `landing-pages:lp-planning` | **Subagent** |
| 5 | `landing-pages:lp-building` | **Subagent** (nested subagents inside) |
| 6 | `landing-pages:lp-qa-review` | **Subagent** |
| 7 | `superpowers:finishing-a-development-branch` | **Subagent** |

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

**Mark TodoWrite as in_progress before starting each step, completed after finishing.**

---

### Steps 0-1: Direct Execution (No Subagent)

**Step 1: Brainstorming** _(Direct execution in orchestrator)_

1. Mark TodoWrite: Step 1 = in_progress
2. Execute skill directly: `landing-pages:lp-brainstorming`
3. Follow skill instructions to gather requirements via AskUserQuestion
4. Create artifact: `[project-folder]/docs/brainstorm-brief.md`
5. Verify: File exists and contains all required sections
6. Mark TodoWrite: Step 1 = completed

---

### Steps 2-7: Subagent Dispatch (Task Tool)

**Step 2: Design DNA** _(Dispatch subagent)_

1. Mark TodoWrite: Step 2 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute design-dna step"
  prompt: |
    ## Landing Page Workflow - Step 2: Design DNA

    SKILL TO USE: landing-pages:lp-design-dna
    PROJECT FOLDER: [project-folder]

    Input: Read [project-folder]/docs/brainstorm-brief.md for context.

    Follow the skill instructions to create the design system.
    Use frontend-design-o skill for distinctive visual design.

    Output: [project-folder]/docs/design-dna.md

    When complete, confirm artifact was created with summary of:
    - Color palette
    - Typography scale
    - Spacing system
    - Component styles
```
3. Verify artifact exists: `[project-folder]/docs/design-dna.md`
4. Mark TodoWrite: Step 2 = completed

---

**Step 3: Text Composing** _(Dispatch subagent)_

1. Mark TodoWrite: Step 3 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute text-composing step"
  prompt: |
    ## Landing Page Workflow - Step 3: Text Composing

    SKILL TO USE: landing-pages:lp-text-composing
    PROJECT FOLDER: [project-folder]

    Input: Read [project-folder]/docs/brainstorm-brief.md for context.

    Follow the skill instructions to write conversion-optimized copy.
    Use copywriting frameworks (4U, PAS, AIDA).

    Output: [project-folder]/docs/copy-sections.md

    When complete, confirm artifact was created with summary of sections.
```
3. Verify artifact exists: `[project-folder]/docs/copy-sections.md`
4. Mark TodoWrite: Step 3 = completed

---

**Step 4: Planning** _(Dispatch subagent)_

1. Mark TodoWrite: Step 4 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute planning step"
  prompt: |
    ## Landing Page Workflow - Step 4: Planning

    SKILL TO USE: landing-pages:lp-planning
    PROJECT FOLDER: [project-folder]

    Input: Read ALL docs in [project-folder]/docs/:
    - brainstorm-brief.md
    - design-dna.md
    - copy-sections.md

    Follow the skill instructions to create implementation plan.
    Break down into bite-sized tasks.

    Output: [project-folder]/docs/implementation-plan.md

    When complete, confirm artifact was created with task count.
```
3. Verify artifact exists: `[project-folder]/docs/implementation-plan.md`
4. Mark TodoWrite: Step 4 = completed

---

**Step 5: Building** _(Dispatch subagent - most complex)_

1. Mark TodoWrite: Step 5 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute building step"
  prompt: |
    ## Landing Page Workflow - Step 5: Building

    SKILL TO USE: landing-pages:lp-building
    PROJECT FOLDER: [project-folder]

    Input: Read ALL docs in [project-folder]/docs/

    This step uses SUBAGENT-DRIVEN DEVELOPMENT:
    - Dispatch fresh subagent for each task from implementation-plan.md
    - Use superpowers:code-reviewer after each task
    - Use frontend-design-o for visual sections

    Output:
    - [project-folder]/index.html
    - [project-folder]/style.css
    - [project-folder]/script.js

    When complete, confirm all three files exist.
```
3. Verify all files exist: `index.html`, `style.css`, `script.js`
4. Mark TodoWrite: Step 5 = completed

---

**Step 6: QA Review** _(Dispatch subagent)_

1. Mark TodoWrite: Step 6 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute QA review step"
  prompt: |
    ## Landing Page Workflow - Step 6: QA Review

    SKILL TO USE: landing-pages:lp-qa-review
    PROJECT FOLDER: [project-folder]

    Input: All files in [project-folder]/

    Follow the skill instructions to perform comprehensive QA.
    Score across 4 categories (100 points total).

    Output: [project-folder]/docs/qa-report.md

    CRITICAL: Report back the final score.
    - Score >= 80: Ready for launch
    - Score < 80: Needs fixes (report critical issues)
```
3. Read QA report and check score
4. If score < 80:
   - Identify critical issues from report
   - Dispatch subagent to fix issues using lp-building
   - Re-run Step 6 (dispatch QA subagent again)
   - Repeat until score >= 80
5. Mark TodoWrite: Step 6 = completed

---

**Step 7: Finish Development** _(Dispatch subagent)_

1. Mark TodoWrite: Step 7 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute finish development step"
  prompt: |
    ## Landing Page Workflow - Step 7: Finish Development

    SKILL TO USE: superpowers:finishing-a-development-branch
    PROJECT FOLDER: [project-folder]

    QA has passed. Complete the development cycle.
    Follow the skill instructions for proper completion.
```
3. Mark TodoWrite: Step 7 = completed

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
