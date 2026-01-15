---
name: pres-structure
description: Step 2 of presentation creation - generate the complete presentation structure based on event type and brainstorming data
---

# Presentation Structure Skill

## Overview

This skill creates the detailed structure for a sales presentation based on the brainstorming document and event type (webinar/marathon/workshop).

## Input Required

- `brainstorming.md` - Output from pres-brainstorming skill
- Event type determines which template to use

## Process

1. Read brainstorming document
2. Select appropriate template (webinar/marathon/workshop)
3. Customize structure based on:
   - Product type and price
   - Audience temperature
   - Transformation promised
   - Big Idea

## Structure Generation

### For Webinar (60-90 min)

Generate structure with these sections:

```markdown
# [PRODUCT NAME] Webinar Structure

## Section 1: Opening (5-10 min)
### Hook
[Generate provocative opening based on main problem]

### Big Promise
[What they'll learn/achieve]

### Credibility Points
[From brainstorming - why listen to you]

### Roadmap
[Preview of 3 main content blocks]

---

## Section 2: Problem Agitation (10-15 min)
### Pain Identification
[Main problem from brainstorming]

### Consequences
[What happens if not solved]

### Common Mistakes
[3 mistakes people make]

### Hope Bridge
[Hint at solution]

---

## Section 3: Content Block 1 (8-12 min)
### Topic: [First Key Concept]
### Belief Shift: [From X to Y]
### Example/Story: [Placeholder]
### Bridge to Product: [Connection point]

---

## Section 4: Content Block 2 (8-12 min)
### Topic: [Second Key Concept]
### Belief Shift: [From X to Y]
### Example/Story: [Placeholder]
### Bridge to Product: [Connection point]

---

## Section 5: Content Block 3 (8-12 min)
### Topic: [Third Key Concept]
### Belief Shift: [From X to Y]
### Example/Story: [Placeholder]
### Bridge to Product: [Connection point]

---

## Section 6: Transition (5 min)
### Summary
[Recap what they learned]

### Gap
[What's still missing]

### Invitation
[Bridge to offer]

---

## Section 7: Offer Presentation (15-20 min)
### Product Introduction
- Name: [From brainstorming]
- Big Promise: [Transformation]

### Modules/Components
[Based on product type]

### Bonuses
- Bonus 1: [Value]
- Bonus 2: [Value]

### Value Stack
[Total value calculation]

### Price Reveal
- Full Price: [X]
- Today's Price: [Y]
- Savings: [Z]

### Guarantee
[Risk reversal]

---

## Section 8: CTA + Close (5-10 min)
### Primary CTA
[Clear action]

### Urgency Elements
[Time-based]

### Scarcity Elements
[Quantity-based]

### Final Push
[Last benefits]

### Q&A Transition
[Handle objections]
```

### For Marathon (3-5 days)

Generate 5-day structure with daily themes:
- Day 1: Foundation + Hook
- Day 2: Deep Dive
- Day 3: Advanced
- Day 4: Case Studies
- Day 5: Offer

### For Workshop (2-4 hours)

Generate intensive structure:
- Phase 1: Opening (15-20 min)
- Phase 2: Teaching (60-90 min)
- Phase 3: Implementation (45-60 min)
- Phase 4: Offer (20-30 min)
- Phase 5: Q&A + Close (15-20 min)

## Output

Save to: `project/{project-name}/structure.md`

## Key Principles (from Hristosenko Methodology)

### Content Must Serve Sales
- "Единственная цель контентной части – это способствовать продаже"
- Every content block must have a belief shift
- Every section must bridge to the product

### Structure Options
1. **Steps** - "5 steps to [result]" - talk about WHY, not HOW
2. **Elements** - Components of success (all needed)
3. **Mistakes** - What NOT to do (automatically avoids teaching)

### Timing Principles
- First 25-30 minutes: Pure value, no selling
- Content blocks: Focus on SIGNIFICANCE, not details
- Offer section: Stack value, reveal price with anchoring

## Success Criteria

- [ ] All sections defined
- [ ] Timing estimates included
- [ ] Belief shifts identified for each content block
- [ ] Offer structure complete
- [ ] CTA sequence planned

## Next Step

After structure is complete, proceed to `pres-content` skill to write the full script.
