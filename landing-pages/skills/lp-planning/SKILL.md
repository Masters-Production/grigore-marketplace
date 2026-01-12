---
name: lp-planning
description: Step 4 of landing page creation - create a detailed implementation plan with bite-sized tasks for building the landing page
---

# Landing Page Planning

You are creating a detailed implementation plan for building the landing page. Break the work into clear, executable tasks that can be delegated to builder subagents.

## CRITICAL RULES

1. **Read all artifacts first** - brainstorm-brief, design-dna, copy-sections
2. **Bite-sized tasks** - Each task should be completable in one focused session
3. **Clear dependencies** - Order tasks logically, note what each needs
4. **Specific instructions** - Include exact files, sections, and references
5. **Output artifact** - Create `[project-folder]/docs/implementation-plan.md` when complete

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
Read and understand:
- `[project-folder]/docs/brainstorm-brief.md` - What sections are planned
- `[project-folder]/docs/design-dna.md` - All styling specifications
- `[project-folder]/docs/copy-sections.md` - All text content

### Output Files
- `[project-folder]/docs/implementation-plan.md` - Task breakdown for building

## Planning Process

### Step 1: Identify Sections

Based on brainstorm-brief, list all sections needed:

```
Typical structure:
1. Navigation/Header
2. Hero Section
3. Problem/Solution Section
4. Benefits Section
5. Social Proof Section
6. FAQ Section (if applicable)
7. Final CTA Section
8. Footer
```

### Step 2: Define Task Breakdown

Each section becomes 1-2 tasks:

**Task Template:**
```markdown
### Task [N]: [Section Name]

**Goal:** [What this task accomplishes]

**Files to modify:**
- `index.html` - Add [specific elements]
- `style.css` - Add [specific styles]
- `script.js` - Add [specific functionality] (if needed)

**Reference:**
- Copy from: `[project-folder]/docs/copy-sections.md` → [Section]
- Styles from: `[project-folder]/docs/design-dna.md` → [Component]

**Steps:**
1. [Specific step 1]
2. [Specific step 2]
3. [Specific step 3]

**Acceptance Criteria:**
- [ ] [Checkable criterion 1]
- [ ] [Checkable criterion 2]
```

### Step 3: Confirm Plan with User

```
Use AskUserQuestion:
Question: "I've created an implementation plan with [X] tasks. Would you like to review it before we start building?"
Header: "Plan Review"
Options:
- label: "Show me the full plan"
  description: "I want to review all tasks"
- label: "Just the summary"
  description: "Show section overview, skip details"
- label: "Looks good, proceed"
  description: "Start building immediately"
```

## Output Artifact

Create `[project-folder]/docs/implementation-plan.md`:

