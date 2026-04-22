# one-shot-graph

Compress business logic, problems, or situations into a single-page operating-principle diagram. 20-frame catalog + static HTML prototypes. One skill, one picture — reveals the essence.

> ⚠️ **MOTION_MODE = OFF (current)** — the skill is in a stabilization phase. Motion code (keyframes, animations) is preserved in templates for future reactivation, but outputs are static HTML/SVG only.

## What it does

Given a business situation, `one-shot-graph` selects from 20 canonical frames (Flywheel, Funnel, Hook Model, Journey Map, JTBD, Unit Economics tree, Capability Stack, etc.) and renders a single-page diagram that captures the underlying operating principle.

Three modes:

- **DIAGNOSE** — situation in, 1–3 frame candidates out with WHY one-liners
- **DESIGN** — frame chosen, empty slots filled via node/edge/axis spec
- **RENDER** — data + frame → static HTML (design skill selection required)

## How it works

1. **Essence question** — seven routers map "why does this exist / grow / retain / monetize / win / break / disrupt" to candidate frames.
2. **Frame selection** — 3 tiers (5 motion-essential, 7 motion-recommended, 8 static-ok) across 20 frames.
3. **Design skill cascade** — before RENDER, one of `apple-box-design` (box/bento) or `design-skill` (node-edge) is invoked to own the visual hierarchy.
4. **Static output** — HTML with inline SVG, zero CDN by default, `var(--osg-info/caption/decor)` color tokens for apple-cascade compatibility.

## Fusion (no-modify)

`one-shot-graph` ships HTML blocks and class-hook signals only. Downstream skills (`paper-engine`, `design-skill`, `apple-box-design`, `apple-design-style`, `obsidian-markdown`, `github-deploy`, `html-div-style`) cascade without touching each other's source.

A CSS alias shim (`--osg-*` ↔ `--label-*`) is auto-injected when `apple-box-design` is in the chain, so dark-container remapping works without variable collision.

## Install

Drop the skill into your Claude skills plugin directory, or install the packaged `.skill` bundle via Claude Code or Cowork.

## Korean version

See [README.ko.md](README.ko.md).

## License

MIT — see [LICENSE](LICENSE).
