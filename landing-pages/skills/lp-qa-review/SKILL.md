---
name: lp-qa-review
description: Step 6 of landing page creation - comprehensive QA review with scoring system to verify quality before delivery
---

# Landing Page QA Review

You are performing a comprehensive quality assurance review of the completed landing page. Use a scoring system to ensure quality gates are met.

## CRITICAL RULES

1. **Score objectively** - Use the checklist exactly
2. **Test thoroughly** - Actually verify each item
3. **Document issues** - Specific file:line references
4. **Minimum score: 80** - Below 80 = needs fixes
5. **Output artifact** - Create docs/qa-report.md

## Input Files

Review these files:
- `index.html` - Page markup
- `style.css` - Styling
- `script.js` - Interactions
- `docs/design-dna.md` - Expected design
- `docs/copy-sections.md` - Expected content

## Scoring System

Total: 100 points across 4 categories

| Category | Points | Description |
|----------|--------|-------------|
| Responsive | 25 | Works on all devices |
| Accessibility | 25 | Usable by everyone |
| Performance | 25 | Fast loading |
| SEO Basics | 25 | Search optimized |

### Passing Score
- **80+**: Ready for launch ✅
- **60-79**: Needs minor fixes ⚠️
- **<60**: Needs major work ❌

## Review Checklist

### Category 1: Responsive (25 points)

Test at each viewport:

**Desktop 1920px (5 points)**
- [ ] Layout displays correctly
- [ ] No horizontal scroll
- [ ] Text readable
- [ ] Images not stretched

**Laptop 1366px (5 points)**
- [ ] Layout adapts properly
- [ ] No content overflow
- [ ] Navigation usable

**Tablet 768px (5 points)**
- [ ] Columns stack appropriately
- [ ] Text size adequate
- [ ] Touch targets sufficient

**Mobile 375px (5 points)**
- [ ] Single column layout
- [ ] All text readable
- [ ] CTA buttons full width
- [ ] No tiny tap targets

**General Responsive (5 points)**
- [ ] No fixed widths breaking layout
- [ ] Images use max-width: 100%
- [ ] Media queries working

### Category 2: Accessibility (25 points)

**Color Contrast (7 points)**
- [ ] Text on background: 4.5:1 minimum
- [ ] Large text: 3:1 minimum
- [ ] Buttons have adequate contrast
- [ ] Links distinguishable

**Semantic HTML (6 points)**
- [ ] `<header>`, `<main>`, `<footer>` present
- [ ] `<nav>` for navigation
- [ ] `<section>` with headings
- [ ] Proper heading hierarchy (h1→h2→h3)

**Image Accessibility (6 points)**
- [ ] All `<img>` have alt text
- [ ] Decorative images have alt=""
- [ ] Icons have aria-labels

**Interactive Elements (6 points)**
- [ ] All links have visible focus state
- [ ] Buttons have focus state
- [ ] Form inputs have labels
- [ ] Tab order logical

### Category 3: Performance (25 points)

**File Size (10 points)**
- [ ] HTML < 50KB
- [ ] CSS < 50KB
- [ ] JS < 50KB
- [ ] Total < 500KB (without images)

**Best Practices (10 points)**
- [ ] CSS loaded in `<head>`
- [ ] JS loaded before `</body>` or deferred
- [ ] No render-blocking resources
- [ ] No unused CSS (minimal bloat)

**Images (5 points)**
- [ ] Images optimized (or placeholders)
- [ ] Proper image dimensions set
- [ ] Loading="lazy" on below-fold images

### Category 4: SEO Basics (25 points)

**Meta Tags (10 points)**
- [ ] `<title>` present and descriptive
- [ ] `<meta name="description">` present
- [ ] `<meta name="viewport">` present
- [ ] Charset declared

**Open Graph (7 points)**
- [ ] `og:title` present
- [ ] `og:description` present
- [ ] `og:image` present (or placeholder)
- [ ] `og:type` present

**Content Structure (8 points)**
- [ ] Single `<h1>` on page
- [ ] Heading hierarchy logical
- [ ] Links have descriptive text
- [ ] No broken links

## Review Process

### Step 1: Automated Checks

Read the files and verify:

```
// Check HTML structure
- DOCTYPE present
- lang attribute on <html>
- <head> contains required meta tags
- <body> contains semantic elements

// Check CSS
- :root variables defined
- Media queries present
- No !important overuse

// Check JS
- No console.log statements
- Event listeners properly attached
- No global variable pollution
```

### Step 2: Manual Verification

For each checklist item:
1. Actually test it
2. Note pass/fail
3. Document issues with specifics

### Step 3: Design Match Verification

Compare against design-dna.md:
- [ ] Colors match exactly
- [ ] Typography matches
- [ ] Spacing matches
- [ ] Components match specifications

### Step 4: Copy Verification

Compare against copy-sections.md:
- [ ] Headlines match exactly
- [ ] Body copy matches
- [ ] CTAs match
- [ ] No typos introduced

## Output Artifact

Create `docs/qa-report.md`:

