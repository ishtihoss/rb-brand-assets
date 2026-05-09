# rb-brand-assets

Ritchie Bros. brand reference assets used by the [rb-presentation MCP server](https://github.com/ishtihoss/rb-presentation-builder). Published as `@ishtihoss/rb-brand-assets` on npm so Claude Desktop's pptx skill can fetch them via `npm install` from inside its network-sandboxed code-execution environment — `registry.npmjs.org` is on the sandbox allowlist; `raw.githubusercontent.com` and other CDN-style hosts are not (verified empirically 2026-05-08).

## Contents

- `RB-Overview.pptx` — populated reference deck. Used as the visual template by Claude Desktop's pptx skill when composing RB-branded slides.
- `brand_guidelines.md` — hard + soft brand rules (color palette, typography, tone, image style).

## Usage from inside the pptx skill

The MCP tool `get_rb_brand_context` returns install instructions in its response. The flow is:

```bash
npm install @ishtihoss/rb-brand-assets
# the pptx is now at node_modules/@ishtihoss/rb-brand-assets/RB-Overview.pptx
```

Claude reads the .pptx from there and uses it as the visual template for slide composition.

## Publishing a new version

After pushing a brand update:

```bash
cd rb-brand-assets
npm version patch    # or minor / major
npm publish --access public
git push --follow-tags
```

The git repo is the source of truth; npm publishes from whatever's checked in locally.
