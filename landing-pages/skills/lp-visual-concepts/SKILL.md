---
name: lp-visual-concepts
description: Step 5 of landing page creation - generate creative visual concepts with metaphors, composition, and rendering style for each section
---

# Landing Page Visual Concepts

You are creating visual concepts for the landing page. Think like a creative director - propose visual metaphors, composition strategies, and rendering styles that will make the landing page stand out.

## CRITICAL RULES

1. **Read ALL docs first** - brainstorm-brief, design-dna, copy-sections, implementation-plan
2. **Think conceptually** - Don't just describe "blue background", think "rocket launching = growth"
3. **Propose 2-3 options** - Use AskUserQuestion for each major section
4. **Document composition** - Layering, positioning, effects, not just "what" but "how"
5. **Stay consistent** - All concepts must align with design-dna mood and colors
6. **Complete documentation** - Output `visual-concepts.md` with full specifications

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
Read and understand:
- `[project-folder]/docs/brainstorm-brief.md` - Project context and audience
- `[project-folder]/docs/design-dna.md` - Visual style, colors, mood
- `[project-folder]/docs/copy-sections.md` - Text content for context
- `[project-folder]/docs/implementation-plan.md` - Sections and structure

### Output Files
- `[project-folder]/docs/visual-concepts.md` - Complete visual concept specifications

## Visual Concept Generation Process

### Step 1: Read All Documentation

Read all docs from `[project-folder]/docs/`:

```
1. brainstorm-brief.md - Understand:
   - Target audience (who are we designing for?)
   - Product/service (what visual metaphors fit?)
   - Tone (playful, professional, bold, minimal?)

2. design-dna.md - Extract:
   - Color palette (exact hex codes to reference)
   - Mood/atmosphere (modern, playful, professional)
   - Visual style (minimalist, bold, organic)

3. copy-sections.md - Analyze:
   - Headlines (what visual can amplify this message?)
   - Key benefits (what metaphors represent these?)
   - Emotional triggers (what imagery evokes this?)

4. implementation-plan.md - Map sections:
   - Which sections need strong visuals?
   - What's the visual hierarchy?
```

### Step 2: Analyze Visual Opportunities

For each major section, think:

| Question | Purpose |
|----------|---------|
| What's the core message? | Find the metaphor |
| What emotion should it evoke? | Define the mood |
| How should elements be arranged? | Plan composition |
| What makes it memorable? | Add unique touches |

**Visual Metaphor Examples:**

| Message | Weak Visual | Strong Visual |
|---------|-------------|---------------|
| "Save time" | Clock icon | Person breaking free from clock chains |
| "Grow your business" | Arrow up | Rocket launching through clouds |
| "Security" | Lock icon | Shield deflecting attacks with energy |
| "Productivity" | Checklist | Person flying above completed tasks |
| "Leadership" | Crown | Chess pieces in strategic formation |

### Step 3: Propose Visual Concepts Per Section

**For each major section, propose 2-3 concepts using AskUserQuestion.**

Think about:
1. **Visual Metaphor** - What object/scene represents the message?
2. **Composition** - How are elements arranged? What's in front/behind?
3. **Rendering Style** - 3D realistic? Illustrated? Photographic?

---

**Hero Section Proposal:**

```
Use AskUserQuestion:
Question: "Ce concept vizual pentru Hero section?"
Header: "Hero Concept"
Options:
- label: "[Concept 1 Name]"
  description: "Metaforă: [X reprezintă Y]. Compoziție: [descriere layering]. Stil: [3D/ilustrație/foto]"

- label: "[Concept 2 Name]"
  description: "Metaforă: [X reprezintă Y]. Compoziție: [descriere layering]. Stil: [3D/ilustrație/foto]"

- label: "[Concept 3 Name]"
  description: "Metaforă: [X reprezintă Y]. Compoziție: [descriere layering]. Stil: [3D/ilustrație/foto]"
```

**Example Hero Concepts (adapt to project):**

| Concept | Metaphor | Composition | Style |
|---------|----------|-------------|-------|
| Rocket Launch | Growth/Speed | 3D rocket at 15° angle, exits frame bottom, text behind | Chrome metallic, motion blur, rim lighting |
| Breaking Free | Liberation | Person breaking chains, fragments floating | Dramatic lighting, slow-motion freeze |
| Chess Strategy | Leadership | Chess pieces on board, king prominent | Marble texture, reflective surface, depth blur |

---

**Benefits Section Proposal:**

```
Use AskUserQuestion:
Question: "Ce stil vizual pentru secțiunea Benefits?"
Header: "Benefits Style"
Options:
- label: "3D Isometric Icons"
  description: "Iconuri 3D cu perspectivă isometrică, umbre soft, materiale lucioase"

- label: "Illustrated Scenes"
  description: "Mini-ilustrații pentru fiecare benefit, stil consistent cu hero"

- label: "Abstract Symbols"
  description: "Forme geometrice abstracte care simbolizează fiecare benefit"

- label: "Photo-realistic Objects"
  description: "Obiecte 3D foto-realiste relevante pentru fiecare benefit"
```

---

**Social Proof Section Proposal:**

```
Use AskUserQuestion:
Question: "Ce vizual pentru Social Proof?"
Header: "Social Proof"
Options:
- label: "Decorative quotes"
  description: "Ghilimele stilizate 3D, efecte de sticlă, floating"

- label: "Avatar frames"
  description: "Frame-uri decorative pentru avatare, stil consistent"

- label: "Minimal/Text only"
  description: "Focus pe text, fără elemente vizuale suplimentare"
```

---

**CTA Section Proposal:**