```markdown
# QA Report: [Project Name]

> Quality assurance review for [project name] landing page

## Summary

| Category | Score | Max |
|----------|-------|-----|
| Responsive | [X] | 25 |
| Accessibility | [X] | 25 |
| Performance | [X] | 25 |
| SEO Basics | [X] | 25 |
| **Total** | **[X]** | **100** |

## Verdict

[✅ READY FOR LAUNCH / ⚠️ NEEDS FIXES / ❌ NEEDS MAJOR WORK]

---

## Detailed Results

### Responsive (X/25)

#### Desktop 1920px (X/5)
- [✓/✗] Layout displays correctly
- [✓/✗] No horizontal scroll
- [Issue if any: description]

#### Laptop 1366px (X/5)
- [✓/✗] Layout adapts properly
- [Issue if any: description]

#### Tablet 768px (X/5)
- [✓/✗] Columns stack appropriately
- [Issue if any: description]

#### Mobile 375px (X/5)
- [✓/✗] Single column layout
- [✓/✗] All text readable
- [Issue if any: description]

#### General (X/5)
- [✓/✗] Media queries working
- [Issue if any: description]

---

### Accessibility (X/25)

#### Color Contrast (X/7)
- [✓/✗] Text contrast adequate
- [Issue if any: specific element, current ratio]

#### Semantic HTML (X/6)
- [✓/✗] Proper landmarks used
- [✓/✗] Heading hierarchy correct
- [Issue if any: description]

#### Image Accessibility (X/6)
- [✓/✗] Alt text present
- [Missing: specific images]

#### Interactive Elements (X/6)
- [✓/✗] Focus states visible
- [Issue if any: description]

---

### Performance (X/25)

#### File Sizes (X/10)
- HTML: [X]KB [✓/✗]
- CSS: [X]KB [✓/✗]
- JS: [X]KB [✓/✗]
- Total: [X]KB [✓/✗]

#### Best Practices (X/10)
- [✓/✗] CSS in head
- [✓/✗] JS deferred
- [Issue if any: description]

#### Images (X/5)
- [✓/✗] Optimized or placeholders
- [Issue if any: description]

---

### SEO Basics (X/25)

#### Meta Tags (X/10)
- Title: [present/missing] - "[title content]"
- Description: [present/missing]
- Viewport: [present/missing]

#### Open Graph (X/7)
- og:title: [present/missing]
- og:description: [present/missing]
- og:image: [present/missing]

#### Content Structure (X/8)
- [✓/✗] Single h1
- [✓/✗] Logical headings
- [Issue if any: description]

---

## Critical Issues

Issues that MUST be fixed before launch:

1. **[Issue Title]** - Priority: HIGH
   - File: [file:line]
   - Problem: [description]
   - Fix: [suggested fix]

2. **[Issue Title]** - Priority: HIGH
   - File: [file:line]
   - Problem: [description]
   - Fix: [suggested fix]

---

## Improvement Recommendations

Nice-to-have improvements:

1. **[Suggestion]** - Impact: MEDIUM
   - Description: [what to improve]
   - Benefit: [why it helps]

2. **[Suggestion]** - Impact: LOW
   - Description: [what to improve]
   - Benefit: [why it helps]

---

## Design Match

| Element | Expected | Actual | Match |
|---------|----------|--------|-------|
| Primary Color | [hex] | [hex] | ✓/✗ |
| Body Font | [font] | [font] | ✓/✗ |
| H1 Size | [px] | [px] | ✓/✗ |
| Section Spacing | [px] | [px] | ✓/✗ |

## Copy Match

| Section | Match | Notes |
|---------|-------|-------|
| Hero Headline | ✓/✗ | [any discrepancy] |
| Hero Subheadline | ✓/✗ | |
| Benefits | ✓/✗ | |
| Testimonials | ✓/✗ | |
| CTAs | ✓/✗ | |

---

## Next Steps

[Based on verdict:]

### If READY FOR LAUNCH ✅
- Add real images to replace placeholders
- Connect forms to backend
- Deploy to hosting

### If NEEDS FIXES ⚠️
- Fix critical issues listed above
- Re-run QA review
- Target score: 80+

### If NEEDS MAJOR WORK ❌
- Address all critical and high-priority issues
- Consider re-running building skill
- Major refactoring needed

---
*Generated by lp-qa-review skill*
*Review Date: [date]*
```

## Handling Results

### Score >= 80: Pass
```
Report to orchestrator:
- QA complete
- Score: [X]/100
- Ready for launch
```

### Score < 80: Fail
```
Report to orchestrator:
- QA failed
- Score: [X]/100
- Critical issues: [list]
- Recommend: Fix issues and re-run QA
```

If score < 80, the orchestrator should:
1. Use lp-building to fix critical issues
2. Re-run lp-qa-review
3. Repeat until score >= 80

## Quality Gate Enforcement

This is a hard gate. Do NOT approve a landing page with:
- Score below 80
- Any critical accessibility issues
- Broken responsive layouts
- Major copy discrepancies

The landing page must be production-ready before delivery.
