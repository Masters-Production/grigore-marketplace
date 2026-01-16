---
name: pres-brainstorming
description: Step 1 of presentation creation - gather requirements through structured questions about event type, audience, product, and goals
---

# Presentation Brainstorming Skill

## Overview

This skill gathers all necessary information to create a high-converting sales presentation for webinars, marathons, or workshops.

## Process

Use `AskUserQuestion` tool to collect information through structured questions. Ask ONE question at a time.

---

## CRITICAL: Offer Packaging Methodology

### The Value Equation
**"Ценность равно масштаб изменений в жизни человека"**
(Value = Scale of changes in person's life)

- The bigger the promised change, the more perceived value
- People choose what promises the LARGEST scale of changes
- This is why "100M launch" beats "educational business system"

### People Buy What They WANT, Not Need
**"Слова вода, люди врут"**
(Words are water, people lie)

- What they SAY they want ≠ What they BUY
- In hookah bar: "We want systems, tired of launches"
- With their wallet: Buy launch course
- Test with MONEY, not words

### Pill vs Vitamin (CRITICAL!)
**"Это не витаминка, это таблетка"**
(This is not a vitamin, it's a pill)

| Type | Characteristic | Example | Sells? |
|------|---------------|---------|--------|
| **Pill** | Solves immediate pain | "Stop panic attacks TODAY" | YES |
| **Vitamin** | Long-term benefit | "Improve mental health over time" | NO |

Your offer MUST be a PILL - immediate, tangible relief from current pain.

### The Prosecco Test
**"Она звонит подруге после двух бутылок просекко..."**
(She calls her friend after two bottles of prosecco...)

Ask yourself:
1. Would your ideal client, relaxed and honest, call a friend about this?
2. Would they say "Oh my god, I want [YOUR OFFER], but I don't know how"?
3. If NO - your offer doesn't hit real desire

### Path of Least Resistance
**"Человек всегда идет по пути наименьшего сопротивления"**
(Person always takes path of least resistance)

- People choose what SEEMS easier, even if less effective
- "15 min/day with ChatGPT" beats "master copywriting in 6 months"
- Minimize perceived effort, maximize perceived result

### Concreteness Beats Generality
**"Не надо ждать, что человек сам додумает"**
(Don't expect them to figure it out themselves)

WRONG: "Transform your life"
RIGHT: "Transform results in key life areas - money, relationships, health, self-realization"

Always specify the SPHERES:
- Деньги (Money)
- Отношения (Relationships)
- Здоровье (Health)
- Реализация (Self-realization)
- Проявленность (Visibility/Manifestation)

### Pre-existing Mental Associations
People have existing associations in their heads:

| Topic | Association | Attractiveness |
|-------|-------------|----------------|
| Crypto | "Buy coin → 1000x → rich" | Very high |
| Launches | "Big money" | Very high |
| Trading | "Complicated, screens, charts" | Lower |
| Systems | "Boring, complex" | Lower |

**USE associations** in your offer naming!

### Skill Re-Packaging Technique
Same skill, different packaging = different results

**Example:**
- BEFORE: Copywriter (15k/month, daily posts, competition)
- AFTER: Reelsmaker (60k/client, expert films, you just write, 15 min/day)

**Process:**
1. Identify base skill
2. Find "sexier" application
3. Calculate attractive numbers
4. Emphasize ease
5. Create new offer

### Title Patterns That Work

**Pattern 1: [Amount] + [Benefit]**
- "Самооценка на миллион" (Million-worth self-esteem)
- "Доход от 300 тысяч" (Income from 300k)

**Pattern 2: [Action] + [Object] + [Concrete Results]**
- "Измени самооценку и трансформируй результаты в деньгах, отношениях, здоровье"

**Pattern 3: [New Profession] + [Demand Attribute] + [Income Promise]**
- "Востребованный копирайтер с доходом от 300к"
- "Релсмейкер – 60к с клиента, 15 минут в день"

---

## Questions Flow

### Phase 1: Event Type & Basics

**Question 1: Event Type**
```
header: "Event Type"
question: "What type of sales event are you creating?"
options:
  - label: "Webinar (60-90 min)"
    description: "Single session, typically 5-15% conversion"
  - label: "Marathon (3-5 days)"
    description: "Multi-day event, higher ticket, 8-20% conversion"
  - label: "Workshop (2-4 hours)"
    description: "Intensive hands-on session, 10-25% conversion"
```

**Question 2: Language**
```
header: "Language"
question: "What language should the presentation be in?"
options:
  - label: "Russian"
    description: "Primary output in Russian"
  - label: "English"
    description: "Primary output in English"
  - label: "Romanian"
    description: "Primary output in Romanian"
  - label: "Bilingual (RU/EN)"
    description: "Both languages in output"
```

### Phase 2: Product & Offer

**Question 3: Product Type**
```
header: "Product"
question: "What type of product/course are you selling?"
options:
  - label: "Online Course"
    description: "Pre-recorded video course"
  - label: "Coaching Program"
    description: "Live coaching with calls"
  - label: "Membership"
    description: "Recurring subscription"
  - label: "High-Ticket Service"
    description: "Done-for-you or consulting"
```

**Question 4: Price Range**
```
header: "Price"
question: "What is the price range of your offer?"
options:
  - label: "Low ticket ($50-$300)"
    description: "Mass market, impulse buy"
  - label: "Mid ticket ($300-$2000)"
    description: "Considered purchase"
  - label: "High ticket ($2000-$10000)"
    description: "Premium offer, may need call"
  - label: "Super high ticket ($10000+)"
    description: "Enterprise or VIP"
```

### Phase 3: Audience

**Question 5: Audience Temperature**
```
header: "Audience"
question: "What is the primary audience type?"
options:
  - label: "Cold Traffic"
    description: "Never heard of you, from ads"
  - label: "Warm Traffic"
    description: "Know you, on email list"
  - label: "Hot Traffic"
    description: "Engaged fans, past customers"
  - label: "Mixed"
    description: "Combination of all"
```

**Question 6: Target Market**
```
header: "Market"
question: "Who is your target audience?"
multiSelect: false
```
*Allow free text response for specific niche*

### Phase 4: Problem & Solution

**Question 7: Main Problem**
```
header: "Problem"
question: "What is the #1 problem your product solves?"
multiSelect: false
```
*Allow free text response*

**Question 8: Main Transformation**
```
header: "Transformation"
question: "What transformation/result does your product deliver?"
multiSelect: false
```
*Allow free text response*

### Phase 5: Differentiators

**Question 9: Why You**
```
header: "Credibility"
question: "What makes you the right person to teach this?"
multiSelect: false
```
*Allow free text response*

**Question 10: Big Idea**
```
header: "Big Idea"
question: "What is your unique approach/methodology? (What makes your solution different?)"
multiSelect: false
```
*Allow free text response*

## Output Format

After collecting all answers, save to project folder:

**File: `project/{project-name}/brainstorming.md`**

```markdown
# Presentation Brainstorming - {Project Name}

## Event Configuration
- **Event Type:** [Webinar/Marathon/Workshop]
- **Language:** [Selected language]
- **Duration:** [Based on event type]

## Product Details
- **Product Type:** [Course/Coaching/etc.]
- **Product Name:** [If provided]
- **Price:** [Range/specific]
- **Guarantee:** [If mentioned]

## Target Audience
- **Temperature:** [Cold/Warm/Hot/Mixed]
- **Target Market:** [Description]
- **Current State:** [Their situation before]
- **Desired State:** [Where they want to be]

## Problem & Solution
- **Main Problem:** [The #1 pain point]
- **Consequences:** [What happens if not solved]
- **Your Solution:** [How you solve it]
- **Transformation:** [End result]

## Positioning
- **Your Credibility:** [Why listen to you]
- **Big Idea:** [Unique approach]
- **Key Differentiator:** [What sets you apart]

## Objections to Address
- [Objection 1]
- [Objection 2]
- [Objection 3]

## Bonuses Planned
- [Bonus 1]
- [Bonus 2]

## Notes
[Any additional context provided]
```

## Quality Checklist

### Basic Requirements
- [ ] Event type selected
- [ ] Language selected
- [ ] Product/offer defined
- [ ] Audience understood
- [ ] Problem clearly articulated
- [ ] Transformation defined
- [ ] Credibility established
- [ ] Big Idea captured

### Offer Packaging (CRITICAL!)
- [ ] Offer is PILL, not vitamin (solves immediate pain)
- [ ] Passes Prosecco Test (would they call a friend about this?)
- [ ] Promises LARGE scale of changes
- [ ] Concrete life spheres mentioned (money, relationships, health, realization)
- [ ] Path of least resistance considered (seems easy)
- [ ] Pre-existing associations leveraged (not fighting negative ones)

### Title/Naming Validation
- [ ] Title uses proven pattern (Amount+Benefit, Action+Result, Profession+Income)
- [ ] Title avoids abstract language ("transform your life")
- [ ] Numbers/amounts included where possible
- [ ] Demand/востребованность element if profession course

### Offer Structure
- [ ] Clear benefit, not just skill
- [ ] Minimized perceived effort
- [ ] Maximized perceived result
- [ ] Re-packaging considered if needed

### Red Flags to Check
- [ ] NOT too complicated (etnovocal example)
- [ ] NOT selling functionality instead of result
- [ ] NOT fighting negative associations
- [ ] NOT vague about outcomes

## Next Step

After brainstorming is complete, proceed to `pres-structure` skill to build the presentation structure.
