# Design System Document: High-End Agency Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Atelier."** 

Unlike standard corporate sites that rely on rigid grids and generic templates, this system treats the web browser as a high-end editorial canvas. It is designed to feel curated, bespoke, and intentional. We move beyond "minimalism" into "intentionality"—where every pixel of whitespace is a deliberate choice. 

To break the "template" look, we employ **intentional asymmetry** and **tonal depth**. By utilizing overlapping elements and a massive typographic scale contrast, we create a sense of architectural structure that is both trustworthy and cutting-edge. The goal is to make MF Agency Lab feel less like a vendor and more like a high-end partner.

---

## 2. Colors
Our palette is rooted in a biological, organic base of deep forest greens and warm cream surfaces. It avoids the clinical "stark white" of traditional SaaS, opting instead for a tactile, paper-like warmth.

### The Palette (Material Design Convention)
*   **Primary (`#192510`)**: Our deep forest green. Use this for authoritative text and primary actions.
*   **Surface (`#fff9ea`)**: The warm cream background. This is our "paper" base.
*   **Secondary (`#5a6053`)**: A muted sage for supporting elements.
*   **Tertiary (`#29210f`)**: A dark, rich obsidian for high-contrast accents.

### Visual Rules for Implementation
*   **The "No-Line" Rule:** Explicitly prohibit 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts. To separate a section, transition from `surface` to `surface-container-low` (`#f9f3e4`).
*   **Surface Hierarchy & Nesting:** Treat the UI as a series of physical layers. A card should not be "placed" on a page; it should "sit" on it. Use `surface-container` tiers (Lowest to Highest) to create nested depth.
*   **The "Glass & Gradient" Rule:** Use Glassmorphism for floating navigation or modals. Utilize semi-transparent versions of `surface` with a `backdrop-blur` of 20px. 
*   **Signature Textures:** For Hero sections, use a subtle linear gradient from `primary` (`#192510`) to `primary-container` (`#2e3b24`) to provide a "velvet" depth that flat color cannot achieve.

---

## 3. Typography
We use **Manrope** across the board, but we vary its application to create an editorial feel. The hierarchy is extreme—large displays command attention, while small, tracked-out labels provide technical precision.

*   **Display-LG (3.5rem):** Reserved for hero headlines. Use tight letter-spacing (-0.02em) to feel premium.
*   **Headline-MD (1.75rem):** Used for section starts. Often paired with an asymmetrical layout.
*   **Body-LG (1rem):** Our standard reading size. Increase line-height to 1.6 for maximum "breathing room."
*   **Label-MD (0.75rem):** All-caps with 0.1em letter spacing. Used for categories, metadata, and "eyebrow" text. This conveys the "Lab" precision of the brand.

The typography hierarchy conveys a "balanced authority"—the large headers show confidence, while the generous whitespace around the body text shows respect for the user's time and focus.

---

## 4. Elevation & Depth
In this system, depth is a feeling, not a shadow. We move away from traditional drop shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Stack `surface-container` tiers. A `surface-container-lowest` card sitting on a `surface-container-low` section creates a soft, natural lift.
*   **Ambient Shadows:** If a floating effect is required (e.g., a primary CTA button), the shadow must be extra-diffused. Use a blur of 40px and an opacity of 6% using a tinted version of `on-surface` (`#1d1c13`). This mimics natural, ambient light.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` (`#c5c8bd`) at **15% opacity**. 100% opaque borders are strictly forbidden.
*   **Glassmorphism:** For top navigation bars, use `surface-container-lowest` at 80% opacity with a `backdrop-blur-xl`. This makes the layout feel integrated and "airy."

---

## 5. Components

### Buttons
*   **Primary:** Background `primary`, text `on-primary`. Roundedness: `md` (0.375rem). No shadow.
*   **Secondary:** Background `secondary-container`, text `on-secondary-container`. 
*   **Tertiary:** Text only, using `primary` color with an animated underline on hover.

### Input Fields
*   **Styling:** No background. Use a bottom-only "Ghost Border" (15% `outline-variant`).
*   **Focus:** Transition the bottom border to `primary` (`#192510`) with a 2px weight.

### Cards & Lists
*   **The "No-Divider" Rule:** Forbid the use of divider lines in lists or between cards. Use vertical white space (32px+) or subtle background shifts (`surface` to `surface-variant`) to separate content. 
*   **Cards:** Use `surface-container-low` with a `lg` (0.5rem) corner radius. Elements inside the card should overlap the edges slightly to break the "box" feel.

### Selection Chips
*   High-contrast: `tertiary` background with `on-tertiary` text. Use `full` roundedness (9999px) to contrast against the more geometric section layouts.

---

## 6. Do's and Don'ts

### Do
*   **DO** use "Over-sized" margins. If you think there is enough whitespace, add 20% more.
*   **DO** use asymmetrical image placements. Align a headline to the left and the supporting image to the far right, leaving a "void" in the center.
*   **DO** use `primary-fixed-dim` (`#bcccac`) for subtle UI accents like progress bars or status indicators to maintain the "Forest" theme.

### Don't
*   **DON'T** use pure black (`#000000`). It breaks the organic warmth of the `surface` palette.
*   **DON'T** use standard 12-column grids for everything. Occasionally break the container to allow images to bleed off the edge of the screen.
*   **DON'T** use 100% opacity borders. It creates a "boxed-in" feel that contradicts the high-end agency aesthetic.
*   **DON'T** use rapid, bouncy animations. Use "Sophisticated Easing"—slow, purposeful transitions (e.g., `cubic-bezier(0.2, 0, 0, 1)`).