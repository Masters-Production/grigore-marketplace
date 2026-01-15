# Presentation Plugin - Design Document

**Date:** 2026-01-15
**Status:** Implemented
**Author:** Grigore + Claude

---

## 1. Vision

Create a Claude plugin that generates high-converting sales presentations for online courses, following the Mikhail Hristosenko webinar methodology. The plugin should:

- Support 3 event types: Webinar, Marathon, Workshop
- Be multilingual (configurable per project)
- Keep methodology **private** (embedded in skills, not in separate knowledge files)
- Produce complete deliverables: script, slides, emails, QA checklist

---

## 2. Problem Statement

Creating effective sales presentations for webinars/marathons requires:
- Deep knowledge of selling psychology
- Specific structures that work (Ladder of Conviction, 15+ CTAs)
- Consistent methodology across all materials
- Hours of manual work per presentation

**Solution:** Automate the entire process with embedded expert methodology.

---

## 3. Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    /presentation command                     │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    pres-orchestrator                         │
│              (Coordinates entire workflow)                   │
└─────────────────────────────────────────────────────────────┘
                              │
        ┌─────────────────────┼─────────────────────┐
        ▼                     ▼                     ▼
┌───────────────┐   ┌───────────────┐   ┌───────────────┐
│ pres-         │   │ pres-         │   │ pres-         │
│ brainstorming │──▶│ structure     │──▶│ content       │
│               │   │               │   │               │
│ [Gather       │   │ [Select       │   │ [Write script │
│  requirements]│   │  template]    │   │  WHY not HOW] │
└───────────────┘   └───────────────┘   └───────────────┘
                              │
        ┌─────────────────────┼─────────────────────┐
        ▼                     ▼                     ▼
┌───────────────┐   ┌───────────────┐   ┌───────────────┐
│ pres-cta-     │   │ pres-         │   │ pres-         │
│ emotional     │──▶│ slides        │──▶│ emails        │
│               │   │               │   │               │
│ [15+ CTAs,    │   │ [Visual       │   │ [Pre/post     │
│  triggers]    │   │  outlines]    │   │  sequences]   │
└───────────────┘   └───────────────┘   └───────────────┘
                              │
                              ▼
                    ┌───────────────┐
                    │ pres-qa-      │
                    │ review        │
                    │               │
                    │ [100-point    │
                    │  scoring]     │
                    │               │
                    │ Pass >= 80    │
                    └───────────────┘
```

---

## 4. Core Methodology (Embedded)

### 4.1 Hristosenko Principles (Private)

The following methodology is embedded directly in skills (not in external files):

| Principle | Where Used |
|-----------|------------|
| Ladder of Conviction (5 steps) | pres-content |
| Content-Sales Paradox | pres-content |
| 15+ Unique CTAs Rule | pres-cta-emotional |
| 4 Value Depths (ИМЕТЬ→ДЕЛАТЬ→ЧУВСТВОВАТЬ→БЫТЬ) | pres-cta-emotional |
| Bridge & Vaccination Techniques | pres-content |
| Marketing vs Methodological Naming | pres-content, pres-slides |
| Minimal Contact Principle | pres-emails |
| 3-Tier Tariff Psychology | pres-structure |

### 4.2 Why Embedded (Not External)

**Decision:** Knowledge embedded in skills, not in `/knowledge/` folder

**Reasons:**
1. Methodology is proprietary (Hristosenko)
2. Plugin can be shared without exposing knowledge
3. Skills are self-contained and portable
4. No dependency on external files

---

## 5. Component Details

### 5.1 Skills (8 total)

| Skill | Purpose | Key Output |
|-------|---------|------------|
| `pres-orchestrator` | Coordinate workflow | Progress tracking |
| `pres-brainstorming` | Gather requirements | `brainstorming.md` |
| `pres-structure` | Generate structure | `structure.md` |
| `pres-content` | Write script | `script.md` |
| `pres-cta-emotional` | Add CTAs & emotions | Updated `script.md` |
| `pres-slides` | Outline slides | `slides.md` |
| `pres-emails` | Email sequences | `emails.md` |
| `pres-qa-review` | Quality validation | `qa-review.md` |

### 5.2 Templates (5 total)

| Template | Event Type | Duration |
|----------|------------|----------|
| `webinar-structure.md` | Webinar | 60-90 min |
| `marathon-structure.md` | Marathon | 3-5 days |
| `workshop-structure.md` | Workshop | 2-4 hours |
| `cta-examples.md` | All | CTA formulas RU/EN |
| `email-sequences.md` | All | Pre/post templates |

### 5.3 Agents (2 total)

| Agent | Purpose |
|-------|---------|
| `pres-reviewer` | QA review with 100-point scoring |
| `pres-section-builder` | Build individual sections in parallel |

---

## 6. Data Flow

```
User Input (via AskUserQuestion)
        │
        ▼
