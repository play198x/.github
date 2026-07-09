# Play198x — org container

This folder is the local mirror of the **`play198x` GitHub org**. It is a
*container*, not a git repo: each subfolder is its own independent repo with its
own history and remote (the same pattern as `Code198x/`, `Asm198x/`, `Cat198x/`,
`Forge198x/`, and `Build198x/`). The umbrella `198x/` repo gitignores this
folder; commit inside the specific subfolder, never here.

Play198x is the 198x family's **retro media player/viewer** — it plays and
previews vintage media (audio, images, animation) without booting a whole
machine. See the umbrella context at [`../CLAUDE.md`](../CLAUDE.md) and the
binding decision at [`../decisions/play198x-media-player.md`](../decisions/play198x-media-player.md).

**Status: not yet started.** No near-term pull; these repos hold design and future
implementation space until a concrete need appears (curriculum media previews or
a Cat198x preview surface).

## Repos in this org

| Folder | GitHub repo | Role |
|--------|-------------|------|
| [`play198x/`](play198x/) | `play198x/play198x` | **Flagship.** Future media player/viewer repo. |
| [`.github/`](.github/) | `play198x/.github` | Org profile (`profile/README.md`) and shared community-health files. |
| [`docs/`](docs/) | `play198x/docs` | Design notes; user docs in time. |

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
