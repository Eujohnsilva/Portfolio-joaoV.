# Design System Strategy: High-End Social Editorial

## 1. Overview & Creative North Star
**The Creative North Star: "The Kinetic Curator"**

This design system is engineered to move João’s portfolio away from the static, "template-ready" world and into a high-impact, editorial space. Social media is fast-paced, bold, and visual; the UI must reflect this through a **"Kinetic Curator"** aesthetic. 

The system utilizes a "Rectangular Quadrant" philosophy—a structural grid inspired by high-end print magazines and brutalist architecture. It avoids the soft, rounded "friendliness" of generic SaaS products, opting instead for razor-sharp edges (`0px` roundedness) and a dominant dark-mode palette. We break the grid's rigidity through intentional asymmetry: overlapping large-scale typography, high-contrast imagery, and tonal depth that creates a "nested" physical reality.

---

## 2. Colors
The palette is rooted in deep obsidian tones, punctuated by a high-octane "Highlight" orange.

*   **Primary (`#ffb59e` / `#F04D07`):** Use for critical CTAs and high-impact accents. This is the "pulse" of the portfolio.
*   **Surface Hierarchy (`#161215` to `#383337`):** We use a monochromatic stack to build depth. 
*   **The "No-Line" Rule:** Explicitly prohibit the use of 1px solid borders for sectioning. Physical boundaries must be defined solely by shifting the background color. A `surface-container-low` section should transition directly into a `surface` section to create a clean, modern break.
*   **Surface Nesting:** Treat the UI as layers of fine paper. An inner card should use `surface-container-highest` when sitting on a `surface-container` background.
*   **The "Glass & Gradient" Rule:** Use the `primary_container` (`#ff5716`) to create subtle radial gradients behind hero images or section headers to provide "visual soul." Use backdrop-blur effects (Glassmorphism) for navigation bars or floating status chips.

---

## 3. Typography
The type system is a dialogue between the aggressive, condensed energy of **Anton** and the functional clarity of **Poppins**.

*   **Display-LG (Anton, 3.5rem):** Reserved for João’s name and high-impact service titles. Letter-spacing should be tightened (e.g., -2%) to maximize the "Bold" personality.
*   **Headline (Space Grotesk/Anton):** Used for section headers within the quadrants. These should feel like magazine headlines—commanding and unavoidable.
*   **Body (Plus Jakarta Sans/Poppins, 1rem):** Provides the necessary breathing room. Use `on_surface_variant` (`#e4beb3`) for secondary body text to reduce visual noise while maintaining readability.
*   **Typography Hierarchy:** The massive scale contrast between Display and Body text is what prevents the site from looking like a template. Don't be afraid of the "Empty Space" created by small body text next to giant headers.

---

## 4. Elevation & Depth
In this design system, "Elevation" is a game of light and tone, not shadows.

*   **The Layering Principle:** Stacking is the primary tool. To lift a "Portfolio Case" card, place it on a `surface-container-lowest` base. The "lift" comes from the tonal shift.
*   **Ambient Shadows:** If a shadow is required for a floating "Contact" button, use a deeply diffused shadow: `box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5)`. Never use pure black shadows; always tint them with a hint of the background hue.
*   **The "Ghost Border" Fallback:** For input fields or secondary buttons where a container is required, use a "Ghost Border": `outline-variant` at 15% opacity. This defines the edge without creating a visual "cage."
*   **Glassmorphism:** Navigation menus should utilize a 12px blur with a 60% opaque `surface_container_high`. This makes the layout feel integrated and sophisticated.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` background with `on_primary` text. `0px` border radius. On hover, use a slight vertical shift (2px up) rather than a color change.
*   **Secondary:** `Ghost Border` (outline-variant 20%) with `primary` text. No background color.

### Quadrant Cards
*   **Structure:** No borders. Background: `surface-container`.
*   **Interaction:** On hover, the background should transition to `surface-container-high`.
*   **Content:** Portfolio images should occupy 100% of the card width, with typography overlaid in a glassmorphic footer.

### Input Fields
*   **Style:** Underline only (2px `outline-variant`). No 4-sided boxes. 
*   **Focus State:** The underline transitions to `primary` (`#F04D07`).

### Portfolio Case Study (Custom Component)
*   A "Split-Screen" layout where the left 50% is a "Sticky" image and the right 50% is a scrolling quadrant of details (Academic Background, Professional Experience). This breaks the horizontal rhythm of a standard scroll.

---

## 6. Do's and Don'ts

### Do:
*   **Use Intentional Asymmetry:** If a text block is on the left in one quadrant, push it to the right in the next.
*   **Embrace the Dark:** Keep 90% of the UI in the `surface` and `surface-container` tiers. Let the primary orange be the "flashlight" that guides the user's eyes.
*   **Leverage High-Impact Visuals:** Treat João’s photo and portfolio work as the main UI elements. The interface is just the frame.

### Don't:
*   **No Rounded Corners:** Any `border-radius` above `0px` will break the "Editorial Brutalist" aesthetic.
*   **No Standard Grids:** Avoid the "Bootstrap" look. If the quadrants feel too perfect, overlap a headline across two sections to break the line.
*   **No High-Contrast Dividers:** Never use `#ffffff` or high-opacity lines to separate content. Use the Spacing Scale (Token 16 or 20) to create separation through "Void."