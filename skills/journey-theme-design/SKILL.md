---
name: journey-theme-design
description: Create or refine destination-specific visual themes within a shared travel-journal design system. Use for theme colors, map palettes, background blending, textures, and image treatment; exclude journey facts and route/camera logic.
---

# Journey Theme Design

Inspect the active theme configuration, CSS variables, and affected page before choosing colors. Preserve the shared logo, navigation, typography proportions, component dimensions, and reading structure. Express the destination through theme data instead of a separate set of page components.

## Theme changes

- Keep colors, texture choices, image treatment, and optional motion parameters together in theme configuration. Make each CSS effect read those values; avoid destination names embedded in shared layout logic.
- Separate decorative accent colors from readable accent text. Check actual body, caption, link, marker, and map-label contrast on the backgrounds where they appear.
- Blend content and map backgrounds with related theme colors and a broad, even transition. Keep the reading surface sufficiently opaque behind text and preserve route, marker, and control contrast. Adjust the theme palette before introducing overlays or filters.
- Derive destination atmosphere from relevant geography and supplied imagery. Use abstract, restrained textures. Only introduce a specific landform or cultural motif when the journey supports it.
- Treat photo color adjustments as display effects. Preserve source images and do not conceal missing real imagery with unlabelled stand-ins.
- Keep existing motion optional and honor reduced motion. A color-only request should not alter layout, camera behavior, cursor interaction, or page transitions.

## Zero-4 / Mountain Story adapter

For a matching checkout, inspect `mountain-story/dist/journey-themes.js`, `journey-regional-theme.js`, and `journey-theme.js` for the theme source and variable mapping. Relevant presentation files include `journey-theme.css` and `journey-narrative.css`. Values such as `accentText`, `onSurface`, `surfaceMuted`, and map colors have different readability roles; preserve those distinctions.

Regional stage palettes may interpolate as the journey progresses. Change them without modifying geographic data or abruptly switching the shared brand shell. Ordinary theme updates should not edit journey records or route JSON.

Run existing theme/contrast checks where available and inspect the affected theme at one desktop and one mobile width. Check actual rendered text and map legibility; report any missing visual verification. Upload or deployment requires a separate user request.
