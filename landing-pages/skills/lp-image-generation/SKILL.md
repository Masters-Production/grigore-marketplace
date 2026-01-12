---
name: lp-image-generation
description: Step 6 of landing page creation - generate images from prompts using configured generation method (MCP tool, API, or browser automation)
---

# Landing Page Image Generation

You are generating images for the landing page based on the prompts defined in `image-prompts.json`. Process each image according to priority and save to the specified output paths.

## CRITICAL RULES

1. **Read image-prompts.json first** - All generation parameters come from this file
2. **Create output folder** - Ensure `[project-folder]/assets/images/` exists
3. **Process by priority** - high -> medium -> low
4. **Continue on failure** - If one image fails, log it and continue with next
5. **Report results** - Provide success/failure counts and details
6. **Flexible generation** - Support multiple generation methods (configurable)

## Input/Output Paths

All files are in the project folder provided by the orchestrator.

### Input Files
- `[project-folder]/docs/image-prompts.json` - Image generation specifications

### Output Files
- `[project-folder]/assets/images/*.webp` - Generated images
- `[project-folder]/docs/image-generation-report.md` - Generation results report

## Generation Methods

**IMPORTANT:** The generation method is CONFIGURABLE, not hardcoded. Check for available methods in this priority order:

### Method Priority

```
1. MCP Tool (Recommended)
   - Check if image generation MCP tool is available
   - Most reliable and integrated option

2. API Direct
   - Use configured API service (OpenAI DALL-E, Stability AI, etc.)
   - Requires API credentials in environment

3. Browser Automation
   - Use claude-in-chrome to interact with web-based generators
   - Fallback option when others unavailable
```

### Method Detection

At the start of execution, detect available methods:

```
Step 1: Check for MCP image generation tools
  - List available MCP tools
  - Look for image/generation capabilities
  - If found: Use MCP method

Step 2: If no MCP, check for API configuration
  - Check environment for API keys (OPENAI_API_KEY, STABILITY_API_KEY, etc.)
  - If found: Use API method

Step 3: If no API, check for browser automation
  - Check if claude-in-chrome is available
  - If found: Use browser method

Step 4: If nothing available
  - Report to user: "No image generation method available"
  - Ask user how to proceed
```

## Processing Flow

```
┌─────────────────────────────────────┐
│  1. Read image-prompts.json         │
│     - Parse JSON                    │
│     - Extract images array          │
│     - Get style_context             │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  2. Create output folder            │
│     mkdir [project-folder]/         │
│           assets/images/            │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  3. Detect generation method        │
│     - Check MCP tools               │
│     - Check API config              │
│     - Check browser automation      │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  4. Sort images by priority         │
│     - high (first)                  │
│     - medium (second)               │
│     - low (last)                    │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  5. For each image:                 │
│     - Log: "Generating [id]..."     │
│     - Call generation method        │
│     - Process background if needed  │
│     - Save to output_path           │
│     - Log result (success/failure)  │
│     - Continue even if failed       │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  6. Generate report                 │
│     - Success count                 │
│     - Failure count                 │
│     - Details per image             │
│     - Retry recommendations         │
└─────────────────────────────────────┘
```

## Image Prompts JSON Structure

Expected format of `[project-folder]/docs/image-prompts.json`:

```json
{
  "project": "landing-page-name",
  "style_context": {
    "colors": ["#primary", "#secondary"],
    "mood": "professional, modern",
    "brand_style": "from design-dna.md"
  },
  "images": [
    {
      "id": "hero-background",
      "type": "hero",
      "prompt": "Abstract gradient mesh background...",
      "negative_prompt": "text, watermark, low quality",
      "size": "1920x1080",
      "format": "webp",
      "background": "keep",
      "output_path": "assets/images/hero-bg.webp",
      "section_target": "hero",
      "priority": "high"
    }
  ]
}
```

### Field Definitions

| Field | Required | Description |
|-------|----------|-------------|
| `id` | Yes | Unique identifier for the image |
| `type` | Yes | Category: "hero", "icon", "illustration", "sticker", "decoration" |
| `prompt` | Yes | Generation prompt text |
| `negative_prompt` | No | What to avoid in generation |
| `size` | Yes | Dimensions (e.g., "1920x1080", "256x256") |
| `format` | Yes | Output format: "webp" or "png" |
| `background` | No | "keep", "transparent", or "cutout" |
| `output_path` | Yes | Relative path for saving |
| `section_target` | Yes | Which section uses this image |
| `priority` | Yes | "high", "medium", or "low" |

## Generation Method Details

### Option 1: MCP Tool (Recommended)

If an MCP image generation tool is available:

