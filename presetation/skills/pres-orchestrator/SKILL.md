---
name: pres-orchestrator
description: Main orchestrator for sales presentation creation - coordinates all skills in sequence from brainstorming to final QA review
---

# Presentation Orchestrator Skill

## Overview

This skill orchestrates the complete sales presentation creation workflow, coordinating all sub-skills in sequence to produce a high-converting presentation for webinars, marathons, or workshops.

## Workflow Steps

```
Step 1: Brainstorming (pres-brainstorming)
    ↓
Step 2: Structure (pres-structure)
    ↓
Step 3: Content (pres-content)
    ↓
Step 4: Emotional Enhancement (pres-cta-emotional)
    ↓
Step 5: Slides (pres-slides)
    ↓
Step 6: Emails (pres-emails)
    ↓
Step 7: QA Review (pres-qa-review)
    ↓
[If score < 80: Fix issues and re-review]
    ↓
Step 8: Delivery
```

## Prerequisites

Before starting, ensure:
1. Templates available in `/templates/` folder
2. User is ready to answer brainstorming questions

## Step-by-Step Process

### Step 1: Project Setup

1. Create project folder:
   ```
   project/{project-name}/
   ```

2. Initialize TodoWrite tracking:
   ```
   - [ ] Complete brainstorming
   - [ ] Generate structure
   - [ ] Write content script
   - [ ] Enhance with emotional triggers
   - [ ] Create slide outlines
   - [ ] Generate email sequences
   - [ ] Pass QA review (score >= 80)
   ```

### Step 2: Brainstorming

**Invoke:** `presentation:pres-brainstorming` skill

**Collect:**
- Event type (webinar/marathon/workshop)
- Language preference
- Product/offer details
- Target audience
- Problem & transformation
- Credibility & Big Idea

**Output:** `project/{project-name}/brainstorming.md`

**Success criteria:**
- All required fields completed
- Clear transformation defined
- Audience profile understood

### Step 3: Structure Generation

**Invoke:** `presentation:pres-structure` skill

**Input:** brainstorming.md

**Process:**
1. Select appropriate template based on event type
2. Customize sections based on product/audience
3. Define timing for each section
4. Identify belief shifts needed

**Output:** `project/{project-name}/structure.md`

**Success criteria:**
- All sections defined with timing
- Belief shifts identified
- Offer structure complete

### Step 4: Content Writing

**Invoke:** `presentation:pres-content` skill

**Input:**
- brainstorming.md
- structure.md

**Process:**
1. Write complete script following Hristosenko methodology
2. Focus on WHY, not HOW (no teaching)
3. Include belief shifts in each content block
4. Create smooth transitions
5. Write offer presentation script

**Output:** `project/{project-name}/script.md`

**Success criteria:**
- Complete script for all sections
- No "how-to" teaching
- Transitions to product natural

### Step 5: Emotional Enhancement

**Invoke:** `presentation:pres-cta-emotional` skill

**Input:** script.md

**Process:**
1. Add emotional triggers throughout
2. Write 15+ unique CTAs
3. Add objection handling scripts
4. Enhance urgency/scarcity elements
5. Include future pacing

**Output:** Updated `script.md` with emotional markers

**Success criteria:**
- 15+ unique CTAs
- All objections pre-handled
- Emotional triggers integrated

### Step 6: Slide Creation

**Invoke:** `presentation:pres-slides` skill

**Input:** script.md, structure.md

**Process:**
1. Create slide outline for each section
2. Recommend visuals
3. Ensure one idea per slide
4. Highlight CTA slides

**Output:** `project/{project-name}/slides.md`

**Success criteria:**
- All sections have slides
- Visuals recommended
- CTA slides prominent

### Step 7: Email Sequences

**Invoke:** `presentation:pres-emails` skill

**Input:** brainstorming.md, script.md

**Process:**
1. Create pre-event sequence
2. Create post-event sequence
3. Follow minimal contact principle
4. Include all deadlines

**Output:** `project/{project-name}/emails.md`

**Success criteria:**
- Minimal but complete sequence
- Benefits in every email
- Deadlines clear

### Step 8: QA Review

**Invoke:** `presentation:pres-qa-review` skill

**Input:** All generated files

**Process:**
1. Score against methodology (100 points)
2. Check all requirements
3. Identify issues

**Output:** `project/{project-name}/qa-review.md`

**Decision:**
- If score >= 80: APPROVED → Proceed to delivery
- If score < 80: Fix issues → Re-run QA

### Step 9: Delivery

When QA passes:

1. Create delivery summary:
   ```markdown
   # [PROJECT NAME] - Delivery Package

   ## Files Included
   - brainstorming.md - Project brief
   - structure.md - Presentation structure
   - script.md - Complete script with emotional triggers
   - slides.md - Slide outlines
   - emails.md - Email sequences
   - qa-review.md - Quality score: [X]/100

   ## Quick Start
   1. Review script.md for the complete presentation
   2. Use slides.md to create your visual presentation
   3. Set up emails.md in your email system
   4. Review qa-review.md for any final tweaks

   ## Event Details
   - Type: [Webinar/Marathon/Workshop]
   - Duration: [X minutes/days]
   - Language: [Selected]
   ```

2. Congratulate user and offer next steps

## Subagent Dispatch Pattern

For complex steps, use the `pres-section-builder` agent:

```
Task tool with subagent_type="presentation:pres-section-builder"
```

Example:
```
prompt: "Build the opening section for this webinar presentation.
        Use the brainstorming data from: project/my-project/brainstorming.md
        Follow the structure from: project/my-project/structure.md
        Save to: project/my-project/sections/opening.md"
```

## Error Handling

### If brainstorming incomplete:
- Return to brainstorming step
- Ask specific missing questions

### If QA fails:
1. List all critical issues
2. Fix highest-priority items first
3. Re-run only affected steps
4. Re-run QA

### If user wants changes:
- Identify which step to modify
- Re-run from that step forward
- Re-run QA

## TodoWrite Integration

Throughout the process, maintain TodoWrite:

```javascript
{
  todos: [
    { content: "Complete brainstorming", status: "completed" },
    { content: "Generate structure", status: "completed" },
    { content: "Write content script", status: "in_progress" },
    { content: "Enhance with emotional triggers", status: "pending" },
    { content: "Create slide outlines", status: "pending" },
    { content: "Generate email sequences", status: "pending" },
    { content: "Pass QA review (>= 80)", status: "pending" }
  ]
}
```

## Success Metrics

A successful presentation project:
- QA score >= 80
- All deliverables complete
- Follows Hristosenko methodology
- Ready for immediate use

## Invocation

To start a new presentation project:

```
/presentation
```

or

```
Use the presentation:pres-orchestrator skill
```
