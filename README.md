# measurewise-privacy

The public, hosted privacy policy for MeasureWise, an offline kitchen
measurement converter app (Android and iOS).

This repository contains only the static, self-contained HTML page for that
policy - no application source code, no build tooling, no dependencies.
`index.html` is served directly by GitHub Pages.

## Source of truth

This page is **not** hand-written. It is a mechanical rendering of a single
canonical source that lives in the main MeasureWise application repository:

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

Do not edit `index.html` by hand. Instead, in the MeasureWise app repository:

1. Edit `src/features/privacy/policyContent.json`.
2. Run `node scripts/generate-privacy-policy.js` and `node scripts/generate-privacy-site.js`.
3. Copy the freshly generated `site/index.html` (and `.nojekyll`, if not already present) into this repository.
4. Commit and push here. GitHub Pages redeploys automatically.

## Contact

measurewise.support@gmail.com
