# Design: Image Generation pentru Landing Pages

**Data:** 2025-01-13
**Status:** Approved

## Overview

Adăugăm 3 etape noi în workflow-ul de landing pages pentru generarea și integrarea de imagini, stickere și elemente vizuale.

## Workflow Actualizat (11 Pași)

```
Step 0:  Project Setup
Step 1:  Brainstorming
Step 2:  Design DNA
Step 3:  Text Composing
Step 4:  Planning → implementation-plan.md (fără imagini)
Step 5:  Image Prompts (NEW) → image-prompts.json
Step 6:  Image Generation (NEW) → assets/images/*.webp
Step 7:  Image Integration (NEW) → actualizează implementation-plan.md
Step 8:  Building
Step 9:  QA Review
Step 10: Finish
```

## Skills Noi

### 1. `lp-image-prompts` (Step 5)

**Input:**
- `[project-folder]/docs/brainstorm-brief.md`
- `[project-folder]/docs/design-dna.md`
- `[project-folder]/docs/copy-sections.md`
- `[project-folder]/docs/implementation-plan.md`

**Output:**
- `[project-folder]/docs/image-prompts.json`

**Ce face:**
1. Citește toate docs/
2. Identifică nevoi vizuale pentru fiecare secțiune
3. Folosește AskUserQuestion pentru confirmări
4. Generează prompturi optimizate
5. Creează JSON-ul

### 2. `lp-image-generation` (Step 6)

**Input:**
- `[project-folder]/docs/image-prompts.json`

**Output:**
- `[project-folder]/assets/images/*.webp`

**Ce face:**
1. Citește image-prompts.json
2. Creează folder assets/images/
3. Sortează după priority (high → medium → low)
4. Generează fiecare imagine cu modelul configurat
5. Procesează background (transparent/cutout dacă cerut)
6. Raportează rezultate

**Configurare model:** Flexibilă - MCP tool, API, sau browser automation.

### 3. `lp-image-integration` (Step 7)

**Input:**
- `[project-folder]/docs/image-prompts.json`
- `[project-folder]/assets/images/` (fișierele generate)
- `[project-folder]/docs/implementation-plan.md`

**Output:**
- `[project-folder]/docs/implementation-plan.md` (actualizat)

**Ce face:**
1. Citește image-prompts.json
2. Verifică ce imagini există în assets/images/
3. Analizează vizual fiecare imagine
4. Actualizează implementation-plan.md cu:
   - Secțiune "Available Assets" la început
   - "Images to use" pentru fiecare task
5. Raportează integrarea

## Structura JSON pentru Prompturi

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

**Câmpuri:**
- `id`: identificator unic
- `type`: "hero" | "icon" | "illustration" | "sticker" | "decoration"
- `prompt`: prompt pentru generare
- `negative_prompt`: ce să evite
- `size`: dimensiuni (ex: "1920x1080", "256x256")
- `format`: "webp" | "png"
- `background`: "keep" | "transparent" | "cutout"
- `output_path`: path relativ pentru salvare
- `section_target`: secțiunea din plan unde se folosește
- `priority`: "high" | "medium" | "low"

## Modificări la Skills Existente

### lp-orchestrator

- Adaugă Steps 5, 6, 7 în workflow
- Actualizează tabelul Required Sub-Skills
- Adaugă dispatch pattern pentru noile steps

### lp-planning

- Adaugă secțiune "Image Planning"
- Identifică nevoi de imagini per secțiune (fără path-uri concrete)

### lp-building

- Adaugă secțiune "Using Generated Assets"
- Instrucțiuni pentru integrarea imaginilor din plan

## Output Structure Actualizat

```
[project-name]/
├── index.html
├── style.css
├── script.js
├── assets/
│   └── images/
│       ├── hero-bg.webp
│       ├── icon-speed.webp
│       ├── icon-security.webp
│       └── workflow-illustration.webp
└── docs/
    ├── brainstorm-brief.md
    ├── design-dna.md
    ├── copy-sections.md
    ├── implementation-plan.md (with image references)
    ├── image-prompts.json
    └── qa-report.md
```

## Implementation Tasks

1. Creează `lp-image-prompts/SKILL.md`
2. Creează `lp-image-generation/SKILL.md`
3. Creează `lp-image-integration/SKILL.md`
4. Actualizează `lp-orchestrator/SKILL.md`
5. Actualizează `lp-planning/SKILL.md`
6. Actualizează `lp-building/SKILL.md`
7. Actualizează `landing-pages/README.md`
8. Commit și push
