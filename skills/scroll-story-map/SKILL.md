---
name: scroll-story-map
description: Implement or refine a travel-story map synchronized with reading chapters, route progress, and camera focus. Use for scroll linkage, marker navigation, camera jitter, framing, and map interaction; exclude creating travel facts or changing route provenance.
---

# Scroll Story Map

Trace the existing map framework, route geometry, reading state, and container layout. Preserve the route data and requested stop zoom or free-map mode. Fix shared logic instead of hardcoding offsets for individual destinations.

## Reading and route state

Use one reading state to drive chapter navigation, active markers, route progress, and URL hash. Prefer `IntersectionObserver` with cached section geometry. Invalidate cached measurements when relevant content, fonts, or viewport dimensions change.

For the complete-route narrative pattern, display the entire route on first entry as a subdued dashed base layer, with completed segments as a solid overlay. Reuse geometry and existing layers where possible. Refreshing a chapter hash should select the corresponding stop; route-node and chapter-link clicks should navigate to the same section.

## Camera and framing

- Diagnose apparent horizontal displacement by checking container bounds, content occlusion, transforms, map padding, and bounds fitting. Calculate the visible map area from the current layout; avoid a fixed pixel offset for every screen.
- Keep the camera steady while the route marker advances inside a safe visible area. Ease the minimum necessary pan when it leaves that area, and perform a deliberate focus/zoom when the reader reaches a new stop.
- Avoid repeatedly interrupting an active camera animation for small progress changes. Let it finish, then apply the latest reading target. Handle fast forward and backward scrolling without queued obsolete movements.
- Focus on the stop coordinate when arriving. Use the route-progress coordinate for travel between stops. Preserve the user's chosen arrival zoom and adjust its strength only within the requested scope.
- In reduced-motion mode, apply the correct final camera and route state without animation. Clean up observers, listeners, frames, and map instances when the page unloads or component unmounts.

## Interaction and verification

Keep page scrolling available until the reader intentionally activates map controls. Provide an explicit exit and preserve keyboard focus. On narrow touch screens, use the site's vertical story and route view; closing the map should restore reading position.

In a matching Zero-4 / Mountain Story checkout, map behavior lives in `mountain-story/dist/app.js`, `reading-state.js`, `map-layout.js`, and `route-geometry.js`; layout and blending also involve `journey-narrative.css`. Use the current map library. Existing checks include `tests/reading.test.cjs` and `tests/map-layout.test.cjs`.

Verify initial overview, chapter hashes, route clicks, fast scrolling in both directions, stop zoom, manual controls, and reduced motion. Inspect one desktop and one mobile width when the interaction changes. Separate logic-test results from actual browser/map-tile verification. Publishing is outside this skill unless explicitly requested.
