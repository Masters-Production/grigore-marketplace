---
name: pres-emails
description: Step 6 of presentation creation - generate complete email sequences for pre-event, during-event, and post-event communication
---

# Presentation Emails Skill

## Overview

This skill creates complete email sequences to maximize attendance, engagement, and conversions for sales presentations.

## Input Required

- `brainstorming.md` - Event details, product info
- `script.md` - Key messages and offer details
- Event type (webinar/marathon/workshop)

## Core Principles (From Hristosenko)

### Minimize Unnecessary Contacts
**"Каждое лишнее касание с аудиторией — это минус конверсии"**
(Every extra contact = minus conversion)

- Each email reduces next email open rate
- Only send if value justifies the cost
- Ask: "Is this message REALLY necessary?"

### The Ice-Cold Persona
**"Это просто ледяной персонаж. Абсолютно ему плевать"**
(This is an ice-cold persona. They don't care)

For cold traffic, only focus on:
- **Benefit** - What they get
- **Gifts** - What they receive

NO:
- Long stories about you
- Life advice
- Motivational content

### The Dating Analogy
**"Мальчик нашел девочку на сайте знакомств... 2-3 сообщения достаточно"**
(Like dating - 2-3 messages is enough)

More messages = "too pushy, annoying"

## Email Sequences by Event Type

### WEBINAR (5-7 emails total)

#### Pre-Event (4 emails)

**Email 1: Registration Confirmation (Immediate)**
```
Subject: Вы зарегистрированы на [EVENT NAME]!

[NAME],

Поздравляю! Вы зарегистрированы.

📅 Дата: [DATE]
⏰ Время: [TIME]
🔗 Ссылка: [LINK]

Что вас ждёт:
- [BENEFIT 1]
- [BENEFIT 2]
- [BENEFIT 3]

ВАЖНО: В конце будет специальный бонус для тех, кто досмотрит до конца.

До встречи!
[SIGNATURE]

P.S. Сохраните это письмо.
```

**Email 2: Day Before (Value + Hook)**
```
Subject: Завтра - история которая изменила всё

[NAME],

Завтра [EVENT NAME].

Сегодня хочу рассказать историю:
[SHORT STORY - 3-4 sentences about the problem you solved]

Именно тогда я понял [KEY INSIGHT].

Завтра покажу:
- [POINT 1]
- [POINT 2]
- [POINT 3]

📅 [DATE] в [TIME]
🔗 [LINK]

[SIGNATURE]
```

**Email 3: Day Of - Morning**
```
Subject: ⏰ СЕГОДНЯ! [EVENT NAME] в [TIME]

[NAME],

СЕГОДНЯ в [TIME]!

🔗 Ваша ссылка: [LINK]

Будьте онлайн за 5 минут до начала.

До встречи!
[SIGNATURE]
```

**Email 4: Starting Now**
```
Subject: 🔴 МЫ НАЧАЛИ! Присоединяйтесь сейчас

Мы уже начали!

👉 ПРИСОЕДИНИТЬСЯ: [LINK]

[SIGNATURE]
```

#### Post-Event (2-3 emails)

**Email 5: Replay + Offer (2-4 hours after)**
```
Subject: Запись + специальное предложение

[NAME],

Спасибо что были с нами!

🎬 Запись: [REPLAY LINK]
⚠️ Доступна только [X] часов

---

Напоминаю о [PROGRAM NAME]:

✅ [BENEFIT 1]
✅ [BENEFIT 2]
✅ [BENEFIT 3]

🎁 Бонусы до [DEADLINE]:
- [BONUS 1]
- [BONUS 2]

💰 Специальная цена: [PRICE]

👉 [OFFER LINK]

Предложение до [DEADLINE].

[SIGNATURE]
```

**Email 6: Case Study (Day +1)**
```
Subject: Как [NAME] получил [RESULT]

[NAME],

История [STUDENT]:

[BEFORE] → [AFTER]

"[TESTIMONIAL QUOTE]"

Это возможно и для вас.

👉 [OFFER LINK]

⏰ Цена до [DEADLINE].

[SIGNATURE]
```

**Email 7: Final Call**
```
Subject: ⏰ Последний шанс: [X] часов

[NAME],

Через [X] часов:
❌ Цена вырастет
❌ Бонусы исчезнут

👉 [OFFER LINK]

[SIGNATURE]
```

### MARATHON (15-20 emails total)

#### Pre-Marathon (3-4 emails)
- Registration confirmation
- Day -2: What to expect
- Day -1: Preparation
- Day 0 morning: Starting today

#### During Marathon (5 emails - one per day)
- Day 1: Welcome + recap + homework
- Day 2: Progress + preview
- Day 3: Deep dive + anticipation
- Day 4: Case studies + offer hint
- Day 5: Offer day + urgency

#### Post-Marathon (3-4 emails)
- Replay + offer summary
- Case study
- Objection handler
- Final call

### WORKSHOP (4-5 emails total)

#### Pre-Workshop (3 emails)
- Registration + materials
- Day before reminder
- Starting now

#### Post-Workshop (2 emails)
- Replay + offer
- Final call

## Email Writing Guidelines

### Subject Line Formulas

**Urgency:**
- "⏰ [X] часов до..."
- "🔴 Последний шанс"
- "Сегодня заканчивается"

**Curiosity:**
- "История которая изменила всё"
- "Вот что я узнал о [TOPIC]"
- "Главная ошибка которую все делают"

**Benefit:**
- "Как получить [RESULT] за [TIME]"
- "3 секрета [TOPIC]"
- "[X] способов [BENEFIT]"

**Personal:**
- "Могу помочь?"
- "Вы что-то забыли?"
- "Специально для вас"

### Email Structure

```
[GREETING - 1 line]

[HOOK - 1-2 sentences]

[BODY - 3-5 short paragraphs]
- Use bullet points
- Short sentences
- White space

[CTA - Clear and specific]

[SIGNATURE]

[P.S. - Additional hook or urgency]
```

### Formatting Rules

- Short paragraphs (1-3 sentences)
- Bullet points for lists
- Bold for emphasis
- Emojis sparingly (📅 ⏰ 🔗 ✅ 🎁)
- Links clearly visible

## Output Format

Save to: `project/{project-name}/emails.md`

```markdown
# [PROJECT NAME] Email Sequences

## Overview
- Event type: [Webinar/Marathon/Workshop]
- Total emails: [X]
- Pre-event: [Y]
- Post-event: [Z]

---

## PRE-EVENT SEQUENCE

### Email 1: Registration Confirmation
**Send:** Immediately after registration
**Subject:** [Subject line]

[Full email text]

---

### Email 2: [Name]
...

---

## POST-EVENT SEQUENCE

### Email X: [Name]
...
```

## Quality Checklist

- [ ] Minimal emails (only necessary ones)
- [ ] Benefits clear in every email
- [ ] Links prominent and repeated
- [ ] Deadline mentioned in post-event
- [ ] Subject lines tested (short, curious)
- [ ] P.S. used in every email
- [ ] Mobile-friendly formatting

## Next Step

After emails are complete, proceed to `pres-qa-review` skill for final quality check.
