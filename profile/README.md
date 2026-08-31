# Play198x

The retro media player/viewer for the 198x family — plays and previews vintage media without booting a whole machine.

Audio (SID, AY/YM, tracker formats), images (IFF/ILBM, C64 koala/hires, Spectrum SCR), and animation (Amiga ANIM, FLI/FLC). The boundary with [Emu198x](https://github.com/emu198x): Emu198x *executes programs* (boots a machine); Play198x *renders media* — a different verb.

## Status — building

The core and browser player are live. Play198x views Spectrum SCREEN$, C64 Koala and Art Studio, and Amiga ILBM; it plays ProTracker MOD, ZX Spectrum AY, and ROM-free callable PSID. It reads plain files, ZIPs and Amiga disk images, including PowerPacker-compressed entries.

AY and SID are machine code plus chip activity rather than data a player merely interprets. Play198x runs that code against Emu198x's published CPU and sound-chip crates on deliberately small, ROM-free hosts. RSID and self-driven PSID need a continuously scheduled C64 and belong to Emu198x; ROM-dependent and multi-SID tunes are identified and explicitly declined.

A guiding rule: Play198x is a thin consumer of Emu198x's chip and CPU cores for the formats that need a player, and decodes pure-data formats directly. It never reimplements chip emulation; the boundary is governed by the umbrella Play198x decision record.

## Repositories

- **[play198x](https://github.com/play198x/play198x)** — the media player/viewer workspace: `play198x-core` and `play198x-web`.
- **[docs](https://github.com/play198x/docs)** — design notes, and user documentation in time.
- **[play198x.github.io](https://github.com/play198x/play198x.github.io)** — the public site and browser player.

## Part of the 198x family

Play198x is the media player/viewer sibling in the 198x family, sharing the same hardware-reference layer as the curriculum, emulator, assembler, build-tools, and catalogue projects.

## Foundations

Every project in the 198x family shares three documents: [why it exists](https://github.com/play198x/.github/blob/main/MANIFESTO.md), [the principles it decides by](https://github.com/play198x/.github/blob/main/PRINCIPLES.md), and [how it works on a subject](https://github.com/play198x/.github/blob/main/PRACTICE.md).
