# Material 3 Expressive Design Guidelines

This document serves as the source of truth for AI/LLM agents and developers building Android applications utilizing the **Material 3 (M3) Expressive** design system.

M3 Expressive is an evolution of Material You, focusing on creating more emotionally impactful, personal, and adaptive user experiences through enhanced visual hierarchy, dynamic scaling, and fluid interactions.

---

## 1. Core Principles & Expressive Tactics

Material 3 Expressive introduces four primary axes to add personality and guide user attention:

1.  **Vibrant Color:** Uses dynamic color bolderly with expanded palettes and higher contrast. 
    *   *Tactic:* Use high contrast between primary, secondary, and tertiary roles to sharpen navigation hierarchy.
2.  **Expressive Typography:** Embraces variable fonts for "editorial-like" layouts.
    *   *Tactic:* Use "Emphasized" styles to create hero moments and reinforce information density for critical actions.
3.  **Intentional Motion:** Implements physics-based "springy" animations.
    *   *Tactic:* Differentiate between **Spatial Springs** (for natural movement of elements) and **Effects Springs** (for seamless transitions in color and opacity).
4.  **Contrasting Shapes:** Employs a library of 35+ shapes.
    *   *Tactic:* Mix rounded and square corner radii to create **visual tension**. Break from the surrounding shape style to draw attention to a specific hero element.

---

## 2. Strategic Shape Usage

Shape is a communication tool, not just a container. 

### Visual Hierarchy & Tension
*   **Create Contrast:** Mix "classic" rounded shapes with "abstract" or more squared silhouettes to create visual tension. A unique silhouette helps an element stand out from a sea of uniform containers.
*   **Shape Morphing:** Use built-in morphing animations to transition between geometries (e.g., a circle morphing into a rounded rectangle).

### The "Importance" Rule (Do vs. Caution)
*   **Do:** Break from the surrounding shape style to draw attention. Use larger, more distinct shapes for primary actions.
*   **Caution:** Avoid using smaller shapes for essential actions. Smaller visual containers can result in critical actions appearing less important to the user.

---

## 3. Typography System

The M3 Expressive type scale expands from the standard 15 styles to **30 styles** by introducing an **"Emphasized"** variant for every baseline style.

*   **Variable Fonts:** Utilize variable fonts (like Roboto Flex) to seamlessly adjust weight and letter spacing.
*   **Emphasized Styles:** These styles use a higher font weight (typically Medium or Bold) and decreased letter spacing compared to their baseline counterparts to establish a stronger visual hierarchy.

### Type Scale Metrics (Baseline)

| Role | Size (Large) | Size (Medium) | Size (Small) | Key Characteristics & Usage |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | 57sp | 45sp | 36sp | Short, critical text; expressive fonts recommended. |
| **Headline** | 32sp | 28sp | 24sp | High-emphasis text on smaller screens. |
| **Title** | 22sp | 16sp | 14sp | Medium-emphasis text for section headers. |
| **Body** | 16sp | 14sp | 12sp | Standard paragraph text; 1.5x line-height recommended. |
| **Label** | 14sp | 12sp | 11sp | Smallest text for captions, tags, and fine print. |

*Agent Directive:** Always apply the appropriate typography token. When primary actions or critical data need highlighting, switch to the "Emphasized" variant of the respective role rather than manually overriding font weights.

---

## 3. Component Dimensions (The XS to XL Scale)

M3 Expressive introduces a standardized 5-size range for interactive components (buttons, icon buttons, chips), replacing the "one size fits all" approach.

### Sizing Scale

| Size | Container Height | Recommended Padding | Use Case |
| :--- | :--- | :--- | :--- |
| **XS (Extra Small)** | 32dp | 12dp | Dense layouts, secondary actions, tooltips. |
| **S (Small)** | 40dp | 16dp | Default size for most mobile apps. |
| **M (Medium)** | 48dp | 20dp | High-visibility actions, larger screens. |
| **L (Large)** | 56dp | 24dp | Hero moments, primary call-to-actions, FABs. |
| **XL (Extra Large)** | 64dp | 32dp | Immersive platforms, extreme emphasis. |

### Accessibility Rule: Touch Targets
Regardless of the visual container size (e.g., an XS button of 32dp height), the interactive touch target area **MUST** maintain a minimum of **48dp x 48dp**. Use internal padding or `TouchTargetExpansion` modifiers to ensure accessibility compliance.

---

## 4. Shape and Corner Radii

The shape system consists of **10 levels of roundedness**, allowing components to morph contextually (e.g., a button expanding into a menu).

| Token Name | Radius (dp) | Typical Component Usage |
| :--- | :--- | :--- |
| **None** | 0dp | Full-screen containers. |
| **Extra Small** | 4dp | XS Button inner corners, Tooltips. |
| **Small** | 8dp | S/M Button inner corners, Chips. |
| **Medium** | 12dp | Cards, Menus. |
| **Large** | 16dp | L Button inner corners, standard FABs. |
| **Large Increased** | 20dp | XL Button inner corners. |
| **Extra Large** | 28dp | Dialogs, Bottom Sheets. |
| **Extra Large Inc.** | 32dp | Large Dialogs. |
| **Extra Extra Large**| 48dp | Hero containers. |
| **Full** | 100% / Full | Default for standard standalone Buttons and FABs. |

---

## 5. Component Selection & Usage Guide

Select components based on the desired **visual weight** and **interaction priority** to maintain a clear hierarchy.