```
For each image:
  1. Prepare parameters from image object
  2. Call MCP tool with:
     - prompt: image.prompt
     - negative_prompt: image.negative_prompt (if supported)
     - width/height: parsed from image.size
     - format: image.format
  3. Save result to image.output_path
  4. Process background if image.background != "keep"
```

### Option 2: API Direct

If using direct API calls:

```
Supported APIs:
- OpenAI DALL-E 3
- Stability AI
- Replicate
- Custom API endpoint

For each image:
  1. Construct API request
  2. Send generation request
  3. Download result
  4. Convert to target format if needed
  5. Save to output_path
  6. Process background if needed
```

### Option 3: Browser Automation

If using claude-in-chrome:

```
Supported services:
- Midjourney (via Discord)
- Leonardo.ai
- Ideogram
- Other web-based generators

For each image:
  1. Navigate to generation service
  2. Input prompt
  3. Set parameters (size, style)
  4. Wait for generation
  5. Download result
  6. Save to output_path
  7. Process background if needed
```

## Background Processing

When `background` field is not "keep":

### transparent
Remove background, make it transparent:
```
1. Use background removal tool/API
2. Save as PNG with alpha channel
3. Convert to WebP with transparency if format is webp
```

### cutout
Remove background and crop to content:
```
1. Remove background
2. Find content bounds
3. Crop to content with small padding
4. Save result
```

## Progress Tracking

Track progress during generation:

```markdown
## Image Generation Progress

| # | ID | Priority | Status | Time |
|---|-----|----------|--------|------|
| 1 | hero-background | high | Generating... | - |
| 2 | icon-speed | high | Pending | - |
| 3 | illustration-workflow | medium | Pending | - |
```

Update after each image:

```markdown
| 1 | hero-background | high | Success | 12s |
| 2 | icon-speed | high | Failed (timeout) | - |
| 3 | illustration-workflow | medium | Generating... | - |
```

## Error Handling

### Per-Image Error Handling

```
Try:
  Generate image
  Process background
  Save to output_path
  Mark as SUCCESS

Catch Error:
  Log error details
  Mark as FAILED
  Add to retry list
  CONTINUE to next image (do NOT stop)
```

### Common Errors and Handling

| Error | Cause | Action |
|-------|-------|--------|
| Timeout | Generation took too long | Mark failed, suggest retry |
| API Error | Service unavailable | Mark failed, log error code |
| Invalid Prompt | Content policy violation | Mark failed, suggest prompt revision |
| File Save Error | Permission/path issue | Mark failed, check path |
| Format Error | Unsupported format | Convert to supported format |

### Retry Option

After completion, if any images failed:

```
Use AskUserQuestion:
Question: "[X] images failed to generate. Would you like to retry?"
Header: "Retry Failed Images"
Options:
- label: "Retry all failed"
  description: "Try generating failed images again"
- label: "Retry specific images"
  description: "I'll tell you which ones to retry"
- label: "Skip and continue"
  description: "Proceed without these images"
- label: "Use placeholders"
  description: "Create placeholder images instead"
```

## Output Report

Create `[project-folder]/docs/image-generation-report.md`:

```markdown
# Image Generation Report

> Generation report for [project name] landing page images

## Summary

| Metric | Value |
|--------|-------|
| Total Images | [X] |
| Successful | [X] |
| Failed | [X] |
| Success Rate | [X]% |
| Total Time | [X]s |
| Method Used | [MCP/API/Browser] |

## Generation Results

### Successful Images

| ID | Type | Size | Output Path | Time |
|----|------|------|-------------|------|
| hero-background | hero | 1920x1080 | assets/images/hero-bg.webp | 12s |
| icon-speed | icon | 256x256 | assets/images/icon-speed.webp | 8s |

### Failed Images

| ID | Type | Error | Retry Suggested |
|----|------|-------|-----------------|
| illustration-complex | illustration | Timeout after 60s | Yes |

## Detailed Log

### hero-background
- **Status:** Success
- **Priority:** high
- **Prompt:** "Abstract gradient mesh background..."
- **Size:** 1920x1080
- **Background:** keep
- **Output:** `assets/images/hero-bg.webp`
- **Generation Time:** 12s

### icon-speed
- **Status:** Success
- **Priority:** high
- **Prompt:** "Minimalist speed icon..."
- **Size:** 256x256
- **Background:** transparent
- **Output:** `assets/images/icon-speed.webp`
- **Generation Time:** 8s
- **Note:** Background removed successfully

### illustration-complex (FAILED)
- **Status:** Failed
- **Priority:** medium
- **Prompt:** "Detailed workflow illustration..."
- **Size:** 800x600
- **Error:** Generation timed out after 60 seconds
- **Recommendation:** Simplify prompt or increase timeout

---

## Files Created

```
[project-folder]/
└── assets/
    └── images/
        ├── hero-bg.webp (1920x1080)
        ├── icon-speed.webp (256x256)
        └── [other generated images]
