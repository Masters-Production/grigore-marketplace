# Design: lp-visual-concepts Skill

**Data:** 2026-01-13
**Status:** Aprobat
**Scop:** Adăugarea gândirii conceptuale vizuale în workflow-ul de landing pages

---

## Problema

Prompturile actuale de imagine sunt generice și nu captează sofisticarea designurilor profesionale:

| Element | Designuri profesionale | Sistem actual |
|---------|------------------------|---------------|
| Metafore vizuale | Ceas pe spate = timp, șah = leadership | Nu există |
| Compoziție/layering | Text în spate, obiecte ies din frame | Nu există |
| Stil 3D/rendering | Octane render, marble, bloom effect | Basic |
| Poziționare | "Obiect la 30% stânga, înclinat 15°" | Nu există |

## Soluția

Noul skill `lp-visual-concepts` care rulează între Planning și Image Prompts:

```
[design-dna] → [visual-concepts] → [image-prompts] → [image-generation]
    ↓               ↓                    ↓
  culori,        metafore,          prompturi
  mood           compoziție         tehnice
                 layering           avansate
```

---

## Workflow Actualizat

### Steps renumerotate:

```
Step 1: Brainstorming
Step 2: Design-DNA
Step 3: Text Composing
Step 4: Planning
Step 5: Visual Concepts    ← NOU
Step 6: Image Prompts      (fost Step 5)
Step 7: Image Generation   (fost Step 6)
Step 8: Image Integration  (fost Step 7)
Step 9: Building           (fost Step 8)
Step 10: QA Review         (fost Step 9)
Step 11: Finish            (fost Step 10)
```

---

## Specificații: lp-visual-concepts

### Input
- `[project-folder]/docs/brainstorm-brief.md` - context proiect, audiență
- `[project-folder]/docs/design-dna.md` - culori, mood, stil vizual
- `[project-folder]/docs/copy-sections.md` - text pentru fiecare secțiune
- `[project-folder]/docs/implementation-plan.md` - structura secțiunilor

### Output
- `[project-folder]/docs/visual-concepts.md` - concepte vizuale per secțiune

### Procesul

**1. Analizează contextul:**
- Citește copy-ul secțiunii
- Extrage mood-ul din design-dna
- Înțelege audiența din brainstorm-brief

**2. Propune 2-3 concepte vizuale per secțiune principală:**
- Folosește AskUserQuestion
- Descrie metafora, compoziția, stilul pentru fiecare opțiune

**3. Documentează alegerile în visual-concepts.md**

**4. Pentru iconuri/decorațiuni:** Decide autonom bazat pe stilul ales

### Interacțiune cu Utilizatorul

Propune și confirmă pentru secțiunile principale:
- Hero Section
- Benefits/Features
- Social Proof
- Final CTA

Decide autonom pentru:
- Iconuri
- Decorațiuni/stickers
- Divisori de secțiuni
- Elemente de fundal secundare

---

## Structura Output: visual-concepts.md

```markdown
# Visual Concepts

## Hero Section

### Concept vizual
**Metaforă:** [descriere metaforă]
**Mesaj:** [ce comunică vizual]

### Compoziție
- **Prim-plan:** [element principal, poziție, unghi]
- **Fundal:** [tip fundal, efecte]
- **Text:** [relația cu elementele vizuale]
- **Elemente secundare:** [decorațiuni, particule]

### Stil rendering
- [tip render: 3D realist, ilustrație, etc.]
- [lighting: studio, natural, dramatic]
- [culori specifice din design-dna]
- [efecte: blur, bloom, shadows]

### Imagini necesare
1. `hero-[name]` - [descriere] (background type)
2. `hero-[name]` - [descriere] (background type)

---

## Benefits Section
[aceeași structură]

---

## Social Proof Section
[aceeași structură]

---

## CTA Section
[aceeași structură]

---

## Iconuri și Decorațiuni

### Stil general iconuri
- [tip: 3D isometric, flat, outlined]
- [culori, efecte]

### Lista iconuri
| ID | Secțiune | Descriere |
|----|----------|-----------|
| icon-1 | benefits | [descriere] |

### Decorațiuni
| ID | Poziție | Descriere |
|----|---------|-----------|
| deco-1 | hero corners | [descriere] |
```

---

## Modificări în lp-image-prompts

