# deck-tools

UI components for Renovus Capital's internal deck-building workflow.

## outline-widget.js

A standalone, dependency-free slide-outline editor. Exposes one global,
`renderOutline(spec, mountId?)`, which renders an editable outline (cards,
drag-to-reorder, layout picker) into the given element.

This file contains **UI code only**. Slide specs (deal content) are passed
in at runtime by the calling environment and are never stored in, or
transmitted to, this repository or the CDN.

Served via jsdelivr:

    https://cdn.jsdelivr.net/gh/<org>/deck-tools@<tag>/outline-widget.js

Always pin to a release tag. Do not point consumers at a branch.

## Releasing a new version

1. Regenerate from the skill: `python3 scripts/build_widget_js.py --out outline-widget.js`
2. Commit, then create a new tag/release (e.g. `v1.0.1`).
3. Update `CDN_WIDGET_URL` in the skill's `scripts/outline.py` to the new tag.
