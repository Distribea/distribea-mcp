<div align="center">

# Distribea MCP

### The brand-aware image generation MCP server.<br/>Define your brand once, every image ships on-brand.

[![npm version](https://img.shields.io/npm/v/distribea-mcp?color=2563eb&label=npm)](https://www.npmjs.com/package/distribea-mcp)
[![npm downloads](https://img.shields.io/npm/dm/distribea-mcp?color=2563eb)](https://www.npmjs.com/package/distribea-mcp)
[![MCP registry](https://img.shields.io/badge/MCP-registry-2563eb)](https://registry.modelcontextprotocol.io)
[![GitHub stars](https://img.shields.io/github/stars/Distribea/distribea-mcp?style=social)](https://github.com/Distribea/distribea-mcp/stargazers)

**Works with Claude Code · Cursor · Windsurf · Replit · Copilot**

</div>

<p align="center">
  <img src="https://distribea-categories-images.fra1.cdn.digitaloceanspaces.com/mcp/distribea-before-after-showcase.gif" width="820" alt="Two landing pages, a sneaker store and a chocolate brand, shown full-page side by side, animating in sync from without the MCP to with the MCP, every image slot filled on-brand" />
</p>

<div align="center">

*Same page, one `make_images` call. Every placeholder filled with on-brand imagery. No stock photos, no manual export.*

</div>

---

## What it does

You build a page with `<img src="https://placehold.co/1200x600">` markers wherever an image goes. One call to `make_images` fills every slot with imagery that matches **your** brand: one consistent look across the whole site, recurring characters with the **same face in every scene**, believable UGC avatars for review sections.

Every image lands production-ready: optimised **WebP**, proper **SEO alt text**, and **patched straight into your code**. No stock photos. No placeholders. No export step.

The engine runs on **Nano Banana Pro**. The heavy lifting (art direction, generation, billing) runs on the hosted Distribea engine; this package is only the local connector that scans and patches **your** files. It holds no API keys and no secrets.

## Why not just use a generic image MCP?

| | Stock photos | Generic image-gen MCP | **Distribea MCP** |
|---|:---:|:---:|:---:|
| Matches your brand | ❌ | ⚠️ prompt by prompt | ✅ locked once, applied everywhere |
| Same face across scenes | ❌ | ❌ | ✅ recurring characters |
| Fills a whole page in one call | ❌ | ❌ | ✅ `make_images` |
| Production-ready (WebP + SEO alt) | ❌ | ❌ | ✅ automatic |
| Patched into your code | ❌ | ❌ | ✅ no manual export |
| UGC avatars for reviews | ❌ | ⚠️ | ✅ built in |

## Quickstart (30 seconds)

A [Distribea](https://distribea.com) subscription is required.

**1.** Grab your personal key at [distribea.com/account/mcp](https://distribea.com/account/mcp)

**2.** Drop this block into the `.mcp.json` at the root of your project:

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

**3.** Build your page with `<img src="https://placehold.co/1200x600">` markers, then ask your agent: *"fill the images."* One `make_images` call dresses the whole page.

That's it. The style is inferred from the page itself, so there is nothing else to set up.

## Tools

| Tool | What it does |
|---|---|
| `make_images` ⭐ | Fill every placeholder/stock slot of a page (or the whole project) with on-brand images, in parallel; or rebrand existing images in place (`rebrand: true`) |
| `generate_image` | One on-brand image (auto-switches to UGC selfie mode for review avatars) |
| `edit_image` | Retouch, redo, remove background, upscale ×4, extend |
| `site_style` | Lock, refine or anchor the site's visual identity |
| `brand_pack` | Logo, favicon pack and og:image in one call |
| `create_reference` | Lock a recurring character (real photo supported) or product |
| `finish_images` | Fix missing ALT texts and convert heavy images to WebP (free) |
| `pack_status` | Current style, characters, credits |
| `list_projects` | List your saved projects (brand, products, image count) to find one to reconnect (free) |
| `link_project` | Reconnect the current folder to a saved project so its style/characters/products come back (free) |
| `forget_project` | Wipe the current project's saved memory so it starts fresh (free) |

## Notes

- Generations are billed in credits on your Distribea plan; every batch is quoted in credits before it starts.
- Your project files never leave your machine, except the specific images you ask to edit.

## Privacy Policy

This local connector contains **no API keys and no secrets**. To generate an image it sends to the hosted Distribea engine only what is needed for the request:

- **What is sent:** your image brief (the subject/prompt you ask for), a short text excerpt of the page being worked on (used to infer the site's style and context), a hashed project identifier, and any image file you explicitly ask to edit. **Your other project files stay on your machine**; they are never read or uploaded.
- **What is stored, tied to your account:** your locked visual style, recurring characters/products/avatars, the images generated for you (hosted on Distribea's CDN), and your credit/billing usage.
- **Third parties:** images are produced through Distribea's hosted AI providers solely to fulfil your request. Your data is **never sold**.
- **Authentication:** calls are authenticated with your personal key (`dmcp_…`), issued and revocable at [distribea.com/account/mcp](https://distribea.com/account/mcp).
- **Retention & contact:** data is kept for the life of your account; full policy, retention details and contact at [distribea.com/legal/privacy-policy](https://distribea.com/legal/privacy-policy).

<div align="center">

© Distribea · [distribea.com](https://distribea.com)

</div>
