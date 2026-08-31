# Play198x — org container

> Read [`PRINCIPLES.md`](.github/PRINCIPLES.md) first. [`MANIFESTO.md`](.github/MANIFESTO.md) is why the project exists.

This folder is the org container for the **`play198x` GitHub organisation**. It is not a Git repo; each child folder is an independent repo with its own remote. Commit inside the repo that owns the file.

Play198x is the 198x family's **retro media player/viewer** — it plays and
previews vintage media (audio, images, animation) without booting a whole
machine. See the umbrella context at [`../AGENTS.md`](../AGENTS.md) and the
binding decision at [`../decisions/play198x-media-player.md`](../decisions/play198x-media-player.md).

**Status: building.** The data-driven core (images + tracker music) is designed
in `docs/specs/`, planned in `docs/plans/`, and implemented in `play198x/` — it
probes a file, decodes ZX Spectrum SCREEN$, C64 Koala and Art Studio and Amiga
ILBM to RGBA, and plays a ProTracker module. `play198x-core` is published on
crates.io and `@play198x/web` on npm. Read those specs before proposing scope
or architecture changes.

ZX Spectrum `.ay` and ROM-free callable PSID tunes play as well, behind
`play198x-core`'s separate optional `ay` and `sid` features. The tunes' own Z80
or 6502 code runs against Emu198x's published CPU and sound-chip crates on
hosts Play198x supplies, and **no ROM is shipped or required**. Both features
are off by default, so an image-only consumer acquires neither CPU. The web
shell exposes both. RSID and zero-play-address PSID belong to Emu198x because
they require a continuously scheduled C64 machine; ROM-dependent and multi-SID
tunes are identified and explicitly declined. The design and measurements are
in `docs/specs/2026-08-28-code-driven-audio.md` and `play198x/decisions/`.

## Repos in this org

| Folder | GitHub repo | Role |
|--------|-------------|------|
| [`play198x/`](play198x/) | `play198x/play198x` | **Flagship.** The media player/viewer workspace; holds `play198x-core`. |
| [`.github/`](.github/) | `play198x/.github` | Org profile (`profile/README.md`) and shared community-health files. |
| [`docs/`](docs/) | `play198x/docs` | Design notes; user docs in time. |
| [`play198x.github.io/`](play198x.github.io/) | `play198x/play198x.github.io` | Public site — a landing page that **is** the player: drop a file on it and it plays in your browser. Designed in `docs/specs/2026-08-26-website-design.md`. |

## Working here

- **Commit in the right subfolder.** Each repo is independent; `git status` from
  the container shows nothing (it isn't a repo).
- **The boundary with Emu198x:** Emu198x *executes programs* (boots a machine);
  Play198x *renders media* (a tune/image/anim that isn't a bootable program).
- **Thin consumer of Emu198x's cores** — Play198x reuses Emu198x's chip/CPU
  emulation (SID/AY/Paula/VIC, 6502/Z80) for formats that need a player, and
  decodes pure-data formats (IFF/SCR images) directly. It **never** reimplements
  chip emulation — the same thin-consumer rule Forge198x lives under.
- **Cross-project decisions** live in the umbrella [`../decisions/`](../decisions/);
  Play198x-only decisions live in `play198x/decisions/` once it starts.