```markdown
# Landing Page Implementation Plan

> Implementation plan for [project name]

## Overview

**Total Tasks:** [X]
**Files to Create:**
- `[project-folder]/index.html` - Page structure and content
- `[project-folder]/style.css` - All styling following design-dna
- `[project-folder]/script.js` - Interactions and animations

**Prerequisites:**
- `[project-folder]/docs/brainstorm-brief.md` ✓
- `[project-folder]/docs/design-dna.md` ✓
- `[project-folder]/docs/copy-sections.md` ✓

---

## Task 1: Project Setup + Base Structure

**Goal:** Create file structure and base HTML/CSS

**Files:**
- Create `[project-folder]/index.html`
- Create `[project-folder]/style.css`
- Create `[project-folder]/script.js`

**Steps:**
1. Create index.html with HTML5 boilerplate
2. Add semantic structure: `<header>`, `<main>`, `<footer>`
3. Add empty `<section>` elements for each planned section
4. Link style.css and script.js
5. Add meta tags (viewport, description, Open Graph)

**Acceptance Criteria:**
- [ ] Valid HTML5 document
- [ ] All sections have semantic containers
- [ ] CSS and JS files linked
- [ ] Meta tags present

---

## Task 2: CSS Foundation + Design System

**Goal:** Implement CSS variables and base styles from design-dna

**Files:**
- `[project-folder]/style.css`

**Reference:**
- `[project-folder]/docs/design-dna.md` → Colors, Typography, Spacing

**Steps:**
1. Add CSS reset (box-sizing, margins)
2. Define CSS custom properties for all colors
3. Define typography custom properties
4. Define spacing custom properties
5. Add base typography styles (body, headings)
6. Add utility classes (.container, .text-center, etc.)

**CSS Variables to include:**
```css
:root {
  /* Colors */
  --color-primary: [from design-dna];
  --color-secondary: [from design-dna];
  /* ... all colors */

  /* Typography */
  --font-heading: [from design-dna];
  --font-body: [from design-dna];
  /* ... all sizes */

  /* Spacing */
  --space-xs: [from design-dna];
  /* ... all spacing */
}
```

**Acceptance Criteria:**
- [ ] All design-dna colors as CSS variables
- [ ] Typography scale implemented
- [ ] Spacing scale implemented
- [ ] Base styles working

---

## Task 3: Navigation/Header

**Goal:** Build responsive navigation

**Files:**
- `[project-folder]/index.html` → `<header>` section
- `[project-folder]/style.css` → Header styles
- `[project-folder]/script.js` → Mobile menu toggle (if needed)

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Navigation items
- `[project-folder]/docs/design-dna.md` → Component styles

**Steps:**
1. Add logo placeholder
2. Add navigation links
3. Add CTA button in header
4. Style for desktop (flexbox, spacing)
5. Add mobile hamburger menu
6. Implement mobile menu toggle

**Acceptance Criteria:**
- [ ] Logo and nav links visible
- [ ] CTA button styled per design-dna
- [ ] Mobile menu functional
- [ ] Sticky header (if specified)

---

## Task 4: Hero Section

**Goal:** Build hero section with headline, subheadline, CTA

**Files:**
- `[project-folder]/index.html` → `<section class="hero">`
- `[project-folder]/style.css` → Hero styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Hero Section
- `[project-folder]/docs/design-dna.md` → Hero Section, Buttons

**Steps:**
1. Add hero HTML structure
2. Insert headline from copy-sections
3. Insert subheadline from copy-sections
4. Add primary CTA button
5. Style hero layout (centered or split)
6. Add background (gradient or image)
7. Ensure min-height per design-dna

**Acceptance Criteria:**
- [ ] Headline matches copy-sections exactly
- [ ] Button styled per design-dna
- [ ] Background/gradient applied
- [ ] Responsive layout

---

## Task 5: Problem/Solution Section

**Goal:** Build problem section with PAS content

**Files:**
- `[project-folder]/index.html` → `<section class="problem">`
- `[project-folder]/style.css` → Problem section styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Problem Section
- `[project-folder]/docs/design-dna.md` → Typography, Spacing

**Steps:**
1. Add section HTML structure
2. Insert problem paragraph
3. Insert agitation paragraph
4. Insert solution paragraph
5. Style typography and spacing
6. Add visual separator or background change

**Acceptance Criteria:**
- [ ] All PAS content present
- [ ] Clear visual hierarchy
- [ ] Proper spacing between paragraphs
- [ ] Section stands out from hero

---

## Task 6: Benefits Section

**Goal:** Build benefits grid/list

**Files:**
- `[project-folder]/index.html` → `<section class="benefits">`
- `[project-folder]/style.css` → Benefits styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Benefits Section
- `[project-folder]/docs/design-dna.md` → Cards, Typography

**Steps:**
1. Add section headline
2. Create benefits grid (3-column desktop)
3. Add benefit cards with icon placeholder
4. Insert benefit headlines and descriptions
5. Style cards per design-dna
6. Add hover effects

**Acceptance Criteria:**
- [ ] All benefits from copy present
- [ ] Grid layout responsive
- [ ] Cards styled per design-dna
- [ ] Hover effects working

---

## Task 7: Social Proof Section

**Goal:** Build testimonials/stats section

**Files:**
- `[project-folder]/index.html` → `<section class="social-proof">`
- `[project-folder]/style.css` → Testimonial styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Social Proof Section
- `[project-folder]/docs/design-dna.md` → Cards, Typography

**Steps:**
1. Add section headline
2. Create testimonial cards
3. Insert testimonial quotes and attributions
4. Add stats/numbers if applicable
5. Style testimonial layout
6. Add company logos if applicable

**Acceptance Criteria:**
- [ ] Testimonials display correctly
- [ ] Proper attribution formatting
- [ ] Stats prominent if included
- [ ] Visual balance achieved

---

## Task 8: FAQ Section (if applicable)

**Goal:** Build FAQ accordion

**Files:**
- `[project-folder]/index.html` → `<section class="faq">`
- `[project-folder]/style.css` → FAQ styles
- `[project-folder]/script.js` → Accordion functionality

**Reference:**
- `[project-folder]/docs/copy-sections.md` → FAQ Section
- `[project-folder]/docs/design-dna.md` → Typography

**Steps:**
1. Add section headline
2. Create FAQ item structure
3. Insert questions and answers
4. Style accordion items
5. Implement toggle functionality
6. Add open/close icons

**Acceptance Criteria:**
- [ ] All FAQs from copy present
- [ ] Accordion toggles work
- [ ] Smooth open/close animation
- [ ] Only one item open at a time (optional)

---

## Task 9: Final CTA Section

**Goal:** Build closing CTA with urgency

**Files:**
- `[project-folder]/index.html` → `<section class="final-cta">`
- `[project-folder]/style.css` → Final CTA styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Final CTA Section
- `[project-folder]/docs/design-dna.md` → Buttons, Hero styles

**Steps:**
1. Add section headline
2. Add supporting text
3. Add urgency message if applicable
4. Add CTA button
5. Add reassurance text
6. Style with contrasting background

**Acceptance Criteria:**
- [ ] Strong visual contrast from previous section
- [ ] CTA button prominent
- [ ] Urgency clear if applicable
- [ ] Reassurance visible

---

## Task 10: Footer

**Goal:** Build footer with links and legal

**Files:**
- `[project-folder]/index.html` → `<footer>`
- `[project-folder]/style.css` → Footer styles

**Reference:**
- `[project-folder]/docs/copy-sections.md` → Footer content
- `[project-folder]/docs/design-dna.md` → Typography, Colors

**Steps:**
1. Add footer structure
2. Add link columns if needed
3. Add copyright text
4. Add social links if applicable
5. Style footer layout
6. Ensure adequate contrast

**Acceptance Criteria:**
- [ ] All required links present
- [ ] Copyright text correct
- [ ] Layout responsive
- [ ] Adequate color contrast

---

## Task 11: Animations + Polish

**Goal:** Add micro-interactions and scroll animations

**Files:**
- `[project-folder]/style.css` → Animation classes
- `[project-folder]/script.js` → Scroll trigger logic

**Reference:**
- `[project-folder]/docs/design-dna.md` → Micro-interactions

**Steps:**
1. Add CSS transition classes
2. Add @keyframes for animations
3. Implement scroll reveal (fade-in-up)
4. Add button hover effects
5. Add card hover effects
6. Test all interactions

**Acceptance Criteria:**
- [ ] Buttons have hover effects
- [ ] Cards have hover effects
- [ ] Elements fade in on scroll
- [ ] Animations smooth (60fps)

---

## Task 12: Responsive Polish

**Goal:** Ensure fully responsive design

**Files:**
- `[project-folder]/style.css` → Media queries

**Reference:**
- `[project-folder]/docs/design-dna.md` → Responsive Breakpoints

**Steps:**
1. Test at 375px (mobile)
2. Test at 768px (tablet)
3. Test at 1024px (laptop)
4. Test at 1920px (desktop)
5. Fix any layout issues
6. Adjust font sizes for mobile
7. Ensure touch targets are 44px+

**Acceptance Criteria:**
- [ ] No horizontal scroll on any viewport
- [ ] Text readable at all sizes
- [ ] Touch targets adequate
- [ ] Images scale properly

---

## Execution Notes

**For Builder Subagents:**
- Read `[project-folder]/docs/design-dna.md` before writing ANY CSS
- Copy text exactly from `[project-folder]/docs/copy-sections.md`
- Commit after each task
- Run visual check before marking complete

**Commit Message Format:**
```
feat(landing): [task description]
```

---
*Generated by lp-planning skill*
```