```
Use AskUserQuestion:
Question: "Ce concept pentru secțiunea CTA finală?"
Header: "Final CTA"
Options:
- label: "Echo Hero"
  description: "Reia elementele din hero într-o formă simplificată"

- label: "Destination Visual"
  description: "Arată 'destinația' - rezultatul după folosirea produsului"

- label: "Urgency Element"
  description: "Element vizual care creează urgență (timer stilizat, etc.)"

- label: "Clean/Minimal"
  description: "Focus pe CTA button, fundal gradient simplu"
```

### Step 4: Document Visual Concepts

After user confirms each section, document in `visual-concepts.md`.

**Format for each section:**

```markdown
## [Section Name]

### Concept vizual
**Metaforă:** [Ce reprezintă ce - ex: "Racheta = creștere rapidă"]
**Mesaj:** [Ce comunică vizual acest concept]

### Compoziție
- **Prim-plan:** [Element principal - poziție, unghi, mărime]
- **Plan secundar:** [Elemente de suport]
- **Fundal:** [Tip fundal - gradient, pattern, blur]
- **Text layering:** [Cum interacționează textul cu elementele vizuale]
- **Elemente decorative:** [Particule, forme, efecte în colțuri/margini]

### Stil rendering
- **Tip:** [3D realist / Ilustrație / Foto / Mixt]
- **Materiale:** [Chrome, marmură, sticlă, etc.]
- **Lighting:** [Studio, natural, dramatic, rim light]
- **Efecte:** [Motion blur, bloom, reflecții, shadows]
- **Culori:** [Referințe exacte din design-dna cu hex codes]

### Imagini necesare
1. `[id]` - [descriere] ([background type: transparent/keep])
2. `[id]` - [descriere] ([background type])
```

**Complete visual-concepts.md Template:**

```markdown
# Visual Concepts for [Project Name]

Generated: [timestamp]
Design DNA Reference: [project-folder]/docs/design-dna.md

---

## Hero Section

### Concept vizual
**Metaforă:** [descriere]
**Mesaj:** [descriere]

### Compoziție
- **Prim-plan:** [descriere]
- **Plan secundar:** [descriere]
- **Fundal:** [descriere]
- **Text layering:** [descriere]
- **Elemente decorative:** [descriere]

### Stil rendering
- **Tip:** [descriere]
- **Materiale:** [descriere]
- **Lighting:** [descriere]
- **Efecte:** [descriere]
- **Culori:** Primary (#hex), Secondary (#hex), Accent (#hex)

### Imagini necesare
1. `hero-main` - [descriere] (transparent)
2. `hero-bg` - [descriere] (keep)
3. `hero-particles` - [descriere] (transparent)

---

## Benefits Section

### Concept vizual
**Stil:** [3D isometric / Illustrated / etc.]
**Consistență:** [Cum se leagă de hero]

### Stil rendering
- **Tip:** [descriere]
- **Materiale:** [descriere]
- **Culori:** [referințe hex]

### Imagini necesare
| ID | Benefit | Descriere |
|----|---------|-----------|
| `icon-benefit-1` | [benefit name] | [descriere vizuală] |
| `icon-benefit-2` | [benefit name] | [descriere vizuală] |
| `icon-benefit-3` | [benefit name] | [descriere vizuală] |

---

## Social Proof Section

### Concept vizual
**Stil:** [descriere]

### Imagini necesare
[lista sau "N/A - text only"]

---

## CTA Section

### Concept vizual
**Metaforă:** [descriere]
**Legătură cu Hero:** [cum se leagă]

### Compoziție
[descriere]

### Imagini necesare
[lista]

---

## Decorațiuni Globale

### Floating Elements
| ID | Poziție | Descriere |
|----|---------|-----------|
| `deco-blob-1` | Hero corners | [descriere] |
| `deco-particles` | Throughout | [descriere] |

### Divisori secțiuni
| ID | Între secțiuni | Stil |
|----|----------------|------|
| `divider-1` | Hero → Benefits | [wave/angle/etc.] |

---

## Composition Notes for Image Prompts

**Key rendering terms to use:**
- [lista de termeni specifici pentru acest proiect]

**Avoid:**
- [ce să evite în prompturi]

**Consistency rules:**
- [reguli pentru consistență vizuală]
```

### Step 5: Autonomous Decisions for Secondary Elements

**For icons and decorations, decide autonomously based on chosen hero style:**

| Hero Style | Icon Style | Decoration Style |
|------------|------------|------------------|
| 3D Realistic | 3D isometric icons | Floating 3D shapes, glass morphism |
| Illustrated | Matching illustration style | Hand-drawn elements, organic shapes |
| Photographic | Photo-realistic objects | Subtle gradients, minimal shapes |
| Abstract | Geometric icons | Pattern-based, mathematical |

**Document these decisions in visual-concepts.md without asking user.**

---

## Quality Checklist

Before completing, verify:

- [ ] All input docs were read (brainstorm, design-dna, copy-sections, implementation-plan)
- [ ] Visual concepts align with design-dna mood and colors
- [ ] User confirmed concept for Hero section
- [ ] User confirmed concept for Benefits section
- [ ] User confirmed concept for Social Proof section
- [ ] User confirmed concept for CTA section
- [ ] Each section has: metaphor, composition, rendering style
- [ ] All necessary images are listed with IDs
- [ ] Background types specified (transparent/keep)
- [ ] Hex color codes referenced from design-dna
- [ ] Composition notes included for image-prompts skill

---

## Completion

After creating visual-concepts.md:

1. Confirm file created at `[project-folder]/docs/visual-concepts.md`
2. Report to orchestrator: "Step 5 complete - Visual concepts created"
3. Summary:
   - Hero concept: [chosen concept name]
   - Benefits style: [chosen style]
   - Total images needed: [count]
   - Ready for image-prompts step

---

*Generated by lp-visual-concepts skill*