```

## Next Steps

### If All Successful
- Proceed to Step 7: Image Integration
- Images ready for implementation-plan.md update

### If Some Failed
- Consider retrying failed images
- Or proceed with available images
- Update implementation-plan.md to note missing images

---
*Generated by lp-image-generation skill*
*Generation Date: [date]*
*Method: [MCP Tool/API Direct/Browser Automation]*
```

## Execution Steps

### Step 1: Read Input

```
1. Read [project-folder]/docs/image-prompts.json
2. Validate JSON structure
3. Extract:
   - project name
   - style_context
   - images array
4. Count total images
5. Log: "Found [X] images to generate"
```

### Step 2: Setup

```
1. Create folder: [project-folder]/assets/images/
2. Detect generation method (see Method Detection above)
3. Log: "Using [method] for image generation"
4. Initialize tracking:
   - success_count = 0
   - failed_count = 0
   - results = []
```

### Step 3: Sort by Priority

```
1. Separate images by priority:
   - high_priority = images.filter(i => i.priority === "high")
   - medium_priority = images.filter(i => i.priority === "medium")
   - low_priority = images.filter(i => i.priority === "low")
2. Combine: sorted_images = [...high, ...medium, ...low]
3. Log: "Processing order: [X] high, [X] medium, [X] low"
```

### Step 4: Generate Images

```
For each image in sorted_images:

  Log: "Generating [image.id] ([current]/[total])..."

  Try:
    // Generate
    result = await generateImage({
      prompt: image.prompt,
      negative_prompt: image.negative_prompt,
      size: image.size,
      format: image.format,
      method: detected_method
    })

    // Process background if needed
    if (image.background !== "keep") {
      result = await processBackground(result, image.background)
    }

    // Save
    await saveImage(result, image.output_path)

    // Track success
    success_count++
    results.push({ id: image.id, status: "success", time: elapsed })
    Log: "Success: [image.id] saved to [output_path]"

  Catch error:
    // Track failure
    failed_count++
    results.push({ id: image.id, status: "failed", error: error.message })
    Log: "Failed: [image.id] - [error.message]"

    // IMPORTANT: Continue to next image, do NOT stop
    continue
```

### Step 5: Generate Report

```
1. Create image-generation-report.md (see Output Report template)
2. Include all results
3. Calculate success rate
4. List failed images with errors
5. Save to [project-folder]/docs/image-generation-report.md
```

### Step 6: Handle Failures

```
If failed_count > 0:
  Use AskUserQuestion for retry options

  If user chooses "Retry all failed":
    - Filter failed images
    - Repeat Step 4 for failed images only
    - Update report

  If user chooses "Retry specific images":
    - Ask which images to retry
    - Repeat Step 4 for selected images
    - Update report

  If user chooses "Skip and continue":
    - Log: "Proceeding with [success_count] images"
    - Note missing images in report

  If user chooses "Use placeholders":
    - Generate placeholder images for failed
    - Mark as placeholders in report
```

## Completion

When generation is complete:

```
Report to orchestrator:
- Step 6 (Image Generation) complete
- Generated: [X]/[total] images
- Success rate: [X]%
- Report: [project-folder]/docs/image-generation-report.md
- Assets: [project-folder]/assets/images/

Ready for Step 7: Image Integration
```

## Quality Checklist

Before marking complete, verify:

- [ ] All high-priority images generated (or noted as failed)
- [ ] Images saved to correct output_path
- [ ] Format matches specification (webp/png)
- [ ] Dimensions match size specification
- [ ] Background processed correctly (if specified)
- [ ] Report created with full details
- [ ] Failed images documented with errors

## Troubleshooting

### No Generation Method Available

```
Use AskUserQuestion:
Question: "No image generation method detected. How would you like to proceed?"
Header: "Generation Method"
Options:
- label: "Configure MCP tool"
  description: "I'll help you set up an MCP image generation tool"
- label: "Configure API"
  description: "I'll set up API credentials for image generation"
- label: "Use browser automation"
  description: "Set up claude-in-chrome for web-based generation"
- label: "Skip image generation"
  description: "Proceed without generating images (use placeholders)"
```

### Generation Taking Too Long

Default timeout: 60 seconds per image

If timeout reached:
1. Mark image as failed
2. Log: "Timeout: [image.id] - generation exceeded 60s"
3. Add to retry list
4. Continue with next image

### Content Policy Violation

If generation refused due to content policy:
1. Mark image as failed
2. Log: "Policy: [image.id] - prompt rejected"
3. Suggest prompt revision in report
4. Continue with next image

---
*lp-image-generation skill - Part of landing-pages workflow*