┌───────────────────────┐
│   brainstorming.md    │ ← Event type, product, audience, transformation
└───────────────────────┘
        │
        ▼
┌───────────────────────┐
│    structure.md       │ ← Sections, timing, belief shifts
└───────────────────────┘
        │
        ▼
┌───────────────────────┐
│     script.md         │ ← Full presentation script with CTAs
└───────────────────────┘
        │
        ├──────────────────┐
        ▼                  ▼
┌───────────────┐  ┌───────────────┐
│  slides.md    │  │  emails.md    │
└───────────────┘  └───────────────┘
        │                  │
        └──────────────────┘
                  │
                  ▼
        ┌───────────────┐
        │ qa-review.md  │ ← Score, issues, verdict
        └───────────────┘
```

---

## 7. QA Scoring System

**Total: 100 points | Pass: >= 80**

| Category | Points | Key Checks |
|----------|--------|------------|
| Structure & Flow | 20 | Hook, problem, content blocks, offer |
| Content Methodology | 25 | Ladder of conviction, WHY not HOW |
| Emotional Triggers | 20 | Pain/desire amplification, FOMO, social proof |
| CTAs & Conversion | 20 | 15+ CTAs, objection handling |
| Supporting Materials | 15 | Slides, emails, cohesion |

---

## 8. Project Output Structure

```
project/{project-name}/
├── brainstorming.md    # Requirements & context
├── structure.md        # Presentation structure
├── script.md           # Full script with CTAs
├── slides.md           # Slide outlines
├── emails.md           # Email sequences
└── qa-review.md        # Quality score & issues
```

---

## 9. Success Criteria

A successful presentation project must:

- [ ] QA score >= 80
- [ ] All 6 deliverable files complete
- [ ] No "how-to" teaching in content (only WHY)
- [ ] 15+ unique CTAs with different triggers
- [ ] Objections pre-handled (time, money, tried before, need to think)
- [ ] Email sequence follows minimal contact principle
- [ ] Ready for immediate use

---

## 10. Future Considerations

**Not in current scope (YAGNI):**

- Automatic slide generation (only outlines)
- Video script timing markers
- A/B testing variations
- Integration with presentation software
- Automatic translation

**May add later:**
- More event types (masterclass, challenge)
- Industry-specific templates
- Case study library

---

## 11. File Structure

```
presetation/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   └── presentation.md
├── agents/
│   ├── pres-reviewer.md
│   └── pres-section-builder.md
├── skills/
│   ├── pres-orchestrator/SKILL.md
│   ├── pres-brainstorming/SKILL.md
│   ├── pres-structure/SKILL.md
│   ├── pres-content/SKILL.md
│   ├── pres-cta-emotional/SKILL.md
│   ├── pres-slides/SKILL.md
│   ├── pres-emails/SKILL.md
│   └── pres-qa-review/SKILL.md
├── templates/
│   ├── webinar-structure.md
│   ├── marathon-structure.md
│   ├── workshop-structure.md
│   ├── cta-examples.md
│   └── email-sequences.md
├── context/
│   └── [source transcripts - private]
└── docs/
    └── plans/
        └── 2026-01-15-presentation-plugin-design.md
```

---

## 12. Invocation

```
/presentation
```

or

```
Use the presentation:pres-orchestrator skill
```

---

*Document created as part of the brainstorming process before implementation validation.*
