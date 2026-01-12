# QA Checklist Template

> Use this checklist to review landing page quality before delivery.

## Project Information

- **Project Name:**
- **Review Date:**
- **Reviewer:**

---

## Scoring Summary

| Category | Score | Max | Notes |
|----------|-------|-----|-------|
| Responsive | /25 | 25 | |
| Accessibility | /25 | 25 | |
| Performance | /25 | 25 | |
| SEO Basics | /25 | 25 | |
| **Total** | **/100** | **100** | |

### Verdict
- [ ] ✅ READY FOR LAUNCH (80+)
- [ ] ⚠️ NEEDS FIXES (60-79)
- [ ] ❌ NEEDS MAJOR WORK (<60)

---

## Responsive Testing (25 points)

### Desktop 1920px (5 points)
- [ ] Layout displays correctly
- [ ] No horizontal scroll
- [ ] All text readable
- [ ] Images not stretched/distorted
- [ ] Navigation fully visible

**Score:** /5
**Issues:**

### Laptop 1366px (5 points)
- [ ] Layout adapts properly
- [ ] No content overflow
- [ ] Navigation usable
- [ ] Cards/grids aligned

**Score:** /5
**Issues:**

### Tablet 768px (5 points)
- [ ] Columns stack appropriately
- [ ] Text size adequate
- [ ] Touch targets sufficient
- [ ] Images scale properly

**Score:** /5
**Issues:**

### Mobile 375px (5 points)
- [ ] Single column layout works
- [ ] All text readable (16px min)
- [ ] CTA buttons appropriately sized
- [ ] No tiny tap targets
- [ ] Mobile menu functional

**Score:** /5
**Issues:**

### General Responsive (5 points)
- [ ] No fixed widths breaking layout
- [ ] Images use max-width: 100%
- [ ] Media queries working correctly
- [ ] Smooth transitions between breakpoints

**Score:** /5
**Issues:**

---

## Accessibility Testing (25 points)

### Color Contrast (7 points)
- [ ] Body text on background: 4.5:1 or higher
- [ ] Large text (24px+): 3:1 or higher
- [ ] Button text contrast adequate
- [ ] Link text distinguishable from body
- [ ] Focus indicators visible

**Score:** /7
**Issues:**

### Semantic HTML (6 points)
- [ ] `<header>` present
- [ ] `<nav>` for navigation
- [ ] `<main>` for main content
- [ ] `<section>` with appropriate headings
- [ ] `<footer>` present
- [ ] Heading hierarchy h1→h2→h3 (no skips)

**Score:** /6
**Issues:**

### Image Accessibility (6 points)
- [ ] All `<img>` have alt attribute
- [ ] Alt text is descriptive
- [ ] Decorative images have alt=""
- [ ] Icons have aria-labels or sr-only text
- [ ] No text embedded in images

**Score:** /6
**Issues:**

### Interactive Elements (6 points)
- [ ] All links have visible focus state
- [ ] Buttons have visible focus state
- [ ] Form inputs have associated labels
- [ ] Tab order is logical
- [ ] Skip link present (bonus)

**Score:** /6
**Issues:**

---

## Performance Testing (25 points)

### File Sizes (10 points)
- [ ] HTML < 50KB
  - Actual size: KB
- [ ] CSS < 50KB
  - Actual size: KB
- [ ] JS < 50KB
  - Actual size: KB
- [ ] Total (without images) < 500KB
  - Actual total: KB

**Score:** /10
**Issues:**

### Loading Best Practices (10 points)
- [ ] CSS loaded in `<head>`
- [ ] JS loaded before `</body>` or has defer
- [ ] No render-blocking resources
- [ ] No unused CSS (minimal bloat)
- [ ] No unnecessary libraries

**Score:** /10
**Issues:**

### Image Optimization (5 points)
- [ ] Images appropriately sized
- [ ] Width/height attributes set
- [ ] loading="lazy" on below-fold images
- [ ] Placeholder images or actual assets

**Score:** /5
**Issues:**

---

## SEO Basics Testing (25 points)

### Meta Tags (10 points)
- [ ] `<title>` present
  - Content:
- [ ] `<title>` is descriptive (50-60 chars)
- [ ] `<meta name="description">` present
  - Content:
- [ ] Description is compelling (150-160 chars)
- [ ] `<meta name="viewport">` present
- [ ] `<meta charset="UTF-8">` present

**Score:** /10
**Issues:**

### Open Graph Tags (7 points)
- [ ] `og:title` present
- [ ] `og:description` present
- [ ] `og:image` present
- [ ] `og:url` present
- [ ] `og:type` present

**Score:** /7
**Issues:**

### Content Structure (8 points)
- [ ] Single `<h1>` on page
- [ ] `<h1>` contains target keyword
- [ ] Heading hierarchy is logical
- [ ] Links have descriptive text (no "click here")
- [ ] No broken links

**Score:** /8
**Issues:**

---

## Design Compliance Check

### Color Match
| Element | Expected (design-dna) | Actual | Match? |
|---------|----------------------|--------|--------|
| Primary | | | ☐ |
| Secondary | | | ☐ |
| Background | | | ☐ |
| Text | | | ☐ |

### Typography Match
| Element | Expected Size | Actual | Match? |
|---------|--------------|--------|--------|
| H1 | | | ☐ |
| H2 | | | ☐ |
| Body | | | ☐ |

### Spacing Match
| Element | Expected | Actual | Match? |
|---------|----------|--------|--------|
| Section padding | | | ☐ |
| Container width | | | ☐ |

---

## Copy Compliance Check

| Section | Matches copy-sections.md? | Notes |
|---------|--------------------------|-------|
| Hero headline | ☐ | |
| Hero subheadline | ☐ | |
| Problem section | ☐ | |
| Benefits | ☐ | |
| Testimonials | ☐ | |
| FAQ | ☐ | |
| Final CTA | ☐ | |

---

## Critical Issues (Must Fix)

| # | Issue | File:Line | Severity | Fix |
|---|-------|-----------|----------|-----|
| 1 | | | HIGH | |
| 2 | | | HIGH | |
| 3 | | | HIGH | |

---

## Improvement Suggestions (Nice to Have)

| # | Suggestion | Impact | Effort |
|---|------------|--------|--------|
| 1 | | MEDIUM | |
| 2 | | LOW | |
| 3 | | LOW | |

---

## Final Sign-off

- [ ] All critical issues resolved
- [ ] Score meets minimum threshold (80+)
- [ ] Design matches design-dna.md
- [ ] Copy matches copy-sections.md
- [ ] Ready for production deployment

**Final Score:** /100

**Approved By:**
**Date:**

---
*QA Checklist Template v1.0*
