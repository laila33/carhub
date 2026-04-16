# Design System Document: Premium Automotive Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Ethereal Showroom"**

This design system is engineered to elevate EWAN ALMUTAMAIZ GENERAL TRADING from a standard marketplace to a high-end digital concierge. We are moving away from the "grid-of-boxes" commodity feel. Instead, we treat the screen as a curated gallery space. 

The system utilizes **Intentional Asymmetry** and **Tonal Depth** to guide the eye. By leveraging extreme whitespace and overlapping elements (e.g., a car silhouette breaking the container of a card), we create a sense of motion and prestige. The "Ethereal Showroom" philosophy dictates that the interface should feel like light reflecting off polished chrome—airy, precise, and undeniably premium.

---

## 2. Colors: Tonal Architecture
We utilize a Material 3-inspired palette but apply it with an editorial lens. Our primary engine is the interplay between the crisp `primary-container` (#00AEEF) and the depth of our `surface` tiers.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be defined solely through background color shifts. 
*   **Example:** A `surface-container-low` section should sit directly against a `surface` background. The shift in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use "Tonal Stacking" to create depth:
*   **Base Layer:** `surface` (#f5faff) – The vast, open floor.
*   **Section Layer:** `surface-container-low` (#eff4fa) – To group related car categories.
*   **Active Layer:** `surface-container-lowest` (#ffffff) – For interactive cards that need to "pop" forward.

### The Glass & Gradient Rule
To prevent the UI from feeling "flat," use Glassmorphism for floating navigation bars or filter overlays.
*   **Token:** `surface` at 70% opacity + 20px Backdrop Blur.
*   **Signature Texture:** Use a subtle linear gradient from `primary` (#00658d) to `primary-container` (#00aeef) at a 135-degree angle for primary CTAs. This mimics the "specular highlight" found on luxury paintwork.

---

## 3. Typography: The Editorial Voice
Our typography pairing balances the technical precision of **Inter** with the architectural character of **Manrope**.

| Level | Token | Font | Size | Character |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Manrope | 3.5rem | High-impact headlines for hero car features. |
| **Headline** | `headline-md` | Manrope | 1.75rem | Section titles (e.g., "New Arrivals"). |
| **Title** | `title-lg` | Inter | 1.375rem | Car model names in card views. |
| **Body** | `body-lg` | Inter | 1rem | Technical specifications and descriptions. |
| **Label** | `label-md` | Inter | 0.75rem | Metadata like "Mileage" or "Fuel Type." |

**Design Note:** Use `display` styles with tight letter-spacing (-0.02em) to evoke a fashion-magazine aesthetic.

---

## 4. Elevation & Depth: Tonal Layering
We replace structural lines with light and shadow.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section to create a soft, natural lift without a shadow.
*   **Ambient Shadows:** Use only when elements "float" (e.g., a sticky "Contact Dealer" mobile bar). 
    *   *Spec:* `Y: 20px, Blur: 40px, Color: on-surface @ 6%`.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., search inputs), use `outline-variant` (#bdc8d1) at **15% opacity**. Never use 100% opaque lines.
*   **Glassmorphism:** Apply to headers and floating action buttons to allow car imagery to bleed through, softening the edges of the UI.

---

## 5. Components: Style Guide

### Buttons
*   **Primary:** Gradient (`primary` to `primary-container`), `lg` (2rem) border-radius. No shadow.
*   **Secondary:** `surface-container-high` background with `on-surface` text.
*   **Tertiary:** Ghost style. `on-surface` text with an underline that appears only on hover.

### Cards (The "Showroom Hero")
*   **Radius:** `lg` (2rem).
*   **Padding:** `xl` (3rem) to ensure the car imagery has "breathing room."
*   **Rule:** Forbid divider lines. Use vertical whitespace (32px+) to separate the car name from the price.

### Inputs & Search
*   **Style:** `surface-container-highest` background.
*   **Radius:** `full` (9999px) for search bars to create a sleek, aerodynamic feel.
*   **Focus State:** A soft 4px glow of `primary-fixed-dim` (#82cfff) instead of a hard border.

### Contextual Components for EWAN ALMUTAMAIZ
*   **Spec-Glance Chips:** Use `secondary-container` with 12px padding for engine specs.
*   **Trust Badge:** A glass-morphic floating badge for "Verified Luxury" status.

---

## 6. Do's and Don'ts

### Do
*   **DO** use extreme whitespace. If you think there is enough space, add 16px more.
*   **DO** overlap elements. Let the front wheel of a car image slightly break the top boundary of its description container.
*   **DO** use "Sky Blue" (`primary-container`) as a surgical accent—for icons, prices, and active states only.

### Don't
*   **DON'T** use black (#000000) for text. Use `on-surface` (#171c20) for a softer, more expensive feel.
*   **DON'T** use 1px dividers to separate list items. Use a 1-step tonal shift in background color or 24px of empty space.
*   **DON'T** use standard "drop shadows." If it looks like a shadow, it’s too dark. It should look like a "glow of depth."