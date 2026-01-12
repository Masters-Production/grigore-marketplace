---
name: lp-image-integration
description: Step 7 of landing page creation - integrate generated images into the implementation plan by visually verifying each asset and updating task instructions with concrete image paths
---

# Landing Page Image Integration

You are integrating generated images into the implementation plan. You must visually verify each image exists and is appropriate, then update the implementation plan with concrete image paths for each section.

## CRITICAL RULES

1. **Read image-prompts.json first** - Know what images should exist
2. **Verify assets exist** - Check assets/images/ folder for actual files
3. **Visually analyze each image** - Use Read tool to SEE each image
4. **Update implementation-plan.md** - Add Available Assets section and per-task image references
5. **Report integration results** - List what was integrated and what's missing

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
- `[project-folder]/docs/image-prompts.json` - Expected images specification
- `[project-folder]/assets/images/` - Generated image files
- `[project-folder]/docs/implementation-plan.md` - Current plan without image references

### Output Files
- `[project-folder]/docs/implementation-plan.md` - Updated with image references

## Integration Process

### Step 1: Read Image Specification

Load `[project-folder]/docs/image-prompts.json` to understand:
- What images should have been generated
- Expected filenames and paths
- Which section each image targets
- Image types (hero, icon, illustration, sticker, decoration)

```json
// Expected structure from image-prompts.json
{
  "project": "landing-page-name",
  "images": [
    {
      "id": "hero-background",
      "type": "hero",
      "output_path": "assets/images/hero-bg.webp",
      "section_target": "hero",
      "size": "1920x1080"
    }
  ]
}
```

### Step 2: Verify Generated Assets

Check what actually exists in `[project-folder]/assets/images/`:

```
Use Glob tool:
pattern: "**/*.{webp,png,jpg,jpeg,svg}"
path: [project-folder]/assets/images/
```

Create a mapping:
- Expected files (from JSON) vs Actual files (from folder)
- Mark each as: EXISTS | MISSING

### Step 3: Visually Analyze Each Image

**CRITICAL: You MUST use the Read tool to visually inspect each image.**

For each existing image:
```
Use Read tool:
file_path: [project-folder]/assets/images/[filename]
```

Document for each image:
- **Filename**: The actual file
- **Visual Description**: What you see in the image
- **Quality Assessment**: Good | Acceptable | Needs Replacement
- **Suitability**: How well it matches the intended purpose
- **Usage Recommendations**: Position, CSS treatment, etc.

### Step 4: Build Available Assets Table

Create the assets inventory table:

```markdown
## Available Assets

Generated images in `assets/images/`:

| File | Type | Size | For Section | Status | Notes |
|------|------|------|-------------|--------|-------|
| hero-bg.webp | background | 1920x1080 | Hero | Ready | Gradient mesh, matches design |
| icon-speed.webp | icon | 256x256 | Benefits | Ready | Transparent background |
| feature-illustration.webp | illustration | 800x600 | Features | Ready | Abstract shapes |
| sticker-badge.webp | sticker | 200x200 | Hero | Ready | "New" badge, cutout |

### Missing Assets

The following images from image-prompts.json were not found:
- `icon-security.webp` - For Benefits section
- `footer-pattern.webp` - For Footer section

**Recommendation:** These missing assets should be generated or placeholders used.
```

### Step 5: Update Implementation Plan Tasks

For EACH task in implementation-plan.md that uses images, add an "Images to use" subsection.

**Before (original task):**
```markdown
### Task 4: Hero Section

**Goal:** Build hero section with headline, subheadline, CTA
...
```

**After (with image integration):**
```markdown
### Task 4: Hero Section

**Goal:** Build hero section with headline, subheadline, CTA

**Images to use:**
- Background: `assets/images/hero-bg.webp`
  - Usage: Full-width background with `background-size: cover`
  - Position: `center center`
  - Notes: Apply slight overlay for text contrast
- Decoration: `assets/images/hero-decoration.webp`
  - Usage: Absolute positioned element
  - Position: bottom-right, 30% width
  - Notes: Use `mix-blend-mode: multiply` for blending

...rest of task...
```

### Step 6: Image Usage Patterns

Provide specific CSS/HTML guidance for each image type:

**Hero Backgrounds:**
```markdown
**Images to use:**
- Background: `assets/images/hero-bg.webp`
  - CSS: `background: url('../assets/images/hero-bg.webp') center/cover no-repeat`
  - Fallback: Use gradient from design-dna as fallback
  - Overlay: Semi-transparent overlay if text contrast needed
```

**Icons:**
```markdown
**Images to use:**
- Icon: `assets/images/icon-speed.webp`
  - Element: `<img src="assets/images/icon-speed.webp" alt="Speed feature">`
  - Size: 48x48px in cards, 64x64px in features
  - Notes: Has transparent background, works on any color
```

**Illustrations:**
```markdown
**Images to use:**
- Illustration: `assets/images/workflow-illustration.webp`
  - Element: `<img>` or `<figure>` depending on context
  - Responsive: `max-width: 100%; height: auto`
  - Position: Center or alongside text content
```

**Stickers/Decorations:**
```markdown
**Images to use:**
- Sticker: `assets/images/badge-new.webp`
  - Position: Absolute, top-right of parent
  - CSS: `position: absolute; top: -10px; right: -10px; width: 80px`
  - Animation: Optional subtle rotation or bounce
```

