# Presentation Plugin Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create a Claude plugin that generates high-converting sales presentations with Hristosenko methodology embedded directly in skills (private).

**Architecture:** Orchestrator pattern with 8 sequential skills, 2 agents for parallel work, 5 templates. All methodology embedded in skills (no external knowledge files).

**Tech Stack:** Claude plugin system, Markdown files, YAML frontmatter

---

## Phase 1: Plugin Foundation

### Task 1: Create Plugin Structure

**Files:**
- Create: `presetation/.claude-plugin/plugin.json`
- Create: `presetation/commands/presentation.md`

**Step 1: Create plugin.json**

```json
{
  "name": "presentation",
  "description": "Professional sales presentation creation workflow for webinars, marathons, and workshops",
  "version": "1.0.0",
  "commands": "./commands",
  "agents": ["./agents/pres-reviewer.md", "./agents/pres-section-builder.md"],
  "skills": "./skills"
}
```

**Step 2: Create entry command**

```markdown
---
name: presentation
description: Create a professional sales presentation
---

# Presentation Creator

Use the `presentation:pres-orchestrator` skill to start.
```

**Step 3: Commit**

```bash
git add presetation/.claude-plugin presetation/commands
git commit -m "feat(presentation): initialize plugin structure"
```

---

### Task 2: Create Agents

**Files:**
- Create: `presetation/agents/pres-reviewer.md`
- Create: `presetation/agents/pres-section-builder.md`

**Step 1: Create pres-reviewer agent**

Agent with 100-point QA scoring system embedded.

**Step 2: Create pres-section-builder agent**

Agent for building individual sections in parallel.

**Step 3: Commit**

```bash
git add presetation/agents
git commit -m "feat(presentation): add reviewer and section-builder agents"
```

---

## Phase 2: Core Skills (Methodology Embedded)

### Task 3: Create Orchestrator Skill

**Files:**
- Create: `presetation/skills/pres-orchestrator/SKILL.md`

**Step 1: Write orchestrator with 8-step workflow**

```markdown
---
name: pres-orchestrator
description: Main orchestrator for sales presentation creation
---

# Workflow Steps
Step 1: Brainstorming → Step 2: Structure → Step 3: Content →
Step 4: Emotional → Step 5: Slides → Step 6: Emails →
Step 7: QA Review → Step 8: Delivery
```

**Step 2: Commit**

```bash
git add presetation/skills/pres-orchestrator
git commit -m "feat(presentation): add orchestrator skill"
```

---

### Task 4: Create Brainstorming Skill

**Files:**
- Create: `presetation/skills/pres-brainstorming/SKILL.md`

**Step 1: Write skill with AskUserQuestion integration**

Collect: Event type, language, product, audience, transformation, credibility.

**Step 2: Commit**

```bash
git add presetation/skills/pres-brainstorming
git commit -m "feat(presentation): add brainstorming skill"
```

---

### Task 5: Create Structure Skill

**Files:**
- Create: `presetation/skills/pres-structure/SKILL.md`

**Step 1: Write skill with template selection logic**

- Webinar: 60-90 min
- Marathon: 3-5 days
- Workshop: 2-4 hours

**Step 2: Commit**

```bash
git add presetation/skills/pres-structure
git commit -m "feat(presentation): add structure skill"
```

---

### Task 6: Create Content Skill (Methodology Embedded)

**Files:**
- Create: `presetation/skills/pres-content/SKILL.md`

**Step 1: Embed core methodology**

- Ladder of Conviction (5 steps)
- Content-Sales Paradox
- WHY not HOW principle
- Bridge & Vaccination techniques
- Marketing vs Methodological naming

**Step 2: Commit**

```bash
git add presetation/skills/pres-content
git commit -m "feat(presentation): add content skill with embedded methodology"
```

---

### Task 7: Create CTA & Emotional Skill (Methodology Embedded)

**Files:**
- Create: `presetation/skills/pres-cta-emotional/SKILL.md`

**Step 1: Embed emotional selling methodology**

