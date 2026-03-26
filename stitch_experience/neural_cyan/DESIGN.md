# Design System Strategy: The Synthetic Luminal

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**
This design system moves beyond the generic "SaaS dashboard" aesthetic to position the AICG creator as an elite technologist and artist. The goal is to balance the cold, high-performance nature of AI with a sophisticated, editorial human touch. 

To break the "template" look, this system utilizes **Intentional Asymmetry**. Instead of a centered, rigid grid, use the 8.5rem (24) spacing token to create wide, breathable gutters that allow content to "float" like artifacts in a digital gallery. Elements should overlap—a `display-lg` headline should partially bleed into a glassmorphism card—creating a sense of three-dimensional depth and cinematic motion.

---

## 2. Colors & Surface Architecture
The palette is rooted in deep obsidian tones, punctuated by "Electric" blue accents that feel like light emitted from a screen.

*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for structural sectioning. Transition between content blocks using background shifts: move from `surface` (#0e0e10) to `surface-container-low` (#131315) to define a new narrative beat.
*   **Surface Hierarchy & Nesting:** Treat the UI as layers of "Polarized Glass."
    *   **Base:** `surface` (#0e0e10).
    *   **Level 1 (Sections):** `surface-container-low` (#131315).
    *   **Level 2 (Cards/Modules):** `surface-container-high` (#1f1f22).
    *   **Level 3 (Interactive):** `surface-container-highest` (#262528).
*   **The "Glass & Gradient" Rule:** Main CTAs and featured sections should utilize a linear gradient from `primary` (#85adff) to `primary-dim` (#0070eb) at a 135-degree angle. Floating navigation or modal overlays must use `surface-variant` (#262528) at 60% opacity with a `20px` backdrop-blur to achieve a high-end glassmorphism effect.

---

## 3. Typography: The Editorial Tech-Stack
We use a high-contrast pairing: **Space Grotesk** for futuristic authority and **Inter** for clinical, tech-focused legibility.

*   **Display & Headline (Space Grotesk):** These are your "Brand Statements." Use `display-lg` (3.5rem) with a tight letter-spacing (-0.02em). These should feel like headers in a high-end tech journal.
*   **Body & Labels (Inter):** All functional information uses Inter. `body-lg` (1rem) is the workhorse for descriptions. 
*   **The Hierarchy Rule:** Never use more than two typographic scales in a single component. For a card, use `title-lg` and `body-md`. The contrast between the wide, geometric Space Grotesk and the neutral Inter creates a "Human vs. Machine" visual tension that defines the AICG space.

---

## 4. Elevation & Depth
In a dark-themed AI environment, depth is signaled by **Light Emission**, not shadow.

*   **Tonal Layering:** Avoid shadows on static cards. Instead, use a "Surface Lift." Place a `surface-container-highest` card on a `surface-dim` background. The delta in lightness provides a cleaner, more modern separation than a drop shadow.
*   **Ambient Glows:** For "active" or "featured" states, apply a glow using the `secondary` (#00d2fd) token. The shadow should be extra-diffused: `0px 20px 50px rgba(0, 210, 253, 0.15)`.
*   **The Ghost Border:** If a boundary is required (e.g., input fields), use the `outline-variant` (#48474a) at **20% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Use `surface-bright` (#2c2c2f) at 40% opacity with `backdrop-filter: blur(12px)` for floating navbars to ensure content remains legible while feeling integrated into the "atmosphere."

---

## 5. Components

### Buttons: The Kinetic Triggers
*   **Primary:** Gradient background (`primary` to `primary-dim`), `full` roundedness, and a subtle `secondary` glow on hover. Text uses `on_primary_fixed` (Black) for maximum punch.
*   **Secondary:** Ghost style. No background, `outline-variant` (20% opacity) border, and `primary` text.
*   **Padding:** Use `spacing-3` (1rem) vertical and `spacing-6` (2rem) horizontal for a wide, premium feel.

### Cards: The Content Vessels
*   **Styling:** No borders. Background: `surface-container-high`. Radius: `xl` (0.75rem). 
*   **Content Separation:** Forbid divider lines. Use `spacing-5` (1.7rem) of vertical whitespace to separate the title from the body text.

### Inputs: The Prompt Fields
*   **Styling:** `surface-container-lowest` (Black) background to create a "void" effect. Border: `outline-variant` at 20%. 
*   **Focus State:** Border shifts to `secondary` (#00d2fd) with a 4px outer glow of the same color at 10% opacity.

### AICG Specific: The "Generation" Loader
*   A custom component: A thin (2px) progress bar using a moving gradient between `secondary` and `tertiary` (#ac89ff). This reflects the multi-modal nature of AI content generation (Blue for Tech, Purple for Creativity).

---

## 6. Do’s and Don’ts

### Do:
*   **DO** use extreme whitespace. Use `spacing-24` (8.5rem) between major sections to emphasize the "Editorial" feel.
*   **DO** use `tertiary` (#ac89ff) sparingly as a "Discovery" accent—use it for tags like "New" or "AI-Generated."
*   **DO** ensure all text on `surface` backgrounds meets WCAG AA contrast using the `on-surface` (#f9f5f8) token.

### Don't:
*   **DON'T** use 100% white (#FFFFFF). Always use `on-surface` (#f9f5f8) to prevent eye strain in dark mode.
*   **DON'T** use standard 4px or 8px "Material" shadows. They look muddy in dark themes. Use tonal shifts or colored glows.
*   **DON'T** center-align long blocks of text. Stick to left-aligned editorial layouts to maintain the "Digital Curator" persona.