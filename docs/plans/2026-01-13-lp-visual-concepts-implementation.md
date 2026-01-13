# lp-visual-concepts Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Add visual concept thinking between Planning and Image Prompts in landing-pages workflow.

**Architecture:** New skill `lp-visual-concepts` proposes 2-3 visual concepts per section (metaphors, composition, rendering style), user confirms, outputs `visual-concepts.md`. Then `lp-image-prompts` reads this to generate advanced prompts.

**Tech Stack:** Markdown skills, AskUserQuestion interactions, JSON outputs

---

## Task 1: Create lp-visual-concepts Skill Directory

**Files:**
- Create: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Create skill directory**

```bash
mkdir "landing-pages/skills/lp-visual-concepts"
```

**Step 2: Verify directory exists**

```bash
ls landing-pages/skills/ | grep visual-concepts
```
Expected: `lp-visual-concepts` in output

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts
git commit -m "chore: create lp-visual-concepts skill directory"
```

---

## Task 2: Write lp-visual-concepts SKILL.md (Part 1 - Header & Rules)

**Files:**
- Create: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Write skill header and critical rules**

Write to `landing-pages/skills/lp-visual-concepts/SKILL.md`:

```markdown
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
```

**Step 2: Verify file created**

Read file and confirm header exists with correct name.

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts/SKILL.md
git commit -m "feat(lp-visual-concepts): add skill header and rules"
```

---

## Task 3: Write lp-visual-concepts SKILL.md (Part 2 - Process Steps 1-2)

**Files:**
- Modify: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Add process steps 1-2**

Append to `landing-pages/skills/lp-visual-concepts/SKILL.md`:

```markdown

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
```

**Step 2: Verify content appended**

Read file and confirm Steps 1-2 exist.

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts/SKILL.md
git commit -m "feat(lp-visual-concepts): add process steps 1-2"
```

---

## Task 4: Write lp-visual-concepts SKILL.md (Part 3 - Concept Proposal)

**Files:**
- Modify: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Add concept proposal section**

Append to `landing-pages/skills/lp-visual-concepts/SKILL.md`:

```markdown

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
```

**Step 2: Verify content appended**

Read file and confirm Step 3 exists with all section proposals.

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts/SKILL.md
git commit -m "feat(lp-visual-concepts): add concept proposal templates"
```

---

## Task 5: Write lp-visual-concepts SKILL.md (Part 4 - Documentation Format)

**Files:**
- Modify: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Add documentation format section**

Append to `landing-pages/skills/lp-visual-concepts/SKILL.md`:

```markdown

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
```

**Step 2: Verify content appended**

Read file and confirm Step 4 exists with complete template.

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts/SKILL.md
git commit -m "feat(lp-visual-concepts): add documentation format and templates"
```

---

## Task 6: Write lp-visual-concepts SKILL.md (Part 5 - Completion & Checklist)

**Files:**
- Modify: `landing-pages/skills/lp-visual-concepts/SKILL.md`

**Step 1: Add completion section**

Append to `landing-pages/skills/lp-visual-concepts/SKILL.md`:

```markdown

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
```

**Step 2: Verify complete skill file**

Read entire file and verify all 5 steps exist.

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-visual-concepts/SKILL.md
git commit -m "feat(lp-visual-concepts): add completion checklist and summary"
```

---

## Task 7: Update lp-orchestrator - Add Step 5 Visual Concepts

**Files:**
- Modify: `landing-pages/skills/lp-orchestrator/SKILL.md`

**Step 1: Update Required Sub-Skills table**

Find the "Required Sub-Skills" table in `lp-orchestrator/SKILL.md` and replace with:

```markdown
## Required Sub-Skills

| Step | Skill | Execution |
|------|-------|-----------|
| 1 | `landing-pages:lp-brainstorming` | Direct (no subagent) |
| 2 | `landing-pages:lp-design-dna` | **Subagent** |
| 3 | `landing-pages:lp-text-composing` | **Subagent** |
| 4 | `landing-pages:lp-planning` | **Subagent** |
| 5 | `landing-pages:lp-visual-concepts` | **Subagent** |
| 6 | `landing-pages:lp-image-prompts` | **Subagent** |
| 7 | `landing-pages:lp-image-generation` | **Subagent** |
| 8 | `landing-pages:lp-image-integration` | **Subagent** |
| 9 | `landing-pages:lp-building` | **Subagent** (nested subagents inside) |
| 10 | `landing-pages:lp-qa-review` | **Subagent** |
| 11 | `superpowers:finishing-a-development-branch` | **Subagent** |
```

