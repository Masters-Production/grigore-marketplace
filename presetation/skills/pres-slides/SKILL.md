---
name: pres-slides
description: Step 5 of presentation creation - generate slide outlines and visual recommendations based on the script
---

# Presentation Slides Skill

## Overview

This skill creates slide outlines with visual recommendations for each section of the presentation script.

## Input Required

- `script.md` - Complete presentation script
- `brainstorming.md` - Brand/visual preferences
- `structure.md` - Section breakdown

## Slide Design Principles

### Visual Hierarchy
1. **One idea per slide**
2. **Minimal text** - Max 6 words per point
3. **High contrast** - Easy to read
4. **Consistent branding** - Colors, fonts

### Slide Types

#### Type 1: Title Slide
- Event name
- Speaker name
- Date/time
- Simple, clean

#### Type 2: Text Slide
- Headline (max 6 words)
- 3-4 bullet points max
- Large font (30pt+)

#### Type 3: Image + Text
- Full-width image
- Overlay text
- Emotional impact

#### Type 4: Before/After
- Split screen
- Clear contrast
- Transformation visual

#### Type 5: Statistics
- Large number
- Brief context
- Source (small)

#### Type 6: Quote/Testimonial
- Quote in large text
- Photo of person
- Name and context

#### Type 7: CTA Slide
- Clear button visual
- Price if applicable
- Urgency text

## Slide Outline Format

For each section, generate:

```markdown
## SECTION: [Name]

### Slide [X]: [Title]
**Type:** [Slide type]
**Headline:** [6 words max]
**Content:**
- Point 1
- Point 2
- Point 3

**Visual:** [Image/graphic recommendation]
**Speaker Notes:** [Key talking points from script]
**Duration:** [Estimated time on this slide]

---
```

## Section-Specific Guidelines

### Opening Slides (3-5 slides)

**Slide 1: Welcome**
- Event title
- Your name/logo
- "Welcome" energy

**Slide 2: Hook**
- Provocative statement
- Large, bold text
- No distractions

**Slide 3: Promise**
- What they'll learn
- Bullet format
- Excitement

**Slide 4: About You (Optional)**
- Brief credentials
- Results achieved
- Photo (authentic)

**Slide 5: Roadmap**
- 3 main topics
- Visual icons
- Timeline feeling

### Problem Section (4-6 slides)

**Slide: Pain Point**
- Emotional headline
- Image showing struggle
- Dark/serious tone

**Slide: Statistics**
- Shocking number
- Context
- Source

**Slide: Mistakes**
- List of 3 mistakes
- Icons for each
- "Don't do this" visual

**Slide: Hope**
- Transition visual
- Light at end of tunnel
- "There's a solution"

### Content Blocks (3-4 slides each)

**Slide: Topic Introduction**
- Big headline
- Icon/visual
- "The [X] Factor"

**Slide: Key Insight**
- Quote or statement
- Minimal text
- Impact visual

**Slide: Example/Story**
- Before/after
- Case study image
- Results highlighted

**Slide: Bridge to Product**
- Subtle transition
- "Part of my system"
- Teaser feeling

### Offer Section (8-12 slides)

**Slide: Transition**
- "Now for something special"
- Energy shift
- Anticipation

**Slide: Product Reveal**
- Product name
- Big, bold
- Logo/brand

**Slide: Module Overview**
- Visual of all modules
- Grid or list
- Professional design

**Slides: Individual Modules**
- One per module
- Icon + benefit
- Quick flip through

**Slide: Bonuses**
- "BONUS" banner
- Each bonus listed
- Value highlighted

**Slide: Value Stack**
- Total calculation
- Visual stack
- Big number

**Slide: Price Reveal**
- Strikethrough original
- Highlight new price
- "Save X%" badge

**Slide: Guarantee**
- Badge/seal visual
- Duration prominent
- Trust symbols

**Slide: CTA**
- Big button visual
- Arrow pointing
- "Click here" text

### Closing Section (3-5 slides)

**Slide: Urgency**
- Countdown visual
- Deadline prominent
- Red/orange colors

**Slide: Final CTA**
- Button again
- Price reminder
- "Last chance"

**Slide: Thank You**
- Appreciation
- Contact info
- Q&A invitation

## Output Format

Save to: `project/{project-name}/slides.md`

```markdown
# [PRODUCT NAME] Presentation Slides

## Overview
- Total slides: [X]
- Duration: [Y] minutes
- Avg time per slide: [Z] seconds

---

## OPENING SECTION

### Slide 1: Welcome
**Type:** Title
**Headline:** [Event Name]
**Content:**
- Speaker name
- Date
**Visual:** Professional background image
**Duration:** 30 sec

...

[Continue for all slides]
```

## Visual Asset Recommendations

For each presentation, recommend:
- Color palette (primary, secondary, accent)
- Font pairing (headline, body)
- Image style (photos, illustrations, icons)
- Mood/tone (professional, energetic, calm)

## Quality Checklist

- [ ] One idea per slide
- [ ] Max 6 words per headline
- [ ] Visual for every concept
- [ ] CTAs have prominent slides
- [ ] Price reveal is dramatic
- [ ] Testimonials have photos
- [ ] Consistent design throughout

## Next Step

After slides are outlined, proceed to `pres-emails` skill to create supporting email sequences.