- 15+ CTAs rule
- 4 Value Depths (ИМЕТЬ→ДЕЛАТЬ→ЧУВСТВОВАТЬ→БЫТЬ)
- Pain/desire amplification
- Objection pre-handling
- Urgency/scarcity elements

**Step 2: Commit**

```bash
git add presetation/skills/pres-cta-emotional
git commit -m "feat(presentation): add CTA skill with embedded methodology"
```

---

### Task 8: Create Slides Skill

**Files:**
- Create: `presetation/skills/pres-slides/SKILL.md`

**Step 1: Write slide outline guidelines**

- One idea per slide
- Visual recommendations
- CTA slides prominent

**Step 2: Commit**

```bash
git add presetation/skills/pres-slides
git commit -m "feat(presentation): add slides skill"
```

---

### Task 9: Create Emails Skill (Methodology Embedded)

**Files:**
- Create: `presetation/skills/pres-emails/SKILL.md`

**Step 1: Embed email methodology**

- Minimal contact principle
- Pre-event sequence (4 emails)
- Post-event sequence (2-3 emails)
- Subject line formulas

**Step 2: Commit**

```bash
git add presetation/skills/pres-emails
git commit -m "feat(presentation): add emails skill with embedded methodology"
```

---

### Task 10: Create QA Review Skill

**Files:**
- Create: `presetation/skills/pres-qa-review/SKILL.md`

**Step 1: Write 100-point scoring system**

| Category | Points |
|----------|--------|
| Structure & Flow | 20 |
| Content Methodology | 25 |
| Emotional Triggers | 20 |
| CTAs & Conversion | 20 |
| Supporting Materials | 15 |

Pass threshold: 80 points

**Step 2: Commit**

```bash
git add presetation/skills/pres-qa-review
git commit -m "feat(presentation): add QA review skill with scoring system"
```

---

## Phase 3: Templates

### Task 11: Create Structure Templates

**Files:**
- Create: `presetation/templates/webinar-structure.md`
- Create: `presetation/templates/marathon-structure.md`
- Create: `presetation/templates/workshop-structure.md`

**Step 1: Write templates with timing and sections**

**Step 2: Commit**

```bash
git add presetation/templates/*-structure.md
git commit -m "feat(presentation): add structure templates"
```

---

### Task 12: Create Supporting Templates

**Files:**
- Create: `presetation/templates/cta-examples.md`
- Create: `presetation/templates/email-sequences.md`

**Step 1: Write CTA formulas (RU/EN)**

5 types: Benefit, Urgency, Fear, Identity, Social proof

**Step 2: Write email sequence templates**

**Step 3: Commit**

```bash
git add presetation/templates/cta-examples.md presetation/templates/email-sequences.md
git commit -m "feat(presentation): add CTA and email templates"
```

---

## Phase 4: Documentation

### Task 13: Create Design Document

**Files:**
- Create: `presetation/docs/plans/2026-01-15-presentation-plugin-design.md`

**Step 1: Document architecture, workflow, components**

**Step 2: Commit**

```bash
git add presetation/docs/plans
git commit -m "docs(presentation): add design document"
```

---

### Task 14: Final Verification

**Step 1: Verify all files exist**

```bash
find presetation -type f \( -name "*.md" -o -name "*.json" \) | wc -l
# Expected: 18+ files
```

**Step 2: Verify no knowledge folder**

```bash
ls presetation/knowledge 2>/dev/null || echo "OK: No knowledge folder"
# Expected: "OK: No knowledge folder"
```

**Step 3: Verify no knowledge references in skills**

```bash
grep -r "knowledge/" presetation/skills || echo "OK: No knowledge references"
# Expected: "OK: No knowledge references"
```

**Step 4: Final commit**

```bash
git add .
git commit -m "feat(presentation): complete plugin implementation"
```

---

## Summary

| Phase | Tasks | Status |
|-------|-------|--------|
| 1. Foundation | 1-2 | Plugin structure, agents |
| 2. Skills | 3-10 | 8 skills with embedded methodology |
| 3. Templates | 11-12 | 5 templates |
| 4. Documentation | 13-14 | Design doc, verification |

**Total:** 14 tasks

---

*Plan created following superpowers:writing-plans skill guidelines.*
