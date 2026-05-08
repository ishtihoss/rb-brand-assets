# rb-brand-assets

Public mirror of Ritchie Bros. brand assets used by the [rb-presentation MCP server](https://github.com/ishtihoss/rb-presentation-builder).

These files are exposed publicly so Claude Desktop's pptx skill (which runs in a network-sandboxed code-execution environment with a strict domain allowlist) can fetch them via `raw.githubusercontent.com` without per-chat allow prompts.

- `RB-Overview.pptx` — populated reference deck. Used as the visual template by Claude Desktop's pptx skill when composing RB-branded slides.
- `brand_guidelines.md` — hard + soft brand rules (color palette, typography, tone, image style).

Updated when the brand evolves. The MCP tool `get_rb_brand_context` returns raw URLs into this repo.
