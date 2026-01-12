---
name: lp-text-composing
description: Step 3 of landing page creation - write conversion-optimized copy using proven copywriting frameworks (4U, PAS, AIDA)
---

# Landing Page Text Composing

You are writing marketing copy that converts visitors into customers. Use proven copywriting frameworks and collaborate with the user to refine each section.

## CRITICAL RULES

1. **Read brainstorm-brief first** - Understand audience, problem, solution
2. **Use copywriting frameworks** - 4U for headlines, PAS for problem sections
3. **Propose variants** - Always give 2-3 options for headlines
4. **User approves each section** - Use AskUserQuestion for choices
5. **Output artifact** - Create docs/copy-sections.md when complete

## Copywriting Frameworks

| Framework | Use For | Structure |
|-----------|---------|-----------|
| **4U** | Headlines | Urgent, Unique, Useful, Ultra-specific |
| **PAS** | Problem section | Problem → Agitate → Solution |
| **AIDA** | Page flow | Attention → Interest → Desire → Action |
| **FAB** | Benefits | Feature → Advantage → Benefit |
| **Social Proof** | Trust | Testimonials, numbers, logos |

## Input

Read `docs/brainstorm-brief.md` to understand:
- Target audience and their language
- Main problem/pain point
- Solution and benefits
- USP and differentiators
- Tone of voice

## Section-by-Section Process

### Section 1: Hero Headline

Apply 4U Framework:
- **U**rgent: Creates sense of now
- **U**nique: Different from competitors
- **U**seful: Clear benefit
- **U**ltra-specific: Concrete, measurable

Generate 3 headline variants:

```
Variant A (Benefit-focused):
"[Achieve specific result] in [timeframe] without [pain point]"

Variant B (Problem-focused):
"Stop [painful activity]. Start [desired outcome]."

Variant C (Social proof):
"Join [X] [audience] who [achieved result]"
```

```
Use AskUserQuestion:
Question: "Which headline resonates most with your audience?"
Header: "Headline"
Options:
- label: "Variant A"
  description: "[full headline A]"
- label: "Variant B"
  description: "[full headline B]"
- label: "Variant C"
  description: "[full headline C]"
- label: "Modify one"
  description: "I like one but want to tweak it"
```

### Section 2: Subheadline

Support the headline with:
- Clarification of the main benefit
- Who it's for
- What they'll get

Generate 2 variants and let user choose.

### Section 3: Primary CTA Button

```
Use AskUserQuestion:
Question: "What should the main CTA button say?"
Header: "CTA Text"
Options:
- label: "Start Free →"
  description: "Action-oriented, low commitment"
- label: "Get Started Now"
  description: "Urgent, immediate action"
- label: "See How It Works"
  description: "Educational, lower friction"
- label: "Custom text"
  description: "I'll write my own CTA"
```

### Section 4: Problem Section (PAS)

**Problem:** State the problem clearly
- Use audience's own words
- Be specific about the pain

**Agitate:** Make it worse
- Show consequences of not solving
- Emotional resonance

**Solution:** Introduce your offering
- How it addresses the problem
- Transition to benefits

Write this section and present for approval:

```
Use AskUserQuestion:
Question: "Does this problem section accurately capture your audience's pain?"
Header: "Problem"
Options:
- label: "Yes, perfect"
  description: "This captures it well"
- label: "Too aggressive"
  description: "Tone it down slightly"
- label: "Not specific enough"
  description: "Add more concrete details"
- label: "Let me edit"
  description: "I'll provide specific changes"
```

### Section 5: Benefits

Transform features into benefits using FAB:
- Feature: What it does
- Advantage: Why that matters
- Benefit: How it helps the user

Create 3-5 benefits:

```markdown
✓ **[Benefit headline]**
[One sentence expanding on the benefit and its impact]

✓ **[Benefit headline]**
[One sentence expanding on the benefit and its impact]

✓ **[Benefit headline]**
[One sentence expanding on the benefit and its impact]
```

### Section 6: Social Proof

Based on what's available (from brief):

**If testimonials:**
```markdown
> "[Specific result or transformation quote]"
> — [Name], [Title/Company]
```

**If numbers:**
```markdown
- [X]+ [metric] (e.g., "10,000+ users")
- [Y]% [improvement] (e.g., "50% faster")
- [Z] [timeframe] (e.g., "2 minute setup")
```

**If logos:**
List trusted companies/publications that use or feature the product.

**If none:**
Suggest alternatives:
- Money-back guarantee
- Free trial promise
- Expert credentials

### Section 7: FAQ (Optional)

Address common objections:
- Price concerns
- Time investment
- Technical requirements
- Results timeline

Write 3-5 Q&A pairs based on likely objections.

### Section 8: Final CTA

Create urgency and reinforce action:

**Headline:** Restate value proposition differently
**Urgency:** If applicable (deadline, limited spots)
**Button:** Same or stronger CTA
**Reassurance:** Risk-reducer (guarantee, no credit card, etc.)

## Output Artifact

Create `docs/copy-sections.md`:

```markdown
# Landing Page Copy

> Copy for [project name] landing page

## Hero Section

### Headline
"[Chosen headline]"

### Subheadline
"[Supporting subheadline]"

### Primary CTA
Button: "[CTA text]"

---

## Problem Section

### The Problem
[Problem paragraph]

### The Agitation
[Agitation paragraph]

### The Solution
[Solution paragraph - transition to product]

---

## Benefits Section

### Section Headline
"[Benefits section title]"

### Benefits List

✓ **[Benefit 1 headline]**
[Benefit 1 description]

✓ **[Benefit 2 headline]**
[Benefit 2 description]

✓ **[Benefit 3 headline]**
[Benefit 3 description]

[Additional benefits if applicable]

---

## Social Proof Section

### Section Headline
"[Social proof section title]"

### Testimonials

> "[Testimonial 1 quote]"
> — [Name], [Title at Company]

> "[Testimonial 2 quote]"
> — [Name], [Title at Company]

### Stats (if applicable)
- [Stat 1]
- [Stat 2]
- [Stat 3]

---

## FAQ Section

### Section Headline
"Frequently Asked Questions"

**Q: [Question 1]**
A: [Answer 1]

**Q: [Question 2]**
A: [Answer 2]

**Q: [Question 3]**
A: [Answer 3]

---

## Final CTA Section

### Headline
"[Final CTA headline]"

### Supporting Text
[One line of supporting copy]

### Urgency (if applicable)
"[Urgency message]"

### Button
"[Final CTA button text]"

### Reassurance
"[Risk reducer - guarantee, no credit card, etc.]"

---

## Microcopy

### Navigation
- [Nav item 1]
- [Nav item 2]
- [Nav item 3]

### Footer
[Copyright and legal text]

### Form Labels (if applicable)
- Email: "Enter your email"
- Name: "Your name"
- Submit: "[Submit button text]"

---
*Generated by lp-text-composing skill*
```

## Quality Checklist

Before completing, verify:
- [ ] Headlines use 4U framework principles
- [ ] Problem section follows PAS structure
- [ ] Benefits are outcome-focused, not feature-focused
- [ ] Social proof is specific and credible
- [ ] CTAs are action-oriented and clear
- [ ] Tone matches brand guidelines from brief
- [ ] No jargon that audience wouldn't understand

## Completion

After creating the artifact:
1. Confirm copy-sections.md was created
2. Report back to orchestrator that Step 3 is complete
3. Provide path to artifact: `docs/copy-sections.md`
