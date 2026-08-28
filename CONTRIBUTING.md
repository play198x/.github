# Contributing to Play198x

Thanks for taking a look. Play198x is the 198x family's retro media
player/viewer — it plays and previews vintage media without booting a whole
machine.

This file applies to every repo in the [play198x](https://github.com/play198x) org.

## Where it is

The data-driven core is building. It probes a file and decodes ZX Spectrum
SCREEN$, C64 Koala and OCP Art Studio, and Amiga IFF/ILBM to RGBA, and plays
ProTracker modules. Nothing is published to crates.io yet. Chip-backed audio
(SID, AY) is deliberately out of the first slice: it needs Emu198x chip crates
that are not yet published.

Read the specs in the `docs` repo before proposing scope or architecture changes.

## Two rules that shape the design

- **Render media, don't execute programs.** Emu198x boots a machine; Play198x
  renders a tune, image or animation that is not a bootable program. Work that
  needs a machine booted belongs in Emu198x.
- **Thin consumer, never a reimplementation.** Play198x reuses Emu198x's chip and
  CPU emulation for formats that need a player, and decodes pure-data formats
  directly. It does not reimplement chip emulation.

## Before opening a pull request

Run `cargo test`, `cargo clippy` and `cargo fmt --check`.

Clear, imperative commit subjects that describe the effect; explain the *why* in
the body. One concern per PR. Conventional-commit prefixes (`feat:`, `fix:`) are
welcome but not required.
