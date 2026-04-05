# Design System Document: High-End Editorial Storytelling

## 1. Overview & Creative North Star
The "Creative North Star" for this design system is **"The Digital Estate."**

We are not building a generic e-commerce landing page; we are curating a digital gallery for Khesaca Coffee. The system prioritizes the "story" over the "transaction." To break the "template" look, we utilize **Editorial Asymmetry**: placing heavy, high-contrast serif headlines against vast expanses of `surface` (#fcf9f8) whitespace.

Elements should never feel "boxed in." Instead, use overlapping imagery—where a documentary-style photo of coffee cherries might bleed off-center or overlap a text block—to create a sense of organic movement and intentional depth. This is a system built on trust, tradition, and the tactile nature of the Vietnamese Highlands.

---

## 2. Colors
Our palette is rooted in the deep crimson of a ripe coffee cherry and the lush green of the Central Highlands, balanced by a sophisticated neutral foundation. The current theme configuration defines the following:

*   **Primary (`primary_color_hex`: #bf1d22):** This vibrant red is our brand's most distinctive chromatic color, suitable for authoritative headings and key interactive elements.
*   **Secondary (`secondary_color_hex`: #cf4944):** A supporting color for less prominent UI elements and secondary actions, offering a warm complement to the primary.
*   **Tertiary (`tertiary_color_hex`: #0f7008):** An additional accent color, a cool blue, for highlights, badges, or decorative elements like sustainability highlights.
*   **Neutral (`neutral_color_hex`: #8c716e):** A sophisticated mid-tone brown that serves as a base color for backgrounds, surfaces, and non-chromatic elements.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section content. Boundaries must be defined through tonal shifts. For example, a "Heritage" story section might use `surface_container_low` (#f6f3f2) to subtly distinguish itself from the `background` (#fcf9f8).

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper.
- **Base Layer:** `surface`
- **Component Layer:** `surface_container_lowest` (White #ffffff) for cards to create a soft "lift."
- **Nesting:** Place a `surface_container_high` module inside a `surface_container_low` section to highlight a specific detail (like a flavor profile) without adding visual noise.

### The "Glass & Gradient" Rule
To add "soul," avoid flat red blocks. Use a subtle linear gradient from `primary` (#ab0017) to `primary_container` (#d12129) on main CTAs. For floating navigation or over-image cards, use **Glassmorphism**: `surface` at 80% opacity with a `20px` backdrop blur.

---

## 3. Typography
We use a high-contrast pairing to balance Vietnamese heritage with modern professionalism.
The current theme configures:

*   **Display & Headline (`headline_font`: Newsreader):** This serif font is our "voice of tradition." Use `display-lg` (3.5rem) for hero statements. The intentional contrast between the organic serifs and the white space conveys a premium, editorial feel.
*   **Title, Body & Label (`body_font` / `label_font`: Be Vietnam Pro):** A modern, geometric sans-serif that ensures readability and pays homage to the brand's roots.
*   **`body-lg`**: Main storytelling prose.
*   **`label-md`**: Small, all-caps metadata (e.g., "ALTITUDE: 1500M") to create an archival look.

---

## 4. Elevation & Depth
In this design system, depth is felt, not seen. The current theme utilizes a `roundedness` of **1 (Subtle roundedness)**, contributing to a refined, less-is-more aesthetic. The `spacing` is set to **2 (Normal)**, offering a balanced and readable layout.

*   **The Layering Principle:** Achieve hierarchy by "stacking" tones. A `surface_container_lowest` card placed on a `surface` background creates a natural, soft lift.
*   **Ambient Shadows:** If a card must float, use a "Shadow-as-Light" approach. Use the `on_surface` color at 4% opacity with a `48px` blur and `12px` Y-offset. It should feel like a soft glow of natural light, not a digital drop shadow.
*   **The "Ghost Border" Fallback:** If accessibility requires a container edge, use a "Ghost Border": `outline_variant` (#e5bdba) at **15% opacity**. 100% opaque borders are strictly forbidden.

---

## 5. Components

### Buttons
- **Primary:** Gradient from `secondary` to `secondary_container`. High-roundedness (`xl`: 0.75rem). No shadow.
- **Tertiary (Storytelling Link):** No background. `primary` text with a custom 2px underline that animates on hover.

### Cards & Lists
- **Editorial Card:** A combination of a documentary-style image and a `surface_container_lowest` text area. **Forbid the use of divider lines.** Use vertical whitespace (32px - 64px) or a background shift to separate content.
- **Sustainability Chips:** Use `tertiary_fixed` (#90f9aa) backgrounds with `on_tertiary_fixed` (#00210c) text. Use `full` (9999px) roundedness to contrast the structured typography.

### Input Fields
- **Search/Newsletter:** `surface_container_highest` background. No border. On-focus, transition to `surface` with a `Ghost Border` of `primary`.

### Narrative Accordions (FAQs)
- Use `surface_container_low`. Do not use lines. When expanded, the container should shift to `surface_container_high` to visually "embrace" the content.

---

## 6. Do's and Don'ts

### Do:
*   **Use Asymmetric Grids:** Align text to the left and images to the right, but allow images to break the container width for a custom "magazine" feel.
*   **Embrace "Slightly Moody" Imagery:** Photos should have deep shadows and warm, natural light.
*   **Prioritize White Space:** If a section feels crowded, increase the padding by 1.5x the standard scale.

### Don't:
*   **Don't use 1px solid dividers:** It breaks the "premium paper" illusion.
*   **Don't use standard Roboto for headings:** Stick strictly to the typography scale; Newsreader is for emotion, Be Vietnam Pro is for utility.
*   **Don't use high-saturation shadows:** Shadows should never be pure black or grey; they must be tinted with the `on_surface` tone.
*   **Don't center-align long-form text:** Keep it left-aligned to maintain the editorial structure.