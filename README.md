<div align="center">

# Distribea

### Generate images, video, music &amp; voice — right inside your terminal and your AI agent.

[![npm version](https://img.shields.io/npm/v/distribea-mcp?style=flat-square&color=2563eb&label=npm)](https://www.npmjs.com/package/distribea-mcp)
[![npm downloads](https://img.shields.io/npm/dm/distribea-mcp?style=flat-square&color=2563eb)](https://www.npmjs.com/package/distribea-mcp)
[![MCP registry](https://img.shields.io/badge/MCP-registry-2563eb?style=flat-square)](https://registry.modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-2563eb?style=flat-square)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/Distribea/distribea-mcp?style=social)](https://github.com/Distribea/distribea-mcp/stargazers)

**CLI · MCP server · Claude Skill** — works with Claude Code · Cursor · Windsurf · Replit · Copilot

</div>

**Distribea is an on-brand AI media toolkit for builders.** It generates **images, video, music and voice** from plain-language prompts and ships them production-ready — optimised **WebP** with **SEO alt text**, downloaded for you or patched straight into your code. One connector, four media types, reachable three ways: a **CLI** in your terminal, an **MCP server** your AI coding agent calls while it builds, and a **Claude Skill**. Define your brand once; a built-in **AI art director** writes every prompt — you say **what** you want, never **how** to render it. Billed in credits at the regular **site price**; the connector holds **no API keys and no secrets**.

```bash
npm install -g distribea-mcp
distribea login                                       # opens your browser — no key to paste

distribea image "founder portrait, soft daylight"  --portrait
distribea video "slow waves rolling at golden hour" --landscape
distribea music "warm lo-fi beat, mellow, 90 bpm"
distribea voice "Welcome to our store."             --lang en
```

Each file lands in a tidy folder, ready to use. Add `--dry-run` to any command to see the exact credit price first (0 credits, generates nothing).

---

## Contents

- [What is Distribea](#what-is-distribea)
- [What you can make](#what-you-can-make)
- [When to use Distribea](#when-to-use-distribea)
- [Why Distribea](#why-distribea)
- [Install](#install)
- [Quickstart](#quickstart)
- [Examples &amp; recipes](#examples--recipes)
- [Dress a whole page](#dress-a-whole-page)
- [Recurring faces &amp; products](#recurring-faces--products)
- [Models](#models)
- [Command reference](#command-reference)
- [Flags](#flags)
- [MCP tools](#mcp-tools)
- [How it works](#how-it-works)
- [Billing &amp; cost](#billing--cost)
- [Privacy &amp; security](#privacy--security)
- [FAQ](#faq)
- [Troubleshooting](#troubleshooting)
- [Updating](#updating)
- [Support](#support)
- [License](#license)

## What is Distribea

Most AI media tools hand you a raw model and a blank prompt box, in a browser tab, one image at a time. Distribea is the layer above that — and it lives **where you build**.

- **One connector, four media types.** Image, video, music *and* voice through a single install. Most tools stop at images.
- **Three ways in, one engine.** Run it from your **shell** (`distribea …`), drop it into your **AI agent** as an MCP server (Claude Code, Cursor, Windsurf, Replit, Copilot), or add the **Claude Skill** so the model reaches for it on its own.
- **On-brand by default.** Lock your brand once and every asset matches it. The art director turns a one-line subject into a full prompt — you never write the "how".
- **Production-ready.** Images come out as optimised WebP with proper SEO alt text, downloaded for you or patched straight into your page.

The heavy lifting — art direction, generation, billing — runs on the hosted Distribea engine. This package is only the local connector: it scans and patches **your** files, holds **no API keys and no secrets**, and bills generation in credits on your Distribea plan at the regular site price.

## What you can make

| Media | Command | What you get |
|---|---|---|
| 🖼️ **Image** | `distribea image "<subject>"` | One on-brand image (png/jpg), any aspect ratio. Portraits, heroes, product shots, illustrations, review avatars. |
| 🎬 **Video** | `distribea video "<subject>"` | One short clip (mp4) — text-to-video, or image-to-video from a reference photo. |
| 🎵 **Music** | `distribea music "<style>"` | One royalty-ready track (mp3) — intros, backing music, ad beds. |
| 🎙️ **Voice** | `distribea voice "<text>"` | One voice-over (mp3), text-to-speech in many languages. |
| 📄 **A whole page** | `distribea page [path]` | Every `<img>` placeholder on a page (or the whole project) filled on-brand, in parallel, patched into your code. |
| ✍️ **Blog cover** | `distribea blog "<article>"` | A 16:9 cover image that illustrates the article's actual subject, in your style, + alt text. |

## When to use Distribea

Reach for Distribea whenever a project needs imagery or audio and you'd otherwise ship stock photos, gray placeholders, CSS-gradient-only sections, or a raw pasted photo. Typical jobs:

- You're **building a landing page** and need real, on-brand images — not stock.
- You need **e-commerce product shots** that stay consistent across the catalog.
- You want a **hero image, team portraits, or testimonial avatars** with believable faces.
- You're **writing a blog post** and need a cover image matched to the article and your style.
- You need a **short video clip** (text-to-video or image-to-video) for a hero or ad.
- You need **background music** for an intro, demo, or ad.
- You need a **voice-over** for a demo, walkthrough, or video narration.
- You have a site full of **cheap or off-brand stock photos** and want to rebrand them in place.
- You're **vibe coding with an AI agent** and want it to fill in media on its own as it builds.

## Why Distribea

| | Raw-model CLI / MCP | Generic image MCP | **Distribea** |
|---|:---:|:---:|:---:|
| Image · video · music · voice | ⚠️ varies | ❌ image only | ✅ all four, one connector |
| Lives in your terminal &amp; your agent | ⚠️ one of them | ⚠️ MCP only | ✅ CLI · MCP · Skill |
| Writes the art direction for you | ❌ you prompt each model | ⚠️ prompt by prompt | ✅ built-in art director |
| Locks your brand once | ❌ | ⚠️ per prompt | ✅ applied everywhere |
| Same face across scenes | ❌ | ❌ | ✅ recurring characters |
| Fills a whole page in one call | ❌ | ❌ | ✅ `distribea page` |
| Production-ready (WebP + SEO alt) | ❌ | ❌ | ✅ automatic |
| No keys/secrets in the connector | ⚠️ holds your model keys | ⚠️ varies | ✅ browser sign-in, nothing to paste |

**In one line:** other tools give you a model and a prompt box; Distribea gives you finished, on-brand assets — in the four media types you actually need — without leaving the place you build.

## Install

A [Distribea](https://distribea.com) plan powers generation (free/trial accounts get a couple of gift images to try it). The connector itself is free and stores no secrets.

### CLI (recommended)

```bash
npm install -g distribea-mcp
distribea login          # opens your browser, click Authorize — no key to paste
```

`distribea whoami` confirms you're connected.

### MCP server

Drop this into the `.mcp.json` at the root of your project:

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

Grab your `dmcp_…` key at [distribea.com/account/mcp](https://distribea.com/account/mcp). If you've already run `distribea login`, the server reuses that session and you can omit the `env` block entirely.

| Tool | Where to add it |
|---|---|
| **Claude Code** | `claude mcp add distribea-mcp -e DISTRIBEA_MCP_KEY=dmcp_… -- npx -y distribea-mcp@latest` |
| **Cursor** | Settings → MCP → Add, or paste the block into `~/.cursor/mcp.json` |
| **Windsurf** | Paste into `~/.codeium/windsurf/mcp_config.json` |
| **VS Code (Copilot)** | Paste into `.vscode/mcp.json` |
| **Replit** | Add as a custom MCP server with the command above |

### Claude Skill

The package ships `SKILL.md`. Add it once and your agent reaches for Distribea on its own whenever a page needs imagery or audio.

```bash
npx skills add Distribea/distribea-mcp
```

## Quickstart

```bash
npm install -g distribea-mcp
distribea login
distribea image "a quiet beach at sunrise, warm light" --landscape
```

The file lands in a tidy folder, ready to use. That's it — no model to pick, no prompt engineering: the style is inferred and the art director writes the prompt. From here, swap `image` for `video`, `music`, or `voice`, or run `distribea page` to dress a whole page at once.

## Examples &amp; recipes

Every command takes a plain-language subject. Add `--dry-run` to preview the price first (0 credits, generates nothing).

### On-brand image

```bash
distribea image "founder portrait, soft daylight, neutral background" --portrait
```

### Standalone video (text-to-video)

```bash
distribea video "slow waves rolling onto a tropical beach" --landscape
```

### Background music

```bash
distribea music "warm lo-fi beat, mellow, 90 bpm" --out ./assets
```

### Voice-over (text-to-speech)

```bash
distribea voice "Welcome to our store — let's get you started." --lang en
```

### Reference photo → image or video (image-to-image / image-to-video)

Turn a real photo into a new on-brand image or animate it. Pass `--ref` once, or several times for multiple references — automatically capped to what the chosen model accepts.

```bash
distribea image "the same product on a marble kitchen counter" --ref ./bottle.jpg
distribea video "gentle push-in on the cliff at golden hour" --ref ./cliff.jpg --portrait
```

### Blog cover

Reads the article and illustrates its specific subject, matched to your locked style, as a 16:9 WebP + alt text.

```bash
distribea blog "How we cut our build times in half — full article body here…"
```

### Pick a specific model

Defaults are strong; only name a model when you want a particular one.

```bash
distribea image "minimalist blue logo on white" --model nano-banana-pro --dry-run
```

### Browse the live catalog (free)

```bash
distribea models image      # or: video | music | voice
```

## Dress a whole page

The page workflow is the superpower. Build your page with `<img src="https://placehold.co/1200x600">` markers wherever an image goes, then one call fills **every** slot with imagery that matches your brand — one consistent look across the whole site, recurring characters with the **same face in every scene**, believable UGC avatars for review sections.

```bash
distribea page ./index.html      # omit the path to dress the whole project
```

Every image lands production-ready: optimised **WebP**, proper **SEO alt text**, and **patched straight into your code**. No stock photos. No placeholders. No export step. The style is inferred from the page itself, so there's nothing to set up.

Already have a site with cheap or off-brand stock photos? Rebrand them in place — the first pass lists every replaceable image for free, then applies the new look without touching your code (originals kept as `*.original`).

## Recurring faces &amp; products

A real person (a founder, a teacher) or a product that must look identical in every shot is treated as a locked subject — the **face/object stays 100% identical, only the staging changes**.

```bash
distribea image "the teacher explaining at a whiteboard" --ref ./founder.jpg
```

Never paste a raw photo into the page: leave a placeholder and let the engine restage that exact face in your site's world. Review and testimonial avatars come out as casual smartphone selfies (UGC look); the same reviewer keeps the same face across the site.

## Models

Generation runs on best-in-class providers, with a strong on-brand default per media type — so you rarely need to name one:

| Type | Default | A few of the providers available |
|---|---|---|
| Image | Nano Banana Pro (2K) | Nano Banana Pro · Seedream · Z-Image · Grok Image |
| Video | Grok Imagine (6s, 720p) | Grok · Seedance · Veo · Sora |
| Music | MiniMax Music | MiniMax · CassetteAI |
| Voice | ElevenLabs Multilingual v2 | ElevenLabs · MiniMax |

The catalog is live — browse current models, what each is best at, their options and indicative prices with `distribea models image|video|music|voice` (free), or `list_models` / `list_video_models` / `list_music_models` / `list_voice_models` over MCP.

## Command reference

| Command | Purpose |
|---|---|
| `distribea login` `[key]` | Connect — opens your browser; or pass a `dmcp_…` key directly |
| `distribea whoami` · `logout` | Check / forget the saved session |
| `distribea image "<subject>"` | One downloadable image (png/jpg) |
| `distribea video "<subject>"` | One downloadable video (mp4) |
| `distribea music "<style>"` | One downloadable track (mp3) |
| `distribea voice "<text>"` | One downloadable voice-over (mp3) |
| `distribea page` `[path]` | Fill a page (or the whole project) — placeholders → on-brand images |
| `distribea blog "<article>"` | Article cover (16:9 + alt text) |
| `distribea models` `[type]` | Browse the live catalog: `image` · `video` · `music` · `voice` |
| `distribea call <tool> --k v` | Call any advanced MCP tool directly (see [MCP tools](#mcp-tools)) |

Run `distribea help` for the full reference.

## Flags

| Flag | Purpose |
|---|---|
| `--model <id>` | Pick a specific model (see `distribea models`) |
| `--ref <file>` | Reference image — image-to-image / image-to-video (repeat for several) |
| `--format <r>` | `16:9` (landscape) · `9:16` (portrait) · `1:1` (square) |
| `--portrait` · `--landscape` · `--square` | Orientation shortcuts |
| `--lang <code>` | Voice language (e.g. `en`, `fr`) |
| `--out <dir>` | Where to download the file |
| `--jpg` | Image as jpg instead of png |
| `--dry-run` | Quote only (0 credits) — shows the price, generates nothing |

## MCP tools

When used as an MCP server, the same engine exposes these tools to your agent. The agent picks the right one for the job; you just describe what you need.

| Tool | What it does |
|---|---|
| `make_images` ⭐ | Fill every placeholder/stock slot of a page (or the whole project) with on-brand images, in parallel; or rebrand existing images in place (`rebrand: true`) |
| `bring_alive` | Make an existing site feel alive: add images where sections have none and replace stock/old pictures on-brand (free proposal first, reversible) |
| `generate_image` | One on-brand image (auto-switches to UGC selfie mode for review avatars) |
| `generate_with_model` | Standalone image with a chosen model + settings, downloaded as a native png/jpg |
| `generate_video` | Standalone video with a chosen model, downloaded as a native mp4 |
| `generate_music` | Standalone music track, downloaded as mp3 |
| `generate_voice` | Standalone voice-over (text-to-speech), downloaded as mp3 |
| `list_models` · `list_video_models` · `list_music_models` · `list_voice_models` | Browse the catalog (ids, strengths, options, indicative prices) before generating (free) |
| `edit_image` | Retouch, redo, remove background, upscale ×4, extend |
| `blog_cover` | Generate an on-brand cover image for a blog article |
| `site_style` | Lock, refine or anchor the site's visual identity |
| `brand_pack` | Logo, favicon pack and og:image in one call |
| `create_reference` | Lock a recurring character (real photo supported) or product |
| `finish_images` | Fix missing ALT texts and convert heavy images to WebP (free) |
| `pack_status` | Current style, characters, credits |
| `list_projects` · `link_project` · `forget_project` | Save, reconnect or wipe a project's brand memory (free) |

## How it works

1. **You give a subject** — a CLI command, or your agent calls a tool while it builds.
2. **The art director expands it** into a full, on-brand prompt using your locked style — so you never hand-write the "how".
3. **The best-fit model generates** the asset (or the one you named with `--model`).
4. **You get a finished file** — downloaded to a tidy folder, or patched into your page as optimised WebP with SEO alt text, originals kept safe.

Every batch is **quoted in credits before it runs**; `--dry-run` (CLI) or `dry_run` (MCP) previews the price and generates nothing. The connector runs locally and holds no secrets; your brand memory, generated assets, and billing live on the hosted Distribea engine.

## Billing &amp; cost

- Generation is billed in credits on your Distribea plan; every batch is quoted in credits before it starts — use `--dry-run` (CLI) or `dry_run` (MCP) to preview the price first.
- Video, music and voice need a paid plan and take longer to render. If a call says it's still rendering, run it again with the same settings to pick it up — **you are never charged twice**.
- One `page` call dresses a page; the job is then done. Distribea won't regenerate or "improve" assets on its own — retouch only when you ask.

## Privacy &amp; security

This local connector contains **no API keys and no secrets**. To generate an asset it sends to the hosted Distribea engine only what is needed for the request:

- **What is sent:** your brief (the subject you ask for), a short text excerpt of the page being worked on (to infer the site's style and context), a hashed project identifier, and any file you explicitly ask to edit. **Your other project files stay on your machine** — they are never read or uploaded.
- **What is stored, tied to your account:** your locked visual style, recurring characters/products/avatars, the assets generated for you (hosted on Distribea's CDN), and your credit/billing usage.
- **Third parties:** assets are produced through Distribea's hosted AI providers solely to fulfil your request. Your data is **never sold**.
- **Authentication:** calls are authenticated with your personal key (`dmcp_…`), issued and revocable at [distribea.com/account/mcp](https://distribea.com/account/mcp).
- **Retention &amp; contact:** data is kept for the life of your account; full policy and contact at [distribea.com/legal/privacy-policy](https://distribea.com/legal/privacy-policy).

## FAQ

**What is Distribea MCP?**
An on-brand AI media toolkit that generates images, video, music and voice from plain-language prompts, available as a CLI, an MCP server, and a Claude Skill. It ships production-ready assets (WebP + SEO alt text) at the regular site price.

**Which AI coding tools does it work with?**
Claude Code, Cursor, Windsurf, Replit and GitHub Copilot — anything that speaks MCP. It also runs as a plain CLI in any terminal.

**Do I need an API key?**
No. `distribea login` signs you in through the browser — nothing to paste. For an MCP/hosted setup you use a personal `dmcp_…` key, issued and revocable in your account.

**Is it free?**
The connector is free and stores no secrets. Generation is billed in credits on your Distribea plan; free and trial accounts get a couple of gift images to try it.

**Can it generate video, music and voice — or only images?**
All four: image, video, music and voice, through one connector.

**How is it different from a raw image model or a generic image MCP?**
A built-in art director writes the prompt from your one-line subject, your brand is locked once and applied everywhere, faces and products stay identical across shots, and a single call can fill an entire page — patched into your code as WebP with SEO alt text.

**Can it use my own photos?**
Yes. Pass `--ref` for image-to-image or image-to-video, and lock a person or product so the same face/object appears in every scene while the staging changes.

**Will it modify my code or files?**
Only files you point it at. `distribea page` fills placeholders and patches them into your markup; when rebranding existing images it keeps the originals as `*.original`. Your other files are never read or uploaded.

**What formats and aspect ratios does it produce?**
Downloaded assets are native png/jpg (image), mp4 (video), mp3 (music/voice); images placed in a page come out as optimised WebP. Orientations: `16:9`, `9:16`, `1:1`.

**How do I see the price before generating?**
Add `--dry-run` (CLI) or `dry_run` (MCP). It quotes the exact credit cost and generates nothing (0 credits).

**A call says it's still rendering — will I be charged twice?**
No. Video, music and voice take longer; re-run the exact same command to pick the result up. You are never charged twice.

**Which models does it use?**
Strong on-brand defaults per media type (e.g. Nano Banana Pro for images, Grok Imagine for video, MiniMax for music, ElevenLabs for voice), with a live catalog you can browse and override with `--model`.

## Troubleshooting

**`No Distribea key` / `Not authenticated`** — run `distribea login` (or set `DISTRIBEA_MCP_KEY` for an MCP/hosted setup).

**`Unknown model "<name>"`** — run `distribea models image|video|music|voice` for the current catalog.

**A call says it's still rendering** — video/music/voice take longer; re-run the exact same command to pick the result up. You are never charged twice.

## Updating

```bash
npm install -g distribea-mcp@latest
```

The MCP server pulls `@latest` automatically through `npx`, so agent setups stay current on their own.

## Support

Bugs and feature requests: [github.com/Distribea/distribea-mcp/issues](https://github.com/Distribea/distribea-mcp/issues). Key and docs: [distribea.com/account/mcp](https://distribea.com/account/mcp).

## License

[MIT](LICENSE)

<div align="center">

© Distribea · [distribea.com](https://distribea.com)

</div>
