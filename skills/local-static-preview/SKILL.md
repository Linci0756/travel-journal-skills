---
name: local-static-preview
description: Start or recover an existing static website's localhost preview and verify the page it serves. Use when a local URL fails, a preview process stops, or static routing/assets fail; exclude public hosting and website redesign.
---

# Local Static Preview

Find the project's existing preview command and determine which directory is actually served. Use its routing rather than starting an unrelated server on another port.

## Diagnose before restarting

Check the target port, owning process, HTTP response, and relevant server output. Distinguish an absent process, a listening process that resets connections, a routing/asset error, and a browser-side access failure. A connection failure alone does not justify website code changes.

If a restart is needed, confirm the process belongs to this project and stop only that process. Preserve the current host binding and port where practical. Keep local-only services bound to loopback; do not expose the site publicly as a recovery step.

Choose a process lifetime appropriate to the request. A preview needed beyond the current task must not depend on a tool session that will end. Use the platform's available process management, and disclose whether the service survives logout or restart. Do not silently configure login startup when the user only requested a current preview.

## Verify recovery

Check the exact page URL and a required asset or data endpoint. Then reload the page in a supported browser and inspect a clear rendering signal. HTTP 200 establishes server response, not successful page execution. If browser access is blocked, report that limitation without bypassing the restriction or repeatedly replacing the server.

For the matching Zero-4 checkout, `kuangye-home/dev_server.py` serves the homepage and sibling `mountain-story/dist` journals on one origin. Its default port is 8765; journals use `/journal/<slug>.html`, with data under `/journal/journeys/`. The server compares the home and journal catalog slugs at startup. Inspect catalog consistency if startup reports an error.

Report the observed cause, recovered URL, and verification scope. A localhost recovery does not authorize deployment, access changes, or unrelated website edits.
