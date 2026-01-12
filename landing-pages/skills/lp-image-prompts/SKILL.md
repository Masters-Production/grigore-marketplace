---
name: lp-image-prompts
description: Step 5 of landing page creation - identify visual needs for each section and generate optimized image prompts based on design-dna style
---

# Landing Page Image Prompts

You are creating optimized image generation prompts for the landing page. Analyze all documentation, identify visual needs for each section, and generate prompts that align with the design system.

## CRITICAL RULES

1. **Read ALL docs first** - brainstorm-brief, design-dna, copy-sections, implementation-plan
2. **Design-DNA drives style** - All prompts must reflect the established visual style
3. **User confirms each section** - Use AskUserQuestion for visual needs per section
4. **Optimized prompts** - Write prompts that produce consistent, high-quality images
5. **Complete JSON structure** - Output `[project-folder]/docs/image-prompts.json` with all fields
6. **No placeholder assumptions** - Ask user what images they actually want

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
Read and understand:
- `[project-folder]/docs/brainstorm-brief.md` - Project context and audience
- `[project-folder]/docs/design-dna.md` - Visual style, colors, mood
- `[project-folder]/docs/copy-sections.md` - Text content for context
- `[project-folder]/docs/implementation-plan.md` - Sections and structure

### Output Files
- `[project-folder]/docs/image-prompts.json` - Complete image generation specifications

## Image Prompt Generation Process

### Step 1: Read All Documentation

Read all docs from `[project-folder]/docs/`:

```
1. brainstorm-brief.md - Understand audience, product, tone
2. design-dna.md - Extract:
   - Color palette (primary, secondary, accent)
   - Mood/atmosphere (modern, playful, professional, etc.)
   - Visual style (minimalist, bold, organic, etc.)
   - Any specified visual elements
3. copy-sections.md - Understand content for each section
4. implementation-plan.md - Map sections that need visuals
```

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

### Step 4: Confirm Visual Needs with User

**For Hero Section:**
```
Use AskUserQuestion:
Question: "What visual element should the hero section have?"
Header: "Hero Visual"
Options:
- label: "Abstract background"
  description: "Gradient mesh, geometric patterns, or abstract shapes"
- label: "Product illustration"
  description: "Stylized illustration of the product/service"
- label: "Hero image with person"
  description: "Photo-realistic or illustrated person using product"
- label: "3D elements"
  description: "3D rendered objects or floating elements"
- label: "No image needed"
  description: "Hero will use CSS gradients/patterns only"
```

**For Benefits Section:**
```
Use AskUserQuestion:
Question: "What style of icons for the benefits section?"
Header: "Benefit Icons"
Options:
- label: "Flat icons"
  description: "Simple, modern flat design icons"
- label: "Outlined icons"
  description: "Line-art style icons with consistent stroke"
- label: "3D icons"
  description: "Subtle 3D depth and shadows"
- label: "Illustrated icons"
  description: "Custom illustrated icons matching brand style"
- label: "Skip icons"
  description: "Use icon library instead (Lucide, Phosphor, etc.)"
```

**For Social Proof Section:**
```
Use AskUserQuestion:
Question: "What visuals for the social proof section?"
Header: "Social Proof Visuals"
Options:
- label: "Avatar placeholders"
  description: "Generate placeholder avatars for testimonials"
- label: "Company logos"
  description: "I'll provide real logos - skip generation"
- label: "Decorative quotes"
  description: "Stylized quotation mark graphics"
- label: "Minimal/None"
  description: "Text-only testimonials"
```

**For Decorative Elements:**
```
Use AskUserQuestion:
Question: "Do you want decorative stickers or floating elements?"
Header: "Decorative Elements"
Options:
- label: "Floating shapes"
  description: "Abstract geometric shapes scattered on page"
- label: "Section dividers"
  description: "Custom wave/angle dividers between sections"
- label: "Background patterns"
  description: "Subtle repeating patterns for sections"
- label: "No decorations"
  description: "Keep it clean and minimal"
```

### Step 5: Generate Optimized Prompts

For each confirmed image, create an optimized prompt following this structure:

**Prompt Template:**
```
[Subject/Content], [Style descriptors from design-dna],
[Color references], [Technical specifications],
high quality, professional, [mood from design-dna]
```

**Negative Prompt Template:**
```
text, watermark, logo, signature, blurry, low quality,
distorted, deformed, ugly, duplicate, out of frame
```

**Example Prompts by Type:**

**Hero Background:**
```
"prompt": "Abstract gradient mesh background with flowing organic shapes,
deep navy blue (#1a2744) transitioning to soft teal (#4fd1c5) accents,
modern minimalist style, clean professional aesthetic,
subtle noise texture, high resolution, 4k quality"
```

**Benefit Icon:**
```
"prompt": "Simple flat icon representing speed and efficiency,
lightning bolt with circular motion lines,
coral accent color (#ff6b6b) on transparent background,
modern minimalist style, consistent 4px stroke weight,
centered composition, clean edges"
```

**Illustration:**
```
"prompt": "Isometric illustration of a person working on laptop,
floating productivity elements around them,
color palette: navy (#1a2744), teal (#4fd1c5), coral (#ff6b6b),
modern flat illustration style, subtle shadows,
professional business context, friendly approachable mood"
```

**Sticker/Decoration:**
```
"prompt": "Abstract geometric blob shape, organic flowing form,
soft gradient from purple (#7c3aed) to pink (#ec4899),
glass morphism effect, subtle blur,
transparent PNG, floating 3D appearance"
```

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
- [ ] User confirmed visual needs for each major section
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
- `[project-folder]/docs/design-dna.md` - Visual style guide
- `[project-folder]/docs/copy-sections.md` - Content context
- `[project-folder]/docs/implementation-plan.md` - Section structure

### To Next Steps
- `[project-folder]/docs/image-prompts.json` - Input for lp-image-generation
- Style context passed to ensure visual consistency

## Completion

After creating the artifact:
1. Confirm image-prompts.json was created
2. Verify JSON is valid (parseable)
3. Count total images by priority: `[X] high, [Y] medium, [Z] low`
4. Report to orchestrator: "Step 5 complete - Image prompts created"
5. Provide path: `[project-folder]/docs/image-prompts.json`
6. Summary of images:
   - Hero visuals: [list]
   - Icons: [count]
   - Decorations: [count]
   - Other: [count]

---
*Generated by lp-image-prompts skill*