## Image Planning

For each section in the implementation plan, identify visual needs. This helps the image generation steps (Steps 5-7) know what assets to create.

### Image Types

- **hero** - Full-width backgrounds, large feature images
- **icon** - Small icons for benefits, features, navigation
- **illustration** - Explanatory visuals, diagrams, decorative art
- **sticker** - Playful decorative elements, badges, labels
- **decoration** - Abstract shapes, patterns, accents
- **none** - Section doesn't need custom images

### Image Placement

- **background** - Behind section content (full-width or contained)
- **inline** - Within content flow (next to text, in cards)
- **decoration** - Accent elements (corners, edges, floating)

### Task Format with Image Needs

When creating tasks, include an **Image needs** field that describes what visuals would help, without specifying concrete paths (those will be added by lp-image-integration after generation):

```markdown
### Task [N]: [Section Name]

**Type:** Visual (use frontend-design-o)

**Goal:** [What this task accomplishes]

**Files to modify:**
- `index.html` - Add [specific elements]
- `style.css` - Add [specific styles]

**Reference:**
- Copy from: `[project-folder]/docs/copy-sections.md` → [Section]
- Styles from: `[project-folder]/docs/design-dna.md` → [Component]

**Image needs:**
- [type]: [description], [placement]
- [type]: [description], [placement]

**Steps:**
1. [Specific step 1]
2. [Specific step 2]

**Acceptance Criteria:**
- [ ] [Checkable criterion 1]
- [ ] [Checkable criterion 2]
```

### Example Image Needs

**Hero Section:**
```markdown
**Image needs:**
- Background image: abstract gradient mesh or lifestyle photo, full-width
- Decorative element: geometric shape accent, bottom-right corner
```

**Benefits Section:**
```markdown
**Image needs:**
- Icons: one icon per benefit (speed, security, simplicity), inline in cards
- Decoration: subtle pattern or shapes, background
```

**Social Proof Section:**
```markdown
**Image needs:**
- Illustration: trust badges or company logos, inline
- Sticker: quote marks or star ratings, decoration
```

**FAQ Section:**
```markdown
**Image needs:**
- none (text-only section works best)
```

### Style Context

Base image style recommendations on the design-dna.md:
- **Mood/Style** - Match the brand personality (professional, playful, minimal, bold)
- **Colors** - Reference primary/secondary colors for consistency
- **Visual Language** - Match the overall aesthetic (geometric, organic, illustrative, photographic)

---

## Completion

After creating the artifact:
1. Confirm implementation-plan.md was created
2. Report back to orchestrator that Step 4 is complete
3. Next step: Step 5 (Image Prompts) - image prompts will be generated based on the image needs identified in this plan
4. Provide path to artifact: `[project-folder]/docs/implementation-plan.md`
