---
name: pres-qa-review
description: Step 7 of presentation creation - comprehensive quality review with scoring system to validate methodology compliance
---

# Presentation QA Review Skill

## Overview

This skill performs comprehensive quality review of the generated presentation, scoring against Hristosenko methodology standards.

## Input Required

- `brainstorming.md` - Original requirements
- `structure.md` - Presentation structure
- `script.md` - Complete script
- `slides.md` - Slide outlines
- `emails.md` - Email sequences

## Scoring System

**Total: 100 points**
- Structure & Flow: 20 points
- Content Methodology: 25 points
- Emotional Triggers: 20 points
- CTAs & Conversion: 20 points
- Supporting Materials: 15 points

**Pass threshold: 80 points**

## Review Checklist

### 1. Structure & Flow (20 points)

**Opening (5 points)**
- [ ] Hook grabs attention immediately (1pt)
- [ ] Big promise clearly stated (1pt)
- [ ] Credibility established briefly (1pt)
- [ ] Roadmap sets expectations (1pt)
- [ ] Timing appropriate (1pt)

**Problem Section (5 points)**
- [ ] Pain clearly identified (1pt)
- [ ] Consequences amplified (1pt)
- [ ] Common mistakes addressed (1pt)
- [ ] Hope bridge created (1pt)
- [ ] Emotional impact strong (1pt)

**Content Blocks (5 points)**
- [ ] 3 distinct blocks present (1pt)
- [ ] Each has belief shift (2pt)
- [ ] Bridges to product natural (1pt)
- [ ] No "how-to" teaching (1pt)

**Offer & Close (5 points)**
- [ ] Transition smooth (1pt)
- [ ] Value stacked properly (1pt)
- [ ] Price anchored (1pt)
- [ ] Guarantee included (1pt)
- [ ] Urgency/scarcity present (1pt)

### 2. Content Methodology (25 points)

**Ladder of Conviction (10 points)**
- [ ] Symptoms connected to problem (2pt)
- [ ] Problem elevated to priority (2pt)
- [ ] Method shown as best (2pt)
- [ ] Product implements method (2pt)
- [ ] Offer options clear (2pt)

**Content That Sells (10 points)**
- [ ] Focus on WHY, not HOW (3pt)
- [ ] Significance over details (2pt)
- [ ] Conclusions made FOR them (2pt)
- [ ] Insights provided (2pt)
- [ ] No free education (1pt)

**Belief Shifts (5 points)**
- [ ] Old belief identified (1pt)
- [ ] New belief articulated (1pt)
- [ ] Bridge created (1pt)
- [ ] Each content block has one (2pt)

### 3. Emotional Triggers (20 points)

**Pain Amplification (5 points)**
- [ ] Current pain named (1pt)
- [ ] Future consequences shown (2pt)
- [ ] Emotional cost highlighted (2pt)

**Desire Amplification (5 points)**
- [ ] Future pacing used (2pt)
- [ ] Sensory details included (1pt)
- [ ] Identity shift addressed (2pt)

**FOMO Elements (5 points)**
- [ ] Time urgency present (2pt)
- [ ] Scarcity believable (2pt)
- [ ] Exclusive access mentioned (1pt)

**Social Proof (5 points)**
- [ ] Results mentioned (2pt)
- [ ] Testimonials included (2pt)
- [ ] Similar people referenced (1pt)

### 4. CTAs & Conversion (20 points)

**CTA Quantity (5 points)**
- [ ] 15+ unique CTAs (3pt)
- [ ] Different hooks each time (2pt)

**CTA Quality (10 points)**
- [ ] Benefit CTAs present (2pt)
- [ ] Urgency CTAs present (2pt)
- [ ] Identity CTAs present (2pt)
- [ ] Fear CTAs present (2pt)
- [ ] Social CTAs present (2pt)

**Objection Handling (5 points)**
- [ ] "No time" addressed (1pt)
- [ ] "Tried before" addressed (1pt)
- [ ] "Too expensive" addressed (1pt)
- [ ] "Need to think" addressed (1pt)
- [ ] Pre-emptive, not reactive (1pt)

### 5. Supporting Materials (15 points)

**Slides (5 points)**
- [ ] One idea per slide (1pt)
- [ ] Minimal text (1pt)
- [ ] Visuals recommended (1pt)
- [ ] CTA slides prominent (1pt)
- [ ] Consistent design (1pt)

**Emails (5 points)**
- [ ] Minimal sequence (1pt)
- [ ] Benefits in every email (1pt)
- [ ] Links prominent (1pt)
- [ ] Deadlines mentioned (1pt)
- [ ] P.S. in every email (1pt)

**Overall Cohesion (5 points)**
- [ ] Message consistent (2pt)
- [ ] Brand voice unified (1pt)
- [ ] All pieces aligned (2pt)

## Review Report Format

```markdown
# QA Review Report - [PROJECT NAME]

## Overall Score: [X]/100

### Verdict: [PASS/FAIL]

---

## Section Scores

| Section | Score | Max | Status |
|---------|-------|-----|--------|
| Structure & Flow | [X] | 20 | ✅/⚠️/❌ |
| Content Methodology | [X] | 25 | ✅/⚠️/❌ |
| Emotional Triggers | [X] | 20 | ✅/⚠️/❌ |
| CTAs & Conversion | [X] | 20 | ✅/⚠️/❌ |
| Supporting Materials | [X] | 15 | ✅/⚠️/❌ |

---

## Detailed Findings

### Strengths
- [Strength 1]
- [Strength 2]
- [Strength 3]

### Issues Found

#### Critical (Must Fix)
1. [Issue description]
   - Location: [file:section]
   - Fix: [Recommendation]

2. [Issue description]
   - Location: [file:section]
   - Fix: [Recommendation]

#### Warnings (Should Fix)
1. [Issue description]
   - Fix: [Recommendation]

#### Suggestions (Nice to Have)
1. [Suggestion]

---

## Methodology Compliance

### Hristosenko Principles Checked:
- [ ] Content serves sales (not education)
- [ ] Ladder of conviction followed
- [ ] 15+ unique CTAs
- [ ] Objections pre-handled
- [ ] Minimal email contacts
- [ ] Focus on benefits for cold traffic

---

## Action Items

If score < 80:
1. [Priority fix 1]
2. [Priority fix 2]
3. [Re-run QA after fixes]

If score >= 80:
✅ Ready for delivery
```

## Automated Checks

The skill automatically checks for:

1. **CTA Count** - Must have 15+ unique CTAs
2. **Belief Shifts** - Each content block needs one
3. **No Teaching** - Flag any "how-to" content
4. **Email Count** - Warn if too many pre-event emails
5. **Objection Scripts** - All 4 main objections addressed

## Output

Save to: `project/{project-name}/qa-review.md`

## Iteration Process

If score < 80:
1. List all critical issues
2. Recommend specific fixes
3. Reference knowledge files for corrections
4. Re-run QA after fixes

If score >= 80:
1. Mark as APPROVED
2. List any optional improvements
3. Ready for delivery

## Quality Standards

**Minimum requirements for PASS:**
- Structure complete (all sections present)
- Methodology followed (no teaching in content)
- 15+ unique CTAs
- Objections pre-handled
- Email sequence complete
- Slides outlined

**Excellence indicators (90+):**
- All belief shifts articulated
- Future pacing vivid
- Social proof strong
- CTAs varied and creative
- Materials cohesive