**Section Dividers/Patterns:**
```markdown
**Images to use:**
- Divider: `assets/images/wave-divider.webp`
  - Position: Between sections
  - CSS: Full-width, `width: 100%; height: auto`
  - Notes: Negative margin to overlap sections
```

## Output Artifact

Update `[project-folder]/docs/implementation-plan.md` with:

### 1. Add Available Assets Section (After Overview)

Insert after the Overview section:

```markdown
---

## Available Assets

Generated images in `assets/images/`:

| File | Type | Size | For Section | Status |
|------|------|------|-------------|--------|
| hero-bg.webp | background | 1920x1080 | Hero | Ready |
| hero-decoration.webp | decoration | 400x400 | Hero | Ready |
| icon-speed.webp | icon | 256x256 | Benefits | Ready |
| icon-security.webp | icon | 256x256 | Benefits | Ready |
| icon-simple.webp | icon | 256x256 | Benefits | Ready |
| workflow-illustration.webp | illustration | 800x600 | Features | Ready |
| wave-divider.webp | divider | 1920x200 | Section breaks | Ready |
| badge-new.webp | sticker | 200x200 | Hero | Ready |

### Asset Usage Guide

**Backgrounds:** Use with `background-size: cover` and proper fallback gradients.
**Icons:** All have transparent backgrounds. Size per context (48px cards, 64px features).
**Illustrations:** Responsive with `max-width: 100%`. Center or float as needed.
**Stickers:** Position absolute. Apply subtle animations for engagement.
**Dividers:** Full-width between sections. Use negative margins for overlap effect.

### Missing Assets

[List any images from prompts that weren't generated, or note "All assets generated successfully"]

---
```

### 2. Add Images to Each Relevant Task

For each task that should use images:

```markdown
### Task 4: Hero Section

**Goal:** Build hero section with headline, subheadline, CTA

**Images to use:**
- Background: `assets/images/hero-bg.webp`
  - CSS: `background: url('../assets/images/hero-bg.webp') center/cover no-repeat`
  - Fallback: Linear gradient from design-dna.md
- Decoration: `assets/images/hero-decoration.webp`
  - Position: bottom-right corner, absolute
  - Size: 30% of section width
  - Blend: Consider `mix-blend-mode` for integration
- Sticker: `assets/images/badge-new.webp`
  - Position: Near CTA button or headline
  - Size: 80px
  - Animation: Subtle bounce or pulse

**Files to modify:**
...
```

## Section-to-Image Mapping

Common patterns for image placement:

| Section | Image Types | Common Usage |
|---------|-------------|--------------|
| Hero | background, decoration, sticker | Full BG + corner decorations + badge |
| Benefits | icons | One icon per benefit card |
| Features | illustration, icons | Large illustration + supporting icons |
| Social Proof | avatars, logos | Testimonial photos, company logos |
| Final CTA | background, sticker | Contrasting BG + urgency badge |
| Footer | pattern, icons | Subtle pattern + social icons |

## Handling Missing Images

If images are missing:

```markdown
### Missing Assets

The following images were not generated:
| Expected File | Section | Fallback Recommendation |
|---------------|---------|------------------------|
| icon-security.webp | Benefits | Use icon library (Lucide, Phosphor) |
| footer-pattern.webp | Footer | Use CSS gradient pattern |

**Action Required:**
- [ ] Generate missing images using lp-image-generation
- [ ] OR use fallback alternatives in implementation
```

## Quality Checks

Before completing, verify:

- [ ] All images in image-prompts.json are accounted for (exists or documented as missing)
- [ ] Each existing image was visually analyzed
- [ ] Available Assets table is complete and accurate
- [ ] Every task that uses images has "Images to use" subsection
- [ ] Image paths are correct relative to HTML files
- [ ] Usage recommendations are specific and actionable
- [ ] Missing images have fallback recommendations

## Completion Report

After updating implementation-plan.md:

```markdown
## Image Integration Complete

### Summary
- **Total Expected:** [X] images
- **Generated Successfully:** [X] images
- **Missing:** [X] images

### Integrated Images

| Image | Section | Integration Status |
|-------|---------|-------------------|
| hero-bg.webp | Hero (Task 4) | Integrated with usage instructions |
| icon-speed.webp | Benefits (Task 6) | Integrated with usage instructions |
...

### Missing Images (if any)
- `[filename]` - Fallback: [recommendation]

### Updated Tasks
Tasks with image references added:
- Task 4: Hero Section
- Task 6: Benefits Section
- Task 7: Features Section
- Task 9: Final CTA Section

### Next Step
Proceed to lp-building (Step 8) - implementation plan now includes all image assets.
```

## Error Handling

### No image-prompts.json
```
Report to orchestrator:
- image-prompts.json not found
- Cannot proceed with image integration
- Recommend: Run lp-image-prompts first (Step 5)
```

### assets/images/ folder empty or missing
```
Report to orchestrator:
- No generated images found in assets/images/
- Cannot proceed with image integration
- Recommend: Run lp-image-generation first (Step 6)
```

### Image files cannot be read
```
Report to orchestrator:
- Unable to read image file: [filename]
- Possible corruption or unsupported format
- Document as "Unverified" in assets table
```

## Important Notes

- **Always READ the actual images** - Don't just check if files exist
- **Be specific with CSS/HTML guidance** - Builders need exact instructions
- **Document everything** - Missing images, quality issues, recommendations
- **Relative paths** - All paths relative to project root for HTML usage
- **Fallbacks matter** - Always provide alternatives for missing/broken images
