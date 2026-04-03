# Design System Specification: Edge of Space

## 1. Overview & Creative North Star
**Creative North Star: The Stratospheric Command**

This design system is engineered to evoke the precision, heroism, and vastness of high-altitude aviation. Unlike standard military themes that lean on heavy borders and flat olive drabs, this system utilizes a "High-End Editorial" approach. We break the template by embracing the "Edge of Space" aesthetic—where deep atmospheric blues meet the harsh, high-contrast light of the sun.

The layout philosophy is defined by **intentional asymmetry and tonal depth**. We treat the screen not as a flat canvas, but as a flight deck instrumentation panel overlaid against a horizon. Expect wide breathing rooms, overlapping elements that suggest motion, and a typographic scale that commands authority.

---

## 2. Colors: Atmospheric Depth
The palette transitions from the "Deep Space" of the vacuum to the "Tactical Gold" of cockpit instrumentation.

### The Palette (Material Design 3 Logic)
*   **Primary (`#b6c4ff`):** High-altitude sky blue. Used for primary actions and essential focus states.
*   **Surface (`#0b1326`):** The void. This is our foundation, a deep, saturated navy-charcoal.
*   **Tertiary (`#eac34a`):** Tactical Gold. Reserved for high-value CTA highlights, scholarship "hero" moments, and critical status indicators.

### Implementation Rules
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should sit directly against the `background` to create a natural horizon line.
*   **Surface Hierarchy:** Depth is created by nesting. Use `surface-container-lowest` (`#060e20`) for the "recessed" base and `surface-container-highest` (`#2d3449`) for cards that need to "approach" the user.
*   **The Glass & Gradient Rule:** To replicate the cockpit canopy effect, use **Glassmorphism** for floating navigation bars or modals. Apply `surface` colors at 60-80% opacity with a `20px` backdrop-blur.
*   **Signature Textures:** Use subtle linear gradients for main CTAs, transitioning from `primary` (`#b6c4ff`) to `primary_container` (`#001c5d`) at a 135-degree angle. This provides a metallic, aeronautical sheen.

---

## 3. Typography: The Command Scale
We utilize two distinct typefaces to balance technical precision with editorial impact.

*   **Headings (Display & Headline): Space Grotesk.** A typeface that feels engineered. Its idiosyncratic terminals and wide stance evoke flight telemetry and mid-century aerospace logotypes.
*   **Body & Labels: Inter.** Chosen for its maximum legibility at high speeds (and small sizes). It provides a clean, neutral counter-balance to the aggressive personality of Space Grotesk.

### Typographic Intent
*   **Display-LG (3.5rem):** Used for "Hero" scholarship headlines. Letter-spacing should be set to `-0.02em` to feel tight and authoritative.
*   **Label-MD (0.75rem):** Always uppercase with `0.1em` letter-spacing when used for technical data points or "Mission Brief" tags.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "web-standard" for this mission. We use **Atmospheric Perspective**.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-highest` card on top of a `surface` background. The color shift *is* the elevation.
*   **Ambient Shadows:** For floating elements (Modals, Popovers), use a shadow color tinted with `primary` (e.g., `rgba(182, 196, 255, 0.08)`). Blur values must be large (32px+) to mimic the soft scattering of light at high altitudes.
*   **The "Ghost Border" Fallback:** If a container requires more definition, use the `outline_variant` token at **15% opacity**. This creates a "glint" on the edge of the component rather than a hard line.

---

## 5. Components: Precision Engineering

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_container`). `0.25rem` (sm) roundedness. Typography: `label-md` bold, uppercase.
*   **Secondary:** Ghost style. Transparent background with a "Ghost Border" (15% opacity `outline`).
*   **Tactical (Tertiary):** Solid `tertiary` (`#eac34a`) with `on_tertiary` text. Use only for the primary conversion goal (e.g., "Apply Now").

### Cards & Lists
*   **Rule:** No dividers. Use `80px` of vertical whitespace to separate major content blocks.
*   **Scholarship Cards:** Use `surface-container-low` with a subtle top-left "glint" (a 1px inner-shadow using `primary` at 20% opacity).

### Inputs & Fields
*   **State:** The "Active" state should not just change border color; it should trigger a subtle `surface-bright` glow behind the input field to simulate an illuminated instrument.

### Special Component: The "Telemetry" Chip
*   Used for status updates (e.g., "Application Open"). These should use `surface-container-highest` with a small, pulsing dot in `tertiary` gold.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Place a large headline on the left and leave the right 40% of the screen empty to create a sense of vast horizon.
*   **Do** use high-quality, high-contrast photography of aircraft or stratospheric views as "background textures," obscured by deep blue overlays.
*   **Do** lean into the `0.25rem` (sm) roundedness scale. It feels more "instrumental" and "tactical" than overly rounded shapes.

### Don't
*   **Don't** use pure black (#000000). Always use the `surface` or `surface-container-lowest` navy tones to maintain the "Deep Space" atmosphere.
*   **Don't** use standard "Success Green." Use `primary` blue for success and `tertiary` gold for warnings/attention.
*   **Don't** use 100% opaque borders. It breaks the immersion of the atmospheric depth.