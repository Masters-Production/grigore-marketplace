---
name: lp-building
description: Step 5 of landing page creation - implement the landing page using subagent-driven development with MANDATORY frontend-design-o skill for visual sections
---

# Landing Page Building

You are implementing the landing page by executing the implementation plan. Use subagents to build each section and reviewers to verify quality.

## Required Sub-Skills

- `superpowers:subagent-driven-development` - REQUIRED: The base pattern for this workflow
- `frontend-design-o` - REQUIRED: For ALL visual sections
- `superpowers:code-reviewer` - REQUIRED: Review after EACH task
- `superpowers:finishing-a-development-branch` - REQUIRED: At completion

## CRITICAL RULES

1. **Read all artifacts first** - Plan, design-dna, copy-sections from `[project-folder]/docs/`
2. **Create TodoWrite first** - ALL tasks from implementation-plan.md
3. **One task per subagent** - Fresh context for each task
4. **Review after each task** - Use `superpowers:code-reviewer`
5. **Follow design-dna exactly** - No improvisation
6. **Commit after each task** - Atomic commits
7. **MANDATORY: Use frontend-design-o for visual sections** - Hero, cards, features

## BEFORE STARTING: Create TodoWrite

**This is MANDATORY. Do not skip.**

```
1. Read [project-folder]/docs/implementation-plan.md
2. Create TodoWrite with ALL tasks from the plan
3. Mark first task as in_progress
4. Proceed with building
```

Example TodoWrite:
```
todos:
- Task 1: Setup - in_progress
- Task 2: CSS Foundation - pending
- Task 3: Navigation - pending
- Task 4: Hero Section - pending
- Task 5: Problem Section - pending
...
```

## MANDATORY frontend-design-o USAGE

**This is NOT optional. Visual sections MUST use the frontend-design-o skill.**

### Visual Sections (REQUIRE frontend-design-o):
- Hero section
- Benefits/features cards
- Testimonials section
- Pricing cards
- Final CTA section
- Any section with visual complexity

### How to Use:

For each visual section, dispatch the builder with frontend-design-o:

```
Use Skill tool:
skill: "frontend-design-o"
args: "Implement the [SECTION NAME] section for this landing page.

DESIGN DNA:
[Include relevant design-dna.md content]

COPY:
[Include relevant copy-sections.md content]

REQUIREMENTS:
1. Create DISTINCTIVE, professional design
2. Avoid generic AI aesthetics
3. Follow design-dna colors/fonts/spacing exactly
4. Use copy text exactly as provided
5. Include all distinctive elements from design-dna
6. NO emoji icons - use specified icon library
7. Mobile-first responsive approach
8. Think like a designer with 10+ years experience

OUTPUT:
- HTML for the section
- CSS for the section
- JS if needed for interactions"
```

## Input Files

Before starting, verify these exist in `[project-folder]/`:
- `[project-folder]/docs/implementation-plan.md` - Task breakdown
- `[project-folder]/docs/design-dna.md` - All styling specifications (created with frontend-design-o)
- `[project-folder]/docs/copy-sections.md` - All text content

## Output Files

All output goes to `[project-folder]/`:
- `[project-folder]/index.html`
- `[project-folder]/style.css`
- `[project-folder]/script.js`

## Building Pattern

For EACH task in the implementation plan:

```
┌─────────────────────────────────────┐
│  1. Read task requirements          │
│     from implementation-plan.md     │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  2. Is this a VISUAL section?       │
│     (hero, cards, features, etc.)   │
└──────────────┬──────────────────────┘
               │
       ┌───────┴───────┐
       │               │
       ▼               ▼
┌──────────────┐ ┌──────────────────────┐
│ YES: Use     │ │ NO: Use standard     │
│ frontend-    │ │ builder subagent     │
│ design-o     │ │                      │
│ skill        │ │                      │
└──────┬───────┘ └──────────┬───────────┘
       │                    │
       └────────┬───────────┘
                │
                ▼
┌─────────────────────────────────────┐
│  3. Builder implements section      │
│     → Writes HTML                   │
│     → Writes CSS                    │
│     → Writes JS (if needed)         │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  4. Dispatch reviewer subagent      │
│     → Check design match            │
│     → Check responsive              │
│     → Check copy accuracy           │
│     → Check NO generic elements     │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  5. If issues found:                │
│     → Fix issues                    │
│     → Re-review                     │
│  Else:                              │
│     → Commit changes                │
│     → Move to next task             │
└─────────────────────────────────────┘
```

## Subagent Dispatch Instructions

### For VISUAL Sections (MANDATORY frontend-design-o)

```
Use Skill tool:
skill: "frontend-design-o"
args: "Build the [SECTION] for landing page.

## Context
[Brief description of the landing page purpose]

## Design DNA
[Full relevant section from design-dna.md]

## Copy Content
[Exact copy from copy-sections.md]

## Files
- index.html (add/modify section)
- style.css (add/modify styles)
- script.js (if interactions needed)

## Quality Requirements
- Distinctive design, not generic
- Follow design-dna exactly
- NO emoji icons
- Proper icon library icons
- Include background shapes/patterns from design-dna
- Include section dividers from design-dna
- Mobile-first responsive"
```

### For Non-Visual Sections (Standard Builder)

Use Task tool with `subagent_type: "general-purpose"`:

