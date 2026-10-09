# ASCENT

### ▶ Live: **[hapybeing.github.io/Ascent](https://hapybeing.github.io/Ascent/)**

*Start where the light is thin.*

ASCENT is a scroll-driven WebGL piece about rising. You begin at the bottom of a sea made of light. Every scroll lifts you higher: up through the waterline, across a sea of clouds and floating islands, into thin lavender air, and finally to a quiet ring of light at the top of the world.

Scroll is altitude. There are no menus, no buttons to hunt for, and nothing to win. Just keep rising.

Best with sound on.

---

## The climb

| | Chapter | What you pass through |
|---|---|---|
| 1 | **Light Sea** | Silk ribbons drifting in luminous water, caustic light on the floor |
| 2 | **Breach** | The waterline crossing: meniscus, droplets on the lens, the first breath of air |
| 3 | **Cloud Sea** | Volumetric clouds you fly through, soft peach light |
| 4 | **Archipelago** | Floating islands with trees, hanging roots and waterfalls that fall *upward* |
| 5 | **Thin Air** | The sky turns lavender, stars show in daylight, the horizon starts to curve |
| 6 | **Ring** | Silence, then a single chord. Stay as long as you like. |

## How to move

| Device | Controls |
|---|---|
| Phone / tablet | Swipe up to rise, swipe down to sink. Tap the water or sky to send a pulse. |
| Trackpad / mouse | Scroll. Move the pointer to part the ribbons. Click for a chime. |
| Keyboard | Arrow keys, Page Up/Down, Space, Home and End |

At the top, **Descend** glides you all the way back down to the beginning.

## Sound

Everything you hear is generated live in the browser with the Web Audio API. There are no audio files. The score shifts with altitude: muffled and low underwater, opening at the surface, thinning into air, and resolving into one chord at the ring. Sound starts when you press Enter and can be toggled any time.

## Accessibility and fallbacks

- **Reduced motion:** if your device asks for reduced motion, ASCENT runs a calmer mode with no blur reveals and gentler movement.
- **No WebGL:** browsers without WebGL get a still poster of the piece instead of a broken page.
- **Older GPUs:** a lighter WebGL1 renderer keeps the climb working.
- **Adaptive quality:** frame time is watched continuously. If a device starts to struggle, the cloud rendering gets cheaper first and screen resolution drops only as a last resort, so scrolling stays smooth on phones and tablets.
- All on-screen lines are real text and are announced to screen readers.

## Debug tools

Add these to the URL:

- `?debug` shows a frame-time readout (p50 / p95 over the last 240 frames) and a tuning panel. It loads separately, so normal visitors never download it.
- `?alt=6500` opens at a given altitude in metres. `?alt=top` jumps straight to the ring.

Example: `https://hapybeing.github.io/Ascent/?debug&alt=3000`

## Built with

- [three.js](https://threejs.org/) and hand-written GLSL shaders (44 shader stages)
- [postprocessing](https://github.com/pmndrs/postprocessing) for bloom, grade and the waterline pass
- [GSAP](https://gsap.com/) for the per-character blur-to-focus type
- [Lenis](https://lenis.darkroom.engineering/) for smooth scrolling
- Web Audio API for the procedural score
- Vite + TypeScript (strict)

**Type:** [Zodiak](https://www.fontshare.com/fonts/zodiak) by Indian Type Foundry and [DM Mono](https://fonts.google.com/specimen/DM+Mono) by Colophon Foundry. Licence files are included in this repo.

## Repo layout

This repo holds the production build, flattened so every file sits at the root (it can be updated straight from a tablet). The main script is `index-*.js`, and `index.html` has the styles inlined. `404.html` is a small page in the same world for wrong links, and `og.jpg` is the share image.

---

Made by **Gaurang Kumar** ([@hapybeing](https://github.com/hapybeing)).
