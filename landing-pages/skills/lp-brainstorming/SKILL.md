---
name: lp-brainstorming
description: Step 1 of landing page creation - gather requirements through structured questions about goals, audience, and value proposition
---

# Landing Page Brainstorming

You are conducting a brainstorming session to understand exactly what landing page to create. Your goal is to gather all necessary information through AskUserQuestion interactions.

## CRITICAL RULES

1. **Ask questions one at a time** - Don't overwhelm with all questions at once
2. **Use AskUserQuestion tool** - Always provide options + "Other" for custom input
3. **Summarize and confirm** - After gathering info, show summary for approval
4. **Output artifact** - Create `[project-folder]/docs/brainstorm-brief.md` when complete

## Input

The orchestrator will provide the project folder path. All output goes to `[project-folder]/docs/`.

## Question Flow

### Question 1: Landing Page Type

```
Use AskUserQuestion:
Question: "What type of landing page do you need?"
Header: "Page Type"
Options:
- label: "Lead Generation"
  description: "Email capture, lead magnets, newsletter signup"
- label: "Product Launch"
  description: "Pre-orders, coming soon, product reveal"
- label: "SaaS / App"
  description: "Features, pricing, testimonials, free trial"
- label: "Event / Webinar"
  description: "Registration, agenda, speakers"
```

### Question 2: Target Audience

```
Use AskUserQuestion:
Question: "Who is your ideal customer or visitor?"
Header: "Audience"
Options:
- label: "B2B Professionals"
  description: "Business owners, managers, decision makers"
- label: "B2C Consumers"
  description: "General consumers, shoppers"
- label: "Developers / Technical"
  description: "Engineers, programmers, tech-savvy users"
- label: "Let me describe"
  description: "I'll provide specific details"
```

If "Let me describe", ask follow-up:
- What industry are they in?
- What's their role/job title?
- What's their experience level?

### Question 3: Main Problem

```
Use AskUserQuestion:
Question: "What main problem or pain point does your product/service solve?"
Header: "Problem"
Options:
- label: "Saves time"
  description: "Automates tasks, reduces manual work"
- label: "Saves money"
  description: "Reduces costs, better ROI"
- label: "Reduces complexity"
  description: "Simplifies processes, easier workflow"
- label: "Let me describe"
  description: "I'll explain the specific problem"
```

### Question 4: Your Solution

```
Use AskUserQuestion:
Question: "How does your product/service solve this problem?"
Header: "Solution"
Options:
- label: "Software/Tool"
  description: "An app, platform, or digital tool"
- label: "Service"
  description: "A service you or your team provides"
- label: "Information/Course"
  description: "Knowledge, training, education"
- label: "Physical Product"
  description: "A tangible product"
```

Then ask for a 1-2 sentence description of the solution.

### Question 5: Unique Selling Proposition (USP)

```
Use AskUserQuestion:
Question: "What makes you different from competitors?"
Header: "USP"
Options:
- label: "Price"
  description: "More affordable, better value"
- label: "Quality"
  description: "Superior results, premium experience"
- label: "Speed"
  description: "Faster delivery, quicker results"
- label: "Unique feature"
  description: "Something competitors don't have"
```

Ask for specific differentiator details.

### Question 6: Primary Call-to-Action

```
Use AskUserQuestion:
Question: "What action should visitors take?"
Header: "CTA"
Options:
- label: "Sign up / Register"
  description: "Create account, start free trial"
- label: "Subscribe"
  description: "Email newsletter, updates"
- label: "Buy / Purchase"
  description: "Direct sale, checkout"
- label: "Book / Schedule"
  description: "Meeting, demo, consultation"
```

### Question 7: Social Proof

```
Use AskUserQuestion:
Question: "What social proof do you have?"
Header: "Proof"
multiSelect: true
Options:
- label: "Customer testimonials"
  description: "Quotes from happy customers"
- label: "Numbers/Stats"
  description: "Users, revenue, growth metrics"
- label: "Client logos"
  description: "Known companies that use you"
- label: "None yet"
  description: "Starting fresh, no proof available"
```

### Question 8: Urgency/Offer

```
Use AskUserQuestion:
Question: "Do you have any urgency or special offer?"
Header: "Urgency"
Options:
- label: "Limited time offer"
  description: "Discount expires on specific date"
- label: "Limited quantity"
  description: "Only X spots/units available"
- label: "Early bird pricing"
  description: "Special price for early adopters"
- label: "No urgency"
  description: "Evergreen, no time pressure"
```

### Question 9: Tone of Voice

```
Use AskUserQuestion:
Question: "What tone should the landing page have?"
Header: "Tone"
Options:
- label: "Professional"
  description: "Formal, business-like, trustworthy"
- label: "Casual & Friendly"
  description: "Conversational, approachable"
- label: "Bold & Urgent"
  description: "High-energy, action-driven"
- label: "Technical & Precise"
  description: "Detailed, specification-focused"
```

## After All Questions

### Summarize and Confirm

Present a summary to the user:

```markdown
## Brainstorm Summary

**Type:** [Lead Generation]
**Audience:** [B2B professionals in marketing]
**Problem:** [Spending too much time on manual reporting]
**Solution:** [Automated analytics dashboard]
**USP:** [AI-powered insights, 10x faster than competitors]
**CTA:** [Start free trial]
**Social Proof:** [50+ customer testimonials, 500 companies]
**Urgency:** [Limited time: 30% off first year]
**Tone:** [Professional]

Is this correct? Would you like to change anything?
```

Use AskUserQuestion to confirm or allow edits.

## Output Artifact

Once confirmed, create `[project-folder]/docs/brainstorm-brief.md`:

```markdown
# Landing Page Brief

## Objective
[Type] landing page with primary CTA: [CTA action]

## Target Audience
- **Who:** [description]
- **Pain Point:** [main problem]
- **Desire:** [what they want to achieve]

## Value Proposition
- **USP:** [unique selling proposition]
- **Key Benefits:**
  1. [benefit 1]
  2. [benefit 2]
  3. [benefit 3]

## Social Proof
- [type of proof available]
- [specific examples if provided]

## Urgency/Offer
[urgency element or "Evergreen - no time pressure"]

## Planned Sections
1. Hero (headline + CTA)
2. Problem/Solution
3. Benefits
4. Social Proof
5. FAQ (if applicable)
6. Final CTA

## Tone of Voice
[selected tone with brief description]

---
*Generated by lp-brainstorming skill*
```

## Completion

After creating the artifact:
1. Confirm file was created
2. Report back to orchestrator that Step 1 is complete
3. Provide path to artifact: `[project-folder]/docs/brainstorm-brief.md`