```
Prompt:
"""
You are a landing page builder implementing Task [N] from the implementation plan.

## Your Task
[Copy task details from implementation-plan.md]

## Design System Reference
[Include relevant sections from design-dna.md]

## Copy Reference
[Include relevant sections from copy-sections.md]

## Rules
1. Use EXACT colors/fonts/spacing from design-dna.md
2. Copy text EXACTLY from copy-sections.md
3. Write clean, semantic HTML
4. Use CSS custom properties defined in :root
5. Mobile-first responsive approach

## Files to Modify
- index.html
- style.css
- script.js (if needed)

Complete this task and report what you implemented.
"""
```

### Reviewer: Use superpowers:code-reviewer

**REQUIRED: Use `superpowers:code-reviewer` after EACH task.**

```
Use Skill tool:
skill: "superpowers:code-reviewer"
```

The code-reviewer will check:
- [ ] Colors match design-dna hex values (NO framework defaults)
- [ ] Typography matches design-dna sizes and fonts
- [ ] Spacing matches design-dna scale
- [ ] Copy matches copy-sections exactly
- [ ] Responsive: works at 375px, 768px, 1024px+
- [ ] NO emoji icons (must use specified icon library)
- [ ] Background shapes/patterns implemented (if in design-dna)
- [ ] Section dividers implemented (if in design-dna)
- [ ] No accessibility issues (contrast, alt text, semantic HTML)
- [ ] No console errors
- [ ] Design looks DISTINCTIVE, not generic template

**If reviewer finds CRITICAL issues: FIX before proceeding.**
**If reviewer finds non-critical issues: Fix or note for later.**

## Anti-Generic Quality Gate

**Before approving any visual section, verify:**

### BANNED Elements (instant FAIL):
- ❌ Emoji icons (⏱️ 🤖 📊 ✨ etc.)
- ❌ Plain gradient-only backgrounds
- ❌ Framework default colors
- ❌ Generic template layout

### REQUIRED Elements (must be present):
- ✅ Specified icon library icons
- ✅ Custom background shapes/patterns (from design-dna)
- ✅ Distinctive typography treatment
- ✅ Section dividers (from design-dna)
- ✅ At least one unique visual element

## Execution Flow

### Task 1: Setup

```
Action: Create base files if they don't exist
- index.html (HTML5 boilerplate with Google Fonts link)
- style.css (CSS reset + variables from design-dna)
- script.js (empty or DOMContentLoaded wrapper)

Commit: feat(landing): initial project setup
```

### Task 2: CSS Foundation

```
Action: Dispatch builder with Task 2 details
- Must include ALL design-dna variables
- Must include icon library CDN
- Must include Google Fonts
Review: Verify all design-dna variables present
Commit: feat(landing): add design system CSS variables
```

### Task 3-N: Each Section

For each section task, use the decision flow:
- Visual section → frontend-design-o skill
- Non-visual → standard builder

## Progress Tracking

After each task, update progress:

```markdown
## Building Progress

| Task | Status | Skill Used | Commit |
|------|--------|------------|--------|
| 1. Setup | ✅ Complete | standard | abc1234 |
| 2. CSS Foundation | ✅ Complete | standard | def5678 |
| 3. Navigation | ✅ Complete | standard | ghi9012 |
| 4. Hero | 🔄 Building | frontend-design-o | - |
| 5. Problem | ⏳ Pending | frontend-design-o | - |
| ... | | | |
```

## Error Handling

### Build Errors
If builder subagent fails:
1. Read error message
2. Identify root cause
3. Provide clearer context
4. Re-dispatch builder

### Review Failures
If reviewer finds issues:
1. List all issues clearly
2. Prioritize by severity
3. Fix one issue at a time
4. Re-run review

### Generic Design Detected
If reviewer flags generic elements:
1. STOP - do not proceed
2. Re-dispatch frontend-design-o with explicit requirements
3. Request specific distinctive elements
4. Re-review until quality passes

### Blocking Issues
If stuck on a task:
```
Use AskUserQuestion:
Question: "I'm having trouble with [issue]. How would you like to proceed?"
Header: "Build Issue"
Options:
- label: "Skip this section"
  description: "Move on, we'll fix it later"
- label: "Simplify design"
  description: "Use a simpler implementation"
- label: "Let me help"
  description: "I'll provide guidance"
```

## Commit Message Format

```
feat(landing): add hero section with CTA
feat(landing): add benefits grid layout
feat(landing): add testimonial carousel
fix(landing): correct button hover color
style(landing): adjust mobile spacing
```

## Completion

When all tasks are complete:

1. Verify all files exist in `[project-folder]/`:
   - `[project-folder]/index.html`
   - `[project-folder]/style.css`
   - `[project-folder]/script.js`

2. Run final quality check:
   - All sections present
   - No placeholder text remaining
   - No console errors
   - Responsive at all breakpoints
   - **NO generic/template elements**
   - **All distinctive design elements present**

3. Mark all TodoWrite items as completed

4. Report to orchestrator:
   - Step 5 complete
   - Files created in `[project-folder]/`
   - Ready for QA review

## After QA Passes

**REQUIRED: Use `superpowers:finishing-a-development-branch` to complete the development cycle.**

```
Use Skill tool:
skill: "superpowers:finishing-a-development-branch"
```

## Quality Reminders

Before marking any task complete:
- [ ] Code is clean and readable
- [ ] No inline styles (use CSS classes)
- [ ] No console.log statements
- [ ] Semantic HTML elements used
- [ ] CSS follows design-dna exactly
- [ ] Copy matches copy-sections exactly
- [ ] Tested on mobile viewport
- [ ] **NO emoji icons**
- [ ] **NO generic design elements**
- [ ] **Distinctive elements implemented**
