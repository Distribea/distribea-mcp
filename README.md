# Distribea MCP

On-brand website imagery, generated straight into your codebase.

Plug this MCP into your coding tool (Claude Code, Cursor…) and every page you
build ships with **ultra-realistic, style-locked images**: one consistent art
direction across the whole site, recurring characters with the **same face in
every scene**, believable UGC-style avatars for review sections, plus logo,
favicon pack and og:image, all delivered as optimised WebP with proper ALT
text, patched directly into your code.

The heavy lifting (art direction, generation, billing) runs on the hosted
Distribea engine. This package is only the local connector: it scans and
patches **your** files, and contains no API keys and no secrets.

## Setup

A [Distribea](https://distribea.com) subscription is required.

1. Get your personal key on <https://distribea.com/account/mcp>
2. Paste the ready-made block into the `.mcp.json` at the root of your project:

```json
{
	"mcpServers": {
		"distribea-mcp": {
			"command": "npx",
			"args": ["-y", "distribea-mcp@latest"],
			"env": {
				"DISTRIBEA_MCP_KEY": "dmcp_…"
			}
		}
	}
}
```

3. Build your pages with `<img src="https://placehold.co/1200x600">` markers,
   then ask your agent for the images, one `make_images` call dresses the
   whole page.

## Tools

| Tool | What it does |
|---|---|
| `make_images` ⭐ | Fill every placeholder/stock slot of a page (or the whole project) with on-brand images, in parallel, or rebrand existing images in place (`rebrand: true`) |
| `generate_image` | One on-brand image (auto-switches to UGC selfie mode for review avatars) |
| `edit_image` | Retouch, redo, remove background, upscale ×4, extend |
| `site_style` | Lock, refine or anchor the site's visual identity |
| `brand_pack` | Logo + favicon pack + og:image in one call |
| `create_reference` | Lock a recurring character (real photo supported) or product |
| `finish_images` | Fix missing ALT texts + convert heavy images to WebP (free) |
| `pack_status` | Current style, characters, credits |

## Notes

- Generations are billed in credits on your Distribea plan; every batch is
  quoted in credits before it starts.
- Your project files never leave your machine except the specific images you
  ask to edit.

© Distribea, <https://distribea.com>
