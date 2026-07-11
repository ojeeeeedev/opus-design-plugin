---
name: ultimate-design-guideline
description: Use when creating, auditing, or updating a project-level DESIGN.md design-system standard to establish consistent layout, tokens, components, or themes.
---

# Ultimate Design Guideline

## Purpose

Use this skill to create or update a single project-level `DESIGN.md` that serves as the UI constitution for a webapp. The design system should synthesize modern industry best practices for digital interfaces:

- **Clarity & Restraint**: Prioritize content legibility, visual hierarchy, high-contrast typography, and platform-native feedback.
- **Precision & Minimalism**: Emphasize clean lines, typographic scales, layout alignments, and structural consistency without decorative clutter.
- **Calming & Human-Centered Interaction**: Focus on low cognitive load, thoughtful defaults, responsive spacing, and smooth, meaningful transitions.
- **Operational Efficiency & Density**: Balance whitespace and high-density layouts for B2B dashboards, tables, forms, and data visualizations.

## Step-by-Step Process

1. **Consult Supporting Design & Motion Skills**: Identify the active agent's configuration directory or the local project workspace. You MUST read and consult the following supporting skills inside this plugin bundle (`./skills/`) in union before writing or updating the project's `DESIGN.md` file:
   - **Impeccable** (`./skills/impeccable/SKILL.md`): Learn premium design engineering practices, OKLCH color rules, strict contrast ratio verification (minimum 4.5:1), typography rules (65–75ch limit, clamping font sizes), and absolute design bans (no side-stripe borders, no text gradients, no lazy identical card grids, no decorative blurs/glassmorphism defaults, no tiny uppercase tracked eyebrows/numbers as default scaffolding).
   - **Leon's Taste** (including `./skills/design-taste-frontend/SKILL.md`, `./skills/brandkit/SKILL.md`, `./skills/high-end-visual-design/SKILL.md`, `./skills/minimalist-ui/SKILL.md`, `./skills/industrial-brutalist-ui/SKILL.md`, `./skills/imagegen-frontend-web/SKILL.md`, `./skills/imagegen-frontend-mobile/SKILL.md`, and `./skills/redesign-existing-projects/SKILL.md`): Learn how to infer the visual design direction (page kind, vibe, reference signals, audience, constraints), setting variance, motion, and visual density dials, composition-first layout principles, and selecting the appropriate official design system.
   - **Emil Kowalski's Animation** (`./skills/emil-design-eng/SKILL.md`, `./skills/animation-vocabulary/SKILL.md`, `./skills/review-animations/SKILL.md`): Learn the frequency-based animation decision framework (e.g. no animations for keyboard actions or high-frequency UIs), ease-out curves for entrances, and smooth transition timings.
2. **Inspect Codebase**: Identify the current styling stack (Tailwind, CSS variables, CSS Modules, or component libraries), typography, layouts, and existing tokens.
3. **Draft/Update `DESIGN.md`**: Create a clean, portable, and enforceable design system standard matching the structure below. Synthesize and incorporate the guidelines, color strategies, layout constraints, motion rules, and anti-patterns from the consulted skills.
4. **Refactor Path**: If existing UI has styling inconsistencies, document them and provide an incremental refactor plan without modifying business logic.

## Required DESIGN.md Structure

1. **Design Identity**: Visual personality, vibe selection, and design goals (incorporating brief inference and design dials from the Taste skills).
2. **Design Tokens**: Standardize semantic variables rather than hardcoded hex colors:
   - Spacing: 8-point system (4px, 8px, 12px, 16px, 24px, 32px, etc.).
   - Colors: `background`, `foreground`, `card`, `popover`, `primary`, `muted`, `accent`, `destructive`, `border`, `input`, `ring`. Specify OKLCH tokens and contrast verification rules (referencing Impeccable guidelines).
   - Radius: standard small, medium, large, and full definitions.
3. **Component Standards**: Enforce consistent styles, interactive states (default, hover, active, focus, disabled, loading), accessibility (labels, focus indicators), and layouts for:
   - Buttons, Form Inputs, Tables, Dialogs/Modals, and Navigations.
     Ensure cardless and composition-first layouts are default unless cards are strictly necessary (referencing Taste and Impeccable).
4. **Motion & Transitions**: Detailed rules based on Emil Kowalski's Animation framework:
   - Frequency-based animation guidelines (never animate keyboard-initiated actions or high-frequency transitions).
   - Entrance and exit easing (default to ease-out/exponential curves) and durations.
   - Reduced motion fallback requirements (`@media (prefers-reduced-motion: reduce)`).
5. **Data Visualization**: Guidelines for clean, readable, low-noise charts and tables (e.g., standard color palettes, tabular numbers for data).
6. **Theme & Responsiveness**: Structured approach for light/dark modes (using scene/lighting context to determine themes) and responsive layout breakpoints.
7. **AI Agent Instructions**: Verbatim rules requiring subsequent agents to read `DESIGN.md`, follow existing tokens, and avoid creating one-off overrides.
8. **Design Review Checklist**: A validation list for checking semantic tokens, keyboard accessibility, animation frequency, themes, and mobile responsiveness.

## AI Agent Rules (Include in DESIGN.md)

- Always read `DESIGN.md` before changing UI.
- Use semantic variables only; never hardcode colors, spacing, or typography.
- Avoid introducing new UI libraries or styles unless explicitly updating the design system.
- If the user wants to add a new UI library, ask the user for confirmation. Don't block them from changing libraries as new and updated libraries can release at any time.
