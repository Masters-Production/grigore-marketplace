---
name: lp-design-dna
description: Step 2 of landing page creation - create a complete design system by leveraging frontend-design-o skill for professional quality
---

# Landing Page Design DNA

You are creating a complete design system for the landing page. This step REQUIRES using the frontend-design-o skill to ensure professional, non-generic output.

## CRITICAL RULES

1. **Read brainstorm-brief first** - Understand the context before designing
2. **MANDATORY: Use frontend-design-o skill** - This is NOT optional
3. **Be specific** - Exact hex codes, exact pixel values, exact CSS properties
4. **Output artifact** - Create docs/design-dna.md when complete
5. **NO GENERIC DESIGNS** - NEVER use default framework colors, emoji icons, or template layouts

## MANDATORY WORKFLOW

### Step 1: Read Context

Read `docs/brainstorm-brief.md` to understand:
- Type of landing page
- Target audience
- Tone of voice
- Industry/niche

### Step 2: Ask Design Source

```
Use AskUserQuestion:
Question: "How would you like to define the design style?"
Header: "Design Source"
Options:
- label: "Reference website"
  description: "Provide a URL and I'll extract and improve the design style"
- label: "Brand guidelines"
  description: "You have existing colors, fonts, logo to use"
- label: "AI creative direction"
  description: "I'll propose distinctive style options using professional design principles"
```

### Step 3: INVOKE frontend-design-o SKILL

**THIS IS MANDATORY - YOU MUST USE THIS SKILL**

```
Use Skill tool:
skill: "frontend-design-o"
args: "Create a complete design system for a landing page with the following context:

PROJECT: [from brainstorm-brief]
TYPE: [landing page type]
AUDIENCE: [target audience]
TONE: [voice/personality]
DESIGN SOURCE: [user's choice from step 2]
REFERENCE/BRAND: [any provided reference or brand guidelines]

REQUIREMENTS:
1. Create a DISTINCTIVE design - no generic AI aesthetics
2. Avoid all default framework colors (Tailwind, Bootstrap, Material)
3. Use custom color palette derived from context
4. Specify distinctive Google Fonts pairing
5. Include at least 3 signature design elements
6. NO emoji icons - specify proper icon library
7. Include hero visual concept (not just gradient)
8. Define unique section dividers/shapes
9. Think like a designer with 10+ years experience

OUTPUT FORMAT:
Return complete design-dna.md content with:
- Full color palette with unique hex codes
- Typography with Google Fonts and letter-spacing
- Distinctive elements specification
- UI component CSS
- Micro-interactions
- Responsive guidelines"
```

### Step 4: Review and Refine

After frontend-design-o returns the design:

1. **Verify quality checklist:**
   - [ ] No banned colors (#2563eb, #7c3aed, #f59e0b, #10b981)
   - [ ] No emoji icons
   - [ ] Distinctive typography (not just Inter/Roboto)
   - [ ] At least 3 signature design elements defined
   - [ ] Hero has visual interest beyond gradient
   - [ ] Custom section dividers specified

2. **If any check fails:** Re-invoke frontend-design-o with specific corrections

3. **If all checks pass:** Proceed to output

### Step 5: Output Artifact

Create `docs/design-dna.md` with the complete design system.

## ANTI-GENERIC REQUIREMENTS

### BANNED - Must Never Appear in Output:

**Colors:**
- #2563eb, #3b82f6 (Tailwind blue)
- #7c3aed, #8b5cf6, #6366f1 (Tailwind violet/indigo)
- #f59e0b, #fbbf24 (Tailwind amber)
- #10b981, #34d399 (Tailwind emerald)

**Icons:**
- Any emoji (⏱️ 🤖 📊 ✨ 🚀 💡 ⚡)

**Typography:**
- System fonts only
- Inter without distinctive treatment

**Layout:**
- Plain gradient-only hero
- Standard template structure

### REQUIRED - Must Appear in Output:

- Unique color palette (custom hex codes)
- Google Fonts with personality
- Icon library specification (Phosphor/Heroicons/Lucide)
- At least 3 distinctive design elements:
  - Custom background shapes/patterns
  - Unique section dividers (waves, angles)
  - Signature visual treatment
  - Creative button/card styles
  - Animated elements
  - Glassmorphism/neumorphism (if fits brand)

## Integration Points

### From Previous Step
- `docs/brainstorm-brief.md` - Context for design decisions

### To Next Step
- `docs/design-dna.md` - Complete design system for building

## Completion

After creating the artifact:
1. Confirm design-dna.md was created
2. Verify all quality checklist items pass
3. Report to orchestrator: "Step 2 complete - Design DNA created with distinctive, professional design"
4. Provide path: `docs/design-dna.md`

---

## Why frontend-design-o is Mandatory

The frontend-design-o skill is specifically designed to:
- Create distinctive, production-grade designs
- Avoid generic AI aesthetics
- Think like a professional designer with 10+ years experience
- Generate creative, polished code and UI design

Without it, output tends toward generic templates. WITH it, output has professional quality and uniqueness.