### A. Buttons (Action Priority)
*   **Filled Button:** **High Emphasis.** Primary, final actions (e.g., "Save", "Submit"). Use for the "happy path".
*   **Tonal Button:** **Medium Emphasis.** Secondary actions that need visibility but shouldn't compete with the primary button (e.g., "Add to Cart").
*   **Elevated Button:** **High Emphasis (Busy backgrounds).** Use when the background is complex or colorful to ensure the button remains prominent.
*   **Outlined Button:** **Medium-Low Emphasis.** For important but non-primary actions, or when multiple actions of equal weight are shown together (e.g., "Edit Profile").
*   **Text Button:** **Low Emphasis.** For auxiliary actions like "Cancel", "Learn More", or within cards/dialogs to minimize clutter.

### B. Cards (Content Grouping)
*   **Filled Card:** Subtle separation. Best for grouping related content without high visual noise.
*   **Elevated Card:** High interaction cue. Use when a card should feel "lifted" and distinct from the background.
*   **Outlined Card:** Clean and minimal. Best for displaying many items (e.g., a product grid) where shadows would create too much visual "weight".

### C. Floating Action Buttons (FAB - The Hero Action)
*   **Small FAB:** Secondary actions or space-constrained layouts.
*   **Regular FAB:** The default for the screen's most important action (e.g., "Compose").
*   **Large FAB:** Hero actions on large screens or extremely critical "centerpiece" actions.
*   **Extended FAB:** Use when the icon's meaning requires a text label or when you need maximum prominence.

### D. Chips (Contextual Actions & Tags)
*   **Assist Chip:** Triggers a related utility (e.g., "Add to Calendar").
*   **Filter Chip:** Toggles content visibility (Selected/Unselected states).
*   **Input Chip:** Represents complex data in a compact form (e.g., email tags).
*   **Suggestion Chip:** AI/System-generated hints (e.g., "Reply 'Yes'").

### E. Navigation (Destination Density)
*   **Navigation Bar (Bottom):** **3-5** top-level destinations. Standard for mobile.
*   **Navigation Rail (Side):** **3-7** destinations. Ideal for tablets/landscape.
*   **Navigation Drawer (Modal/Standard):** **5+** destinations. Best for complex apps or secondary utilities (Settings, Help).

### F. Feedback & Overlays
*   **Dialogs:** **Interruptive.** Use for critical confirmation (e.g., "Delete forever?").
*   **Bottom Sheets:** **Supplementary.** For additional options or menus that don't need a full screen.
*   **Snackbars:** **Non-interruptive.** Short feedback messages (e.g., "Sent").

---

## 6. New Expressive Components

Implement these specific component structures when building M3 Expressive interfaces:

1.  **Button Groups:** Used to organize related buttons.
    *   **Spacing:** Use a **2dp inner padding/gap** between connected items.
    *   **Interaction:** Buttons should "bump" and react (shape morph) to each other when pressed.
2.  **Split Buttons:** A dual-action button featuring a primary action paired with a connected menu toggle.
    *   **Spacing:** Requires a **2dp gap** between the primary action area and the dropdown/menu toggle area.
3.  **Flexible Toolbars:** Replaces or supplements traditional Bottom App Bars. Available in docked or floating variants, adapting to display frequently used actions. Often paired contextually with a FAB.
4.  **FAB Menu:** Replaces the legacy "speed dial" pattern with a more integrated, shape-morphing menu that expands fluidly from the FAB.
5.  **Loading Indicators:** Utilize `LoadingIndicator` and `ContainedLoadingIndicator` that morph between geometric shapes during progress, providing engaging, continuous motion rather than static spinners.

---

## 6. Container Strategy & Surfaces

Use surface tones and varying elevation levels (often achieved via color rather than shadow in M3) to create distinct containers for content.

*   **Content Grouping:** Use different surface containers to group related information.
*   **Emphasis through Color:** Apply more vibrant surface tones to hero containers to draw immediate attention.
*   **Dynamic Containers:** Containers should react to content density; use flexible layouts that adapt while maintaining consistent inner padding.

---

## 7. Intentional Motion & Interaction

Motion is a functional requirement, not just decoration.

*   **Spatial Springs:** Use for movement, scaling, and physical interaction. These should feel "heavy" and tactile.
*   **Effects Springs:** Use for transitions in non-spatial properties like color, opacity, and shape-morphing.
*   **Tactile Feedback:** Couple haptic feedback with visual spring animations (e.g., a "bump" effect when reaching the end of a list or selecting an item in a Button Group).
*   **Shape Morphing:** Animate corner radii transitioning between tokens (e.g., Full to Medium) rather than just fading in the new component.

---

## 8. Directives for LLM Agents

When generating Jetpack Compose code for M3 Expressive:

1.  **Strict Token Usage:** ALWAYS use the `MaterialTheme` object. NEVER hardcode sizes or colors.
2.  **Strategic Shape Variety:** When building hero sections, intentionally mix shape tokens (e.g., use a `Medium` rounded container for secondary items but a `Full` or `Large` squared silhouette for the primary CTA) to create visual tension.
3.  **Spring-Based Motion:** Prefer `spring()` animation specs over `tween()`. Use appropriate stiffness/damping ratios to differentiate between **Spatial** and **Effects** springs.
4.  **Emphasized Typography:** Default to "Emphasized" tokens for headers and primary action labels.
5.  **Accessibility First:** Ensure the 48dp touch target for all XS/S sized components using `Modifier.minimumInteractiveComponentSize()`.
6.  **Hierarchy Check:** Ensure essential actions have larger silhouettes/containers than secondary ones. Avoid the "small shape" pitfall for primary actions.