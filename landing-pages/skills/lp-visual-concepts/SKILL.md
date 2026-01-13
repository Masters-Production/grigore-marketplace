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
