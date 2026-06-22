---
name: frontend-design
description: Design distinctive, intentional UIs — avoid AI defaults, make deliberate aesthetic choices
---

# Frontend Design

Approach as design lead at a small studio. Every client gets a visual identity no one else has.

## Design Philosophy

- Make deliberate, opinionated choices about palette, typography, layout
- Take one real aesthetic risk you can justify
- Reject templated defaults — the brief's own words always win

## Process: Brainstorm → Explore → Plan → Critique → Build → Critique Again

### 1. Ground It in the Subject

Before designing:
- Name the concrete subject, audience, page's single job
- The subject's own world (materials, instruments, artifacts) is where distinctive choices come from
- Build with real content throughout

### 2. Brainstorm Plan

Compact token system:
- Color: 4-6 named hex values
- Type: 2+ roles (display, body, accent)
- Layout: ASCII wireframe
- Signature element: one memorable thing

### 3. Review Against Brief

If any part reads like generic default → revise that part, explain what changed and why.

### 4. Build Code

Follow revised plan exactly. Derive every decision from it.

### 5. Critique

- Take screenshots (picture = 1000 tokens)
- Ask: "What would a real designer change?"
- Chanel's advice: before leaving the house, remove one accessory

## Design Principles

### Hero is a Thesis
Open with the most characteristic thing in the subject's world. Be deliberate — big number with small label + gradient accent is the template answer, only use if truly best.

### Typography Carries Personality
Pair display and body faces deliberately. Set clear type scale with intentional weights, widths, spacing. Make type treatment memorable.

### Structure is Information
Structural devices (numbering, eyebrows, dividers) should encode something true about content, not decorate.

### Leverage Motion Deliberately
Orchestrate one moment that lands harder than scattered effects. Sometimes less is more — extra animation = AI-generated feel.

### Match Complexity to Vision
Maximalist needs elaborate execution; minimal needs precision. Elegance = executing the chosen vision well.

## AI Design Defaults to Avoid

These cluster around three looks:

1. **Warm cream** (#F4F1EA) + high-contrast serif + terracotta accent
2. **Near-black background** + single acid-green/vermilion accent
3. **Broadsheet layout** + hairline rules + zero border-radius + dense columns

All legitimate for some briefs, but they're defaults not choices. Where brief leaves an axis free, don't spend it on these.

## Writing in Design

- Words are design material, not decoration
- Write from end user's side: "Notifications" not "webhook config"
- Active voice default: "Save changes" not "Submit"
- Same vocabulary through whole flow: button "Publish" → toast "Published"
- Errors: explain what went wrong and how to fix it, never apologize
- Empty screen = invitation to act

## Restraint

- Spend boldness in ONE place
- Cut decoration that doesn't serve the brief
- Not taking a risk can be a risk itself
- Build quality floor: responsive, visible keyboard focus, reduced motion respected
