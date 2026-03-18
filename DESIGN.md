# Design System: High-Performance Engineering Aesthetic

## 1. Overview & Creative North Star

### Creative North Star: "The Kinetic Laboratory"
This design system moves away from the static, traditional web layouts of the past and into a high-performance, data-driven environment. It is inspired by the precision of F1 telemetric dashboards and the technical sophistication of aerospace engineering. The "Kinetic Laboratory" aesthetic is characterized by raw technical data, intentional asymmetry, and a surgical use of light against deep, obsidian surfaces.

To break the "template" look, we utilize a **Technical Grid Overlay**. Instead of hiding our structure, we celebrate it. Subtle, non-intrusive grid lines and "coordinates" (label-sm typography placed at container corners) provide an editorial, blueprint-like feel. Components should feel like modular "HUD" (Heads-Up Display) panels—removable, swappable, and high-functioning.

---

## 2. Colors

The palette is anchored in a monochromatic "Obsidian" base to ensure the vibrant "Ignition Red" accents deliver maximum impact without visual fatigue.

*   **Background (`#131313`) & Surfaces:** We use a monochromatic stack to define depth.
*   **Primary (`#ffb4aa`) / Secondary (`#ffb4a8`):** These tokens represent our "Ignition Red." Use them sparingly for high-action items, telemetry alerts, and focus states.
*   **The "No-Line" Rule:** Sectioning must never be achieved through 1px solid borders. Boundaries are defined by shifting from `surface` to `surface-container-low` or `surface-container-high`. If a visual break is needed, use a change in background tonal value, not a stroke.
*   **Surface Hierarchy & Nesting:** Treat the UI as a physical machine.
    *   The base layer is `surface`.
    *   A technical data panel sits on `surface-container-low`.
    *   Interactive controls or "active" modules use `surface-container-highest`.
*   **The "Glass & Gradient" Rule:** Floating HUD panels should utilize Glassmorphism. Use semi-transparent variants of `surface-container` with a `backdrop-blur` of 12px–20px. 
*   **Signature Textures:** Apply a subtle linear gradient to main CTAs (transitioning from `primary` to `primary-container`). This adds a "glowing" energy reminiscent of a backlit mechanical switch.

---

## 3. Typography

Typography is the primary driver of the "Engineering" feel. We pair the geometric, wide-stanced **Space Grotesk** with the surgical precision of **Inter**.

*   **Display & Headlines (Space Grotesk):** These are our "telemetry" headers. Use `display-lg` for hero impact. Space Grotesk’s unique apertures feel futuristic and machined.
*   **Body (Inter):** High legibility is paramount for technical documentation. Inter provides a neutral, crisp counterpoint to the aggressive headings.
*   **Labels (Space Grotesk):** `label-md` and `label-sm` are used for "Micro-Data"—system timestamps, version numbers, or grid coordinates. These should often be in ALL CAPS with a tracking (letter-spacing) increase of 0.05rem to mimic dashboard readouts.

---

## 4. Elevation & Depth

We eschew traditional drop shadows for **Tonal Layering** and **Luminescent Glare**.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-lowest` card placed on a `surface` background creates a "recessed" look, like a screen set into a dashboard.
*   **Ambient Shadows:** For floating HUD elements, use extra-diffused shadows. 
    *   *Value:* `0px 20px 40px rgba(0, 0, 0, 0.4)`. 
    *   Avoid grey shadows; ensure the shadow color is a deep, tinted version of the background to maintain "Dark Mode" purity.
*   **The "Ghost Border" Fallback:** If a container requires definition against a similar tone, use the `outline-variant` token at 15% opacity. This creates a "glint" on the edge rather than a heavy line.
*   **HUD Glow:** Interactive elements in a "High-Alert" state (like a mission-critical button) can utilize a soft outer glow using the `primary` color at 10% opacity, simulating a light-emitting diode (LED).

---

## 5. Components

### Buttons
*   **Primary:** Sharp corners (`0px` radius). Background: `primary` to `primary-container` gradient. Text: `on-primary` (All Caps).
*   **Secondary/Tertiary:** No background. `Ghost Border` (outline-variant @ 20%) with a `primary` glow on hover.
*   **Interaction:** On hover, buttons should "overdrive"—increase brightness and add a subtle 2px lateral shift to suggest mechanical movement.

### HUD Panels (Cards)
*   **Forbid Dividers:** Do not use lines to separate content within a card. Use `1.75rem` (Spacing 8) of vertical whitespace or a subtle background shift to `surface-container-high`.
*   **Styling:** Sharp `0px` corners. Incorporate a small "corner bracket" in the top-left using the `primary` color to emphasize the engineering aesthetic.

### Input Fields
*   **Style:** Underline-only or fully enclosed in a `surface-container-lowest` block. 
*   **States:** On focus, the bottom border "charges" with the `primary` color, and a subtle glow appears behind the text.

### Additional Components: Telemetry Data Points
*   **Component:** Small modules showing "Live" stats (e.g., Robot Battery, Velocity).
*   **Style:** `label-sm` category name in `secondary`, followed by a `title-lg` numerical value. Always include a small "+" or "-" trend indicator.

---

## 6. Do's and Don'ts

### Do
*   **DO** use strict `0px` border radii. Sharpness equates to precision in this system.
*   **DO** use intentional asymmetry. Align a heading to the left, but place the supporting data points on a far-right "Sidebar" grid.
*   **DO** treat the background as a 3D space. Use varying shades of black/grey to create "pits" and "platforms."
*   **DO** use "Micro-copy." Add small technical strings (e.g., "SYS_REF: 0042") in `label-sm` to fill negative space and enhance the "Engineering" vibe.

### Don't
*   **DON'T** use rounded corners. It breaks the "Machined" look and feels too consumer-grade.
*   **DON'T** use 100% opaque white for body text. Use `on-surface-variant` (`#e9bcb6` at reduced opacity) to prevent "retina burn" against the deep black.
*   **DON'T** use traditional icons for everything. Sometimes a text-based label (e.g., "[ MENU ]") is more evocative of a high-end interface than a hamburger icon.
*   **DON'T** clutter the UI. High performance requires focus. If a piece of data isn't necessary, purge it.