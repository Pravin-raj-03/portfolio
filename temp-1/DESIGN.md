# Design System: The Obsidian Terminal

## 1. Overview & Creative North Star
The Creative North Star for this system is **"The Obsidian Terminal."** This is not a standard "dark mode" website; it is a high-end, editorialized command center for an AI/ML Engineer. It bridges the gap between the raw utility of a kernel terminal and the sophisticated layout of a premium architectural journal.

To break the "template" look, we lean into **Intentional Asymmetry**. Rather than perfectly centered grids, we use heavy left-aligned typography contrasted with expansive negative space on the right. We utilize "glitch" offsets where elements are slightly shifted off-axis to suggest a living, processing system. The experience should feel like looking through a high-resolution viewport into a deep-space data core: cold, precise, and undeniably powerful.

## 2. Colors & Surface Logic
The palette is strictly monochrome. This constraint is our greatest strength, forcing us to use tonal depth rather than color to guide the eye.

### The "No-Line" Rule
Traditional 1px solid borders for sectioning are strictly prohibited. Boundaries between major content blocks must be defined through **Background Color Shifts**. For example, a project case study should transition from `surface` (#131313) to `surface-container-low` (#1B1B1B) to define a new context without the "boxed-in" feel of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of obsidian sheets. Use the `surface-container` tiers to create optical depth:
*   **Level 0 (Base):** `surface-container-lowest` (#0E0E0E) for the deep background.
*   **Level 1 (Sections):** `surface` (#131313) for primary content areas.
*   **Level 2 (Cards/Modules):** `surface-container-high` (#2A2A2A) for elevated data modules.

### The "Glass & Scanline" Rule
To add "soul," use `surface-variant` (#353535) with a `backdrop-blur` of 12px-20px for floating navigation or overlays. Overlay a subtle, 2% opacity repeating linear-gradient "scanline" texture over the entire viewport to ground the digital terminal aesthetic.

## 3. Typography
The typography scale creates a tension between technical precision and editorial authority.

*   **The Display Scale:** Uses `Space Grotesk`. It is wide, aggressive, and high-contrast. Use `display-lg` (3.5rem) for hero statements, kerned tightly (-0.05em) to feel like a heavy machine-stamped serial number.
*   **The Interface Scale:** Uses `Inter` for all body copy (`body-md`, `body-lg`). This ensures that complex AI/ML documentation remains readable and professional.
*   **The Technical Scale:** All labels (`label-sm`), code snippets, and metadata must use a Monospace font. This is the "voice" of the machine. Use `on-surface-variant` (#C6C6C6) for these to differentiate them from human-readable content.

## 4. Elevation & Depth
In a monochrome world, elevation is whispered, not shouted.

*   **Tonal Layering:** Avoid shadows for standard components. If a card needs to pop, move from `surface` to `surface-container-highest` (#353535). 
*   **Ambient Shadows:** For floating modals, use a massive, diffused shadow: `0px 40px 100px rgba(0, 0, 0, 0.8)`. It shouldn't look like a shadow; it should look like the element is casting a "void" onto the layer beneath it.
*   **The "Ghost Border" Fallback:** If a technical separator is required (e.g., in a complex data table), use `outline-variant` (#474747) at 20% opacity. It should be barely perceptible—a "ghost" of a line.

## 5. Components

### Buttons
*   **Primary:** `on-primary-fixed` (#FFFFFF) background with `on-primary` (#1A1C1C) text. Shape: strictly 0px radius. Hover state: Inverse to `primary-container` (#D4D4D4).
*   **Secondary:** `outline` (#919191) ghost border, monospace text. 
*   **Tertiary:** Text only, prefixed with a `>` character (e.g., `> EXECUTE_QUERY`).

### Input Fields
*   **Default:** No background. Only a bottom-border using `outline-variant`.
*   **Focus:** A subtle `surface-container-highest` background fill with a blinking 2px vertical cursor at the end of the label.

### Cards & Lists
*   **Strict Rule:** No dividers. Use `spacing-8` (1.75rem) to separate list items. 
*   **ASCII Accents:** Use characters like `[ ]`, `::`, or `//` from the typography scale to denote interactivity or status instead of rounded icons.

### Charts & ML Visualizations
*   All charts must use the monochromatic scale. Use `primary` (#FFFFFF) for the "active" data line and `surface-variant` (#353535) for grid lines. 
*   Use stippling (dots) or cross-hatching textures instead of solid grey fills to represent different data sets.

## 6. Do's and Don'ts

### Do
*   **DO** use extreme white space. A single code snippet in the center of a `surface-container-lowest` section feels more premium than a cluttered grid.
*   **DO** use 0px border-radii for everything. Hard corners convey the "Obsidian" hardness.
*   **DO** use monospace fonts for "system" information (dates, tags, file sizes).

### Don't
*   **DON'T** use 100% white (#FFFFFF) for long-form body text; use `on-surface` (#E2E2E2) to reduce eye strain against the black background.
*   **DON'T** use shadows to define cards; use background color shifts.
*   **DON'T** use standard "Material" icons. Use custom SVG paths with sharp strokes or ASCII characters.