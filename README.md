# measurewise-privacy

The public, hosted privacy policy for **Culiquant**, an offline kitchen
measurement converter app (Android and iOS).

**Note on this repository's name and URL**: this repo (and therefore its
`github.io/measurewise-privacy/` URL) was created under the product's
previous name, MeasureWise. The product has since been renamed to
**Culiquant**. The repository name and URL path are being kept unchanged
deliberately, since the live URL is already configured in Google Play - only
the page *content* has been updated to say Culiquant. See the app
repository's rebrand decision record for the rename rationale. A cleaner,
Culiquant-named URL is possible as optional future cleanup, but release
readiness does not depend on it.

This repository contains only the static, self-contained HTML page for that
policy - no application source code, no build tooling, no dependencies.
`index.html` is served directly by GitHub Pages.

## Source of truth

This page is **not** hand-written. It is a mechanical rendering of a single
canonical source that lives in the main Culiquant application repository
(technical repo/directory name: `measurewise`, unchanged from before the
rebrand - see that repo's own rebrand decision record for why the technical
identifiers were intentionally left alone):

```
src/features/privacy/policyContent.json
```

Two generators read that same JSON file and produce two outputs that are
guaranteed to stay substantively identical:

- `scripts/generate-privacy-policy.js` -> `docs/PRIVACY_POLICY_PUBLIC.md` (markdown copy in the app repo)
- `scripts/generate-privacy-site.js` -> `site/index.html` (the file published here)

The app itself also has a native, fully offline-readable Privacy Policy
screen (More -> About -> Privacy Policy) that reads the identical JSON
source directly.

## Updating this page

Do not edit `index.html` by hand. Instead, in the Culiquant app repository:

1. Edit `src/features/privacy/policyContent.json`.
2. Run `node scripts/generate-privacy-policy.js` and `node scripts/generate-privacy-site.js`.
3. Copy the freshly generated `site/index.html` (and `.nojekyll`, if not already present) into this repository.
4. Commit and push here. GitHub Pages redeploys automatically.

## Contact

measurewise.support@gmail.com