**Step 2: Update Workflow Sequence diagram**

Find the "Workflow Sequence" section and replace with:

```markdown
## Workflow Sequence

```
Step 0: Project Setup → Create [project-folder]/, [project-folder]/docs/, [project-folder]/assets/images/
    ↓
Step 1: lp-brainstorming → [project-folder]/docs/brainstorm-brief.md
    ↓
Step 2: lp-design-dna → [project-folder]/docs/design-dna.md
    ↓
Step 3: lp-text-composing → [project-folder]/docs/copy-sections.md
    ↓
Step 4: lp-planning → [project-folder]/docs/implementation-plan.md
    ↓
Step 5: lp-visual-concepts → [project-folder]/docs/visual-concepts.md
    ↓
Step 6: lp-image-prompts → [project-folder]/docs/image-prompts.json
    ↓
Step 7: lp-image-generation → [project-folder]/assets/images/*.webp
    ↓
Step 8: lp-image-integration → [project-folder]/docs/implementation-plan.md (updated)
    ↓
Step 9: lp-building → [project-folder]/index.html, style.css, script.js
    ↓
Step 10: lp-qa-review → [project-folder]/docs/qa-report.md (score >= 80)
    ↓
Step 11: finishing-a-development-branch → Complete
```
```

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-orchestrator/SKILL.md
git commit -m "feat(lp-orchestrator): update workflow to include visual-concepts step"
```

---

## Task 8: Update lp-orchestrator - Add Step 5 Dispatch Block

**Files:**
- Modify: `landing-pages/skills/lp-orchestrator/SKILL.md`

**Step 1: Add Step 5 Visual Concepts dispatch block**

After Step 4 (Planning) dispatch block, add:

```markdown
---

**Step 5: Visual Concepts** _(Dispatch subagent)_

1. Mark TodoWrite: Step 5 = in_progress
2. Dispatch subagent:
```
Task tool:
  subagent_type: "general-purpose"
  description: "Execute visual-concepts step"
  prompt: |
    ## Landing Page Workflow - Step 5: Visual Concepts

    SKILL TO USE: landing-pages:lp-visual-concepts
    PROJECT FOLDER: [project-folder]

    Input: Read ALL docs in [project-folder]/docs/:
    - brainstorm-brief.md
    - design-dna.md
    - copy-sections.md
    - implementation-plan.md

    Follow the skill instructions to create visual concepts.
    Think like a creative director - propose metaphors, compositions, rendering styles.
    Use AskUserQuestion to confirm concept for each major section.

    Output: [project-folder]/docs/visual-concepts.md

    When complete, confirm artifact was created with:
    - Hero concept chosen
    - Benefits style chosen
    - Total images needed
```
3. Verify artifact exists: `[project-folder]/docs/visual-concepts.md`
4. Mark TodoWrite: Step 5 = completed
```

**Step 2: Renumber all subsequent steps (6-11)**

Update all step numbers in the orchestrator:
- "Step 5: Image Prompts" → "Step 6: Image Prompts"
- "Step 6: Image Generation" → "Step 7: Image Generation"
- "Step 7: Image Integration" → "Step 8: Image Integration"
- "Step 8: Building" → "Step 9: Building"
- "Step 9: QA Review" → "Step 10: QA Review"
- "Step 10: Finish" → "Step 11: Finish"

**Step 3: Update TodoWrite section in Part C**

Replace TodoWrite todos list with:

```markdown
TodoWrite todos:
- Step 0: Project Setup - COMPLETED
- Step 1: Brainstorming - pending
- Step 2: Design DNA - pending
- Step 3: Text Composing - pending
- Step 4: Planning - pending
- Step 5: Visual Concepts - pending
- Step 6: Image Prompts - pending
- Step 7: Image Generation - pending
- Step 8: Image Integration - pending
- Step 9: Building - pending
- Step 10: QA Review - pending
- Step 11: Finish Development - pending
```

**Step 4: Commit**

```bash
git add landing-pages/skills/lp-orchestrator/SKILL.md
git commit -m "feat(lp-orchestrator): add Step 5 dispatch and renumber steps 6-11"
```

---

## Task 9: Update lp-image-prompts - Read visual-concepts.md

**Files:**
- Modify: `landing-pages/skills/lp-image-prompts/SKILL.md`

**Step 1: Update Input Files section**

Find "Input Files" section and replace with:

```markdown
### Input Files
Read and understand:
- `[project-folder]/docs/brainstorm-brief.md` - Project context and audience
- `[project-folder]/docs/design-dna.md` - Visual style, colors, mood
- `[project-folder]/docs/copy-sections.md` - Text content for context
- `[project-folder]/docs/implementation-plan.md` - Sections and structure
- `[project-folder]/docs/visual-concepts.md` - **PRIMARY INPUT** - Visual concepts, metaphors, compositions
```

**Step 2: Update Step 1 (Read All Documentation)**

Replace Step 1 with:

```markdown
### Step 1: Read All Documentation

Read all docs from `[project-folder]/docs/`:

```
1. visual-concepts.md - **PRIMARY** - Contains:
   - Visual metaphors per section
   - Composition specifications (layering, positioning)
   - Rendering style (materials, lighting, effects)
   - List of images needed with IDs

2. design-dna.md - Extract:
   - Color palette (exact hex codes)
   - Mood/atmosphere
   - Visual style keywords

3. brainstorm-brief.md - Context for:
   - Target audience
   - Tone and messaging

4. copy-sections.md - Reference for:
   - Headlines that need visual support
   - Section order

5. implementation-plan.md - Map:
   - Section structure
   - Image placement needs
```

**IMPORTANT:** `visual-concepts.md` is now the primary input. It already contains:
- What images are needed
- What metaphors to use
- How to compose each image
- What rendering style to apply

Your job is to transform these concepts into optimized generation prompts.
```

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-image-prompts/SKILL.md
git commit -m "feat(lp-image-prompts): add visual-concepts.md as primary input"
```

---

## Task 10: Update lp-image-prompts - Enhanced Prompt Generation

**Files:**
- Modify: `landing-pages/skills/lp-image-prompts/SKILL.md`

**Step 1: Update prompt generation section**

Find "Step 5: Generate Optimized Prompts" and replace with:

```markdown
### Step 5: Generate Optimized Prompts from Visual Concepts

**Transform visual-concepts.md specifications into technical prompts.**

For each image in visual-concepts.md:

1. **Read the concept specification:**
   - Metaphor (what it represents)
   - Composition (positioning, layering)
   - Rendering style (materials, lighting, effects)

2. **Build the prompt with technical terms:**

**Prompt Structure:**
```
[Subject from metaphor], [specific positioning from composition],
[material/texture from rendering], [lighting setup],
[effects: blur, bloom, reflection], [color references with hex],
[quality terms: high resolution, 8k, professional],
[style: octane render, studio photography, digital illustration]
```

**Example Transformation:**

Visual Concept Input:
```
Metaphor: Rocket = growth
Composition: 3D rocket at 15° angle, exits frame bottom, text behind
Rendering: Chrome metallic, rim lighting, motion blur on exhaust
Colors: Primary (#1a2744), Accent (#ff6b6b)
```

Generated Prompt:
```
"3D rocket launching at 15 degree angle tilted right, chrome metallic body
with subtle scratches and reflections, navy blue (#1a2744) primary color,
coral (#ff6b6b) flames and exhaust, positioned lower third of frame
exiting bottom edge, strong rim lighting from upper right, motion blur
on exhaust particles, transparent background, octane render quality,
studio lighting setup, 8k resolution, professional product photography style"
```

**Rendering Term Reference:**

| Visual Concept Term | Prompt Terms to Add |
|---------------------|---------------------|
| 3D realistic | octane render, 8k, photorealistic, studio lighting |
| Chrome/metallic | chrome material, reflective surface, subtle scratches |
| Marble | marble texture with veins, polished surface |
| Glass | glass material, refraction, caustics, transparency |
| Motion blur | motion blur, speed lines, dynamic movement |
| Bloom effect | bloom, glow, light bleeding, soft highlights |
| Rim lighting | rim light, backlight, edge lighting, silhouette glow |
| Depth blur | depth of field, bokeh, background blur, tilt-shift |
| Floating | levitating, zero gravity, suspended in air |
| Isometric | isometric perspective, 30 degree angle, no perspective distortion |

**Composition Term Reference:**

| Visual Concept Term | Prompt Terms to Add |
|---------------------|---------------------|
| Exits frame | cropped at edge, extends beyond frame, partial view |
| Text behind | layered composition, negative space for text |
| Central | centered composition, symmetrical |
| Lower third | positioned in lower third, rule of thirds |
| Tilted X° | rotated X degrees, angled, dynamic pose |
| Foreground/background | depth layers, foreground element, background separation |
```

**Step 2: Remove user questions (already decided in visual-concepts)**

Find "Step 4: Confirm Visual Needs with User" and replace with:

```markdown
### Step 4: Map Images from Visual Concepts

**DO NOT ask the user what images they want - this was already decided in visual-concepts.md**

Read the "Imagini necesare" sections from visual-concepts.md and create a prompt for each listed image.

For each image entry:
1. Find its ID (e.g., `hero-main`, `icon-benefit-1`)
2. Read its description and section
3. Find the composition and rendering specs from that section
4. Generate the technical prompt
```

**Step 3: Commit**

```bash
git add landing-pages/skills/lp-image-prompts/SKILL.md
git commit -m "feat(lp-image-prompts): enhanced prompt generation from visual concepts"
```

---

## Task 11: Update lp-image-prompts - Integration Points

**Files:**
- Modify: `landing-pages/skills/lp-image-prompts/SKILL.md`

**Step 1: Update Integration Points section**

Find "Integration Points" section and replace with:

```markdown
## Integration Points

### From Previous Steps
- `[project-folder]/docs/brainstorm-brief.md` - Project context
- `[project-folder]/docs/design-dna.md` - Colors, mood, style keywords
- `[project-folder]/docs/copy-sections.md` - Content context
- `[project-folder]/docs/implementation-plan.md` - Section structure
- `[project-folder]/docs/visual-concepts.md` - **PRIMARY** - Concepts, compositions, rendering specs

### To Next Steps
- `[project-folder]/docs/image-prompts.json` - Input for lp-image-generation
- Prompts contain technical rendering terms from visual-concepts transformation

### Dependency Chain
```
visual-concepts.md (concepts)
    → image-prompts.json (technical prompts)
        → image-generation (actual images)
            → image-integration (into implementation-plan)
```

### What Changed from Previous Workflow
- **Before:** image-prompts asked user what images they wanted
- **After:** image-prompts reads visual-concepts.md which already has decisions
- **Before:** Prompts were basic ("blue gradient background")
- **After:** Prompts include technical rendering terms ("octane render, rim lighting, 8k")
```

**Step 2: Commit**

```bash
git add landing-pages/skills/lp-image-prompts/SKILL.md
git commit -m "feat(lp-image-prompts): update integration points for visual-concepts flow"
```

---

## Task 12: Final Verification

**Step 1: Verify all files exist and are valid**

```bash
# Check new skill exists
cat landing-pages/skills/lp-visual-concepts/SKILL.md | head -20

# Check orchestrator has Step 5
grep -n "Step 5: Visual Concepts" landing-pages/skills/lp-orchestrator/SKILL.md

# Check image-prompts reads visual-concepts
grep -n "visual-concepts.md" landing-pages/skills/lp-image-prompts/SKILL.md
```

Expected:
- lp-visual-concepts/SKILL.md exists with header
- Orchestrator mentions "Step 5: Visual Concepts"
- image-prompts mentions "visual-concepts.md"

**Step 2: Run git status to confirm all committed**

```bash
git status
git log --oneline -10
```

Expected: Clean working tree, commits visible

**Step 3: Final commit message**

```bash
git log --oneline -10
```

Should show commits:
1. chore: create lp-visual-concepts skill directory
2. feat(lp-visual-concepts): add skill header and rules
3. feat(lp-visual-concepts): add process steps 1-2
4. feat(lp-visual-concepts): add concept proposal templates
5. feat(lp-visual-concepts): add documentation format and templates
6. feat(lp-visual-concepts): add completion checklist and summary
7. feat(lp-orchestrator): update workflow to include visual-concepts step
8. feat(lp-orchestrator): add Step 5 dispatch and renumber steps 6-11
9. feat(lp-image-prompts): add visual-concepts.md as primary input
10. feat(lp-image-prompts): enhanced prompt generation from visual concepts
11. feat(lp-image-prompts): update integration points for visual-concepts flow

---

## Summary

**Created:**
- `landing-pages/skills/lp-visual-concepts/SKILL.md` - New skill for visual concept generation

**Modified:**
- `landing-pages/skills/lp-orchestrator/SKILL.md` - Added Step 5, renumbered 6-11
- `landing-pages/skills/lp-image-prompts/SKILL.md` - Reads visual-concepts.md, enhanced prompts

**Workflow Change:**
```
Before: Planning → Image Prompts → Generation
After:  Planning → Visual Concepts → Image Prompts → Generation
```

---

*Implementation plan created: 2026-01-13*