### Input actualizat
```
Înainte: design-dna.md
După:    design-dna.md + visual-concepts.md
```

### Generare prompturi avansate

**Înainte:**
```
"Abstract gradient background, blue (#1a2744), modern style, high quality"
```

**După:**
```
"3D rocket launching at 15° angle, metallic chrome material with subtle scratches,
studio lighting with strong rim light from upper right, motion blur on exhaust particles,
navy blue (#1a2744) body with coral (#ff6b6b) flames, transparent background,
octane render quality, dramatic perspective from below, 8k resolution"
```

### Schimbări în skill
1. Citește `visual-concepts.md` ca input principal
2. Transformă "compoziție brief" în specificații tehnice
3. Adaugă termeni de rendering (octane, studio lighting, materials)
4. Nu mai întreabă utilizatorul ce imagini vrea (deja decis)
5. Focus pe optimizarea tehnică a prompturilor

---

## Modificări în lp-orchestrator

### Adăugare Step 5

```markdown
## Step 5: Visual Concepts

**Purpose:** Generate creative visual concepts for each section

**Dispatch Pattern:**
Task tool:
  subagent_type: "general-purpose"
  description: "Execute visual-concepts step"
  prompt: |
    SKILL TO USE: landing-pages:lp-visual-concepts
    PROJECT FOLDER: [project-folder]

    Input: Read all docs from [project-folder]/docs/
    - brainstorm-brief.md
    - design-dna.md
    - copy-sections.md
    - implementation-plan.md

    Follow the skill instructions to create visual concepts.
    Propose 2-3 options per major section.
    Document choices in visual-concepts.md

    Output: [project-folder]/docs/visual-concepts.md

**Verification:** Check visual-concepts.md exists and has content for Hero, Benefits, CTA
```

### Renumerotare Steps 6-11

Toate referințele la steps actualizate corespunzător.

---

## Fișiere de Modificat

| Fișier | Acțiune | Descriere |
|--------|---------|-----------|
| `lp-orchestrator/SKILL.md` | Modifică | Adaugă Step 5, renumerotează 6-11 |
| `lp-image-prompts/SKILL.md` | Modifică | Citește visual-concepts.md, prompturi avansate |
| `skills/lp-visual-concepts/SKILL.md` | **Creează** | Skill-ul nou complet |

---

## Exemple de Concepte Vizuale

### Exemplu 1: Productivitate
**Metaforă:** Rachetă care decolează
**Compoziție:** Obiect central 3D, înclinat 15°, iese din frame jos, text în spate
**Stil:** Chrome metalic, rim lighting, motion blur pe flăcări

### Exemplu 2: Timp Salvat
**Metaforă:** Ceas care explodează în bucăți
**Compoziție:** Fragmente floating din centru spre exterior, efect dramatic
**Stil:** Glass shatter, slow-motion freeze frame, particule strălucitoare

### Exemplu 3: Leadership
**Metaforă:** Piese de șah (rege, regină) pe tablă
**Compoziție:** Perspectivă joasă, piese în focus, fundal blur, reflexie pe tablă
**Stil:** 3D realist, marble texture, studio lighting dramatic

### Exemplu 4: Securitate
**Metaforă:** Scut 3D cu efect de energie
**Compoziție:** Central, ușor rotit, particule de energie în jurul lui
**Stil:** Holographic, glow effects, transparent energy field

---

## Criterii de Succes

1. **Visual-concepts.md conține:**
   - Concept clar pentru fiecare secțiune principală
   - Descriere compoziție (layering, poziționare)
   - Stil rendering specificat
   - Lista imaginilor necesare

2. **Image-prompts generează prompturi cu:**
   - Termeni tehnici de rendering (octane, studio lighting)
   - Specificații de materiale (chrome, marble, glass)
   - Efecte (blur, bloom, reflection)
   - Compoziție precisă (unghi, poziție, crop)

3. **Imaginile generate arată:**
   - Compoziții complexe ca în exemplele profesionale
   - Metafore vizuale clare
   - Calitate de rendering înaltă

---

## Note de Implementare

- Skill-ul folosește subagent pattern ca restul workflow-ului
- AskUserQuestion pentru secțiuni principale, autonom pentru secundare
- Output markdown ușor de citit de către image-prompts skill
- Păstrează consistența cu design-dna (culori, mood)

---

*Design aprobat: 2026-01-13*
