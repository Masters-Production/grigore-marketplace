---
name: lp-image-prompts
description: Step 6 of landing page creation - identify visual needs for each section and generate optimized image prompts based on design-dna style
---

# Landing Page Image Prompts

You are creating optimized image generation prompts for the landing page. Analyze all documentation, identify visual needs for each section, and generate prompts that align with the design system.

## CRITICAL RULES

1. **Read ALL docs first** - brainstorm-brief, design-dna, copy-sections, implementation-plan
2. **Design-DNA drives style** - All prompts must reflect the established visual style
3. **Visual concepts drive prompts** - Read visual-concepts.md for all image decisions
4. **Optimized prompts** - Write prompts that produce consistent, high-quality images
5. **Complete JSON structure** - Output `[project-folder]/docs/image-prompts.json` with all fields
6. **No placeholder assumptions** - Use exact specifications from visual-concepts.md

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
Read and understand:
- `[project-folder]/docs/brainstorm-brief.md` - Project context and audience
- `[project-folder]/docs/design-dna.md` - Visual style, colors, mood
- `[project-folder]/docs/copy-sections.md` - Text content for context
- `[project-folder]/docs/implementation-plan.md` - Sections and structure
- `[project-folder]/docs/visual-concepts.md` - **PRIMARY INPUT** - Visual concepts, metaphors, compositions

### Output Files
- `[project-folder]/docs/image-prompts.json` - Complete image generation specifications

## Image Prompt Generation Process

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

### Step 2: Extract Style Context

From design-dna.md, build the style context:

```json
{
  "style_context": {
    "colors": ["#hex1", "#hex2", "#hex3"],
    "mood": "professional, modern, trustworthy",
    "brand_style": "minimalist with bold accents",
    "visual_elements": ["geometric shapes", "subtle gradients"]
  }
}
```

### Step 3: Identify Visual Needs Per Section

Map each section from implementation-plan.md to potential visual needs:

| Section | Common Visual Needs |
|---------|---------------------|
| Hero | Background image/gradient, hero illustration, product mockup |
| Problem/Solution | Icons, illustrations showing pain/solution |
| Benefits | Icons for each benefit, supporting illustrations |
| Social Proof | Avatar placeholders, company logos, quote decorations |
| FAQ | Decorative icons, section dividers |
| Final CTA | Background pattern, decorative elements |
| Footer | Logo, social icons |

### Step 4: Map Images from Visual Concepts

**DO NOT ask the user what images they want - this was already decided in visual-concepts.md**

Read the "Imagini necesare" sections from visual-concepts.md and create a prompt for each listed image.

For each image entry:
1. Find its ID (e.g., `hero-main`, `icon-benefit-1`)
2. Read its description and section
3. Find the composition and rendering specs from that section
4. Generate the technical prompt

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

### Step 6: Determine Sizes and Formats

| Type | Recommended Size | Format | Background |
|------|------------------|--------|------------|
| Hero background | 1920x1080 | webp | keep |
| Hero illustration | 800x600 | webp | transparent |
| Benefit icons | 256x256 | png | transparent |
| Stickers/decorations | 512x512 | png | transparent |
| Section dividers | 1920x200 | png | transparent |
| Avatars | 128x128 | webp | keep |

### Step 7: Assign Priorities

| Priority | When to Use |
|----------|-------------|
| high | Hero visuals, main illustrations (generate first) |
| medium | Benefit icons, decorations (generate second) |
| low | Optional elements, alternatives (generate if time permits) |

## Output Artifact

Create `[project-folder]/docs/image-prompts.json`:

```json
{
  "project": "[project-name]",
  "generated_at": "[ISO timestamp]",
  "style_context": {
    "colors": ["#primary", "#secondary", "#accent"],
    "mood": "description from design-dna",
    "brand_style": "visual style summary"
  },
  "images": [
    {
      "id": "hero-background",
      "type": "hero",
      "prompt": "Abstract gradient mesh background with flowing organic shapes, deep navy blue (#1a2744) transitioning to soft teal (#4fd1c5) accents, modern minimalist style, clean professional aesthetic, subtle noise texture, high resolution",
      "negative_prompt": "text, watermark, logo, blurry, low quality, distorted, ugly",
      "size": "1920x1080",
      "format": "webp",
      "background": "keep",
      "output_path": "assets/images/hero-bg.webp",
      "section_target": "hero",
      "priority": "high"
    },
    {
      "id": "icon-speed",
      "type": "icon",
      "prompt": "Simple flat icon representing speed and efficiency, lightning bolt design, coral color (#ff6b6b), modern minimalist style, clean edges, centered",
      "negative_prompt": "text, complex details, gradients, shadows, 3D",
      "size": "256x256",
      "format": "png",
      "background": "transparent",
      "output_path": "assets/images/icon-speed.png",
      "section_target": "benefits",
      "priority": "medium"
    },
    {
      "id": "icon-security",
      "type": "icon",
      "prompt": "Simple flat icon representing security and protection, shield with checkmark, teal color (#4fd1c5), modern minimalist style, clean edges, centered",
      "negative_prompt": "text, complex details, gradients, shadows, 3D",
      "size": "256x256",
      "format": "png",
      "background": "transparent",
      "output_path": "assets/images/icon-security.png",
      "section_target": "benefits",
      "priority": "medium"
    },
    {
      "id": "decoration-blob-1",
      "type": "decoration",
      "prompt": "Abstract organic blob shape, soft gradient, glass morphism effect, subtle transparency, floating 3D appearance",
      "negative_prompt": "text, sharp edges, solid colors, realistic",
      "size": "512x512",
      "format": "png",
      "background": "transparent",
      "output_path": "assets/images/blob-decoration-1.png",
      "section_target": "hero",
      "priority": "low"
    }
  ]
}
```

## JSON Field Reference

| Field | Description | Values |
|-------|-------------|--------|
| `id` | Unique identifier | kebab-case string |
| `type` | Category of image | `hero`, `icon`, `illustration`, `sticker`, `decoration`, `avatar`, `divider` |
| `prompt` | Generation prompt | Detailed, style-consistent string |
| `negative_prompt` | What to avoid | Common artifacts to exclude |
| `size` | Dimensions | `WIDTHxHEIGHT` (e.g., `1920x1080`) |
| `format` | Output format | `webp` or `png` |
| `background` | Background handling | `keep`, `transparent`, `cutout` |
| `output_path` | Relative save path | `assets/images/filename.ext` |
| `section_target` | Where it's used | Section name from implementation-plan |
| `priority` | Generation order | `high`, `medium`, `low` |

## Quality Checklist

Before completing, verify:
- [ ] All docs were read (brainstorm, design-dna, copy-sections, implementation-plan)
- [ ] Style context extracted from design-dna
- [ ] All images from visual-concepts.md mapped to prompts
- [ ] Prompts include specific color hex codes from design-dna
- [ ] Prompts include mood/style keywords from design-dna
- [ ] All prompts have negative_prompt to avoid artifacts
- [ ] Sizes are appropriate for intended use
- [ ] Priorities are assigned logically
- [ ] Output paths follow convention (assets/images/)
- [ ] JSON is valid and complete

## Prompt Writing Best Practices

### DO:
- Include specific hex colors from design-dna
- Reference the mood and style from design-dna
- Use clear, descriptive subject matter
- Include technical quality terms (high resolution, clean edges)
- Keep prompts focused and concise
- Match the visual style across all prompts

### DON'T:
- Use vague terms like "nice" or "beautiful"
- Include conflicting style directions
- Forget negative prompts
- Mix incompatible styles in one project
- Use colors not in the design-dna palette

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

## Completion

After creating the artifact:
1. Confirm image-prompts.json was created
2. Verify JSON is valid (parseable)
3. Count total images by priority: `[X] high, [Y] medium, [Z] low`
4. Report to orchestrator: "Step 6 complete - Image prompts created"
5. Provide path: `[project-folder]/docs/image-prompts.json`
6. Summary of images:
   - Hero visuals: [list]
   - Icons: [count]
   - Decorations: [count]
   - Other: [count]

---
*Generated by lp-image-prompts skill*
