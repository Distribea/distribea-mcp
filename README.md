# Distribea MCP

> Brand-aware image generation MCP, powered by Nano Banana Pro — define your
> brand once, every image ships on-brand and production-ready (WebP, SEO alt
> text, placed in your repo). Works with Claude Code, Cursor, Windsurf, Replit,
> Copilot.

Define your brand **once** — art direction, colours, recurring faces, products —
and every page you build ships with on-brand imagery **by default**: one
consistent look across the whole site, recurring characters with the **same face
in every scene**, believable UGC-style avatars for review sections. The engine
runs on **Nano Banana Pro**.

Each image lands production-ready: optimised **WebP**, proper **SEO alt text**,
and **patched straight into your code** — no stock photos, no placeholders, no
manual export step.

The heavy lifting (art direction, generation, billing) runs on the hosted
Distribea engine. This package is only the local connector: it scans and
patches **your** files, and contains no API keys and no secrets.

## See it in action

A plain landing page, dressed with on-brand product imagery in a single
`make_images` call — no stock photos, no placeholders:

<p align="center">
  <img src="https://distribea-categories-images.fra1.cdn.digitaloceanspaces.com/mcp/distribea-before-after-en.gif" width="380" alt="A sneaker store landing page animating from without the MCP (raw photos) to with the MCP (on-brand product imagery)" />
  &nbsp;
  <img src="https://distribea-categories-images.fra1.cdn.digitaloceanspaces.com/mcp/distribea-before-after-feastables.gif" width="380" alt="A chocolate brand landing page animating from without the MCP (raw photos, empty sections) to with the MCP (on-brand imagery in every slot)" />
</p>

> **A/B test:** same prompt, same reference image, same LLM model.

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
| `list_projects` | List your saved projects (brand, products, image count) to find one to reconnect (free) |
| `link_project` | Reconnect the current folder to a saved project so its style/characters/products come back (free) |
| `forget_project` | Wipe the current project's saved memory so it starts fresh (free) |

## Notes

- Generations are billed in credits on your Distribea plan; every batch is
  quoted in credits before it starts.
- Your project files never leave your machine except the specific images you
  ask to edit.

## Privacy Policy

This local connector contains **no API keys and no secrets**. To generate an
image it sends to the hosted Distribea engine only what is needed for the
request:

- **What is sent:** your image brief (the subject/prompt you ask for), a short
  text excerpt of the page being worked on (used to infer the site's style and
  context), a hashed project identifier, and any image file you explicitly ask
  to edit. **Your other project files stay on your machine** — they are never
  read or uploaded.
- **What is stored, tied to your account:** your locked visual style, recurring
  characters/products/avatars, the images generated for you (hosted on
  Distribea's CDN), and your credit/billing usage.
- **Third parties:** images are produced through Distribea's hosted AI
  providers solely to fulfil your request. Your data is **never sold**.
- **Authentication:** calls are authenticated with your personal key
  (`dmcp_…`), issued and revocable at
  <https://distribea.com/account/mcp>.
- **Retention & contact:** data is kept for the life of your account; full
  policy, retention details and contact at
  <https://distribea.com/legal/privacy-policy>.

© Distribea, <https://distribea.com>
