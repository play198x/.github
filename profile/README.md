# Play198x

The retro media player/viewer for the 198x family — plays and previews vintage media without booting a whole machine.

Audio (SID, AY/YM, tracker formats), images (IFF/ILBM, C64 koala/hires, Spectrum SCR), and animation (Amiga ANIM, FLI/FLC). The boundary with [Emu198x](https://github.com/emu198x): Emu198x *executes programs* (boots a machine); Play198x *renders media* — a different verb.

## Status — building

The first sub-project is running: a **data-driven core** that views Spectrum SCR, C64 Koala and Art Studio, and Amiga ILBM, and plays ProTracker MOD, read straight out of plain files, ZIPs and Amiga disk images.

SID and AY come later. Those formats are machine code plus a register stream rather than data a player interprets, so they need the emulator's chip cores; the data-driven half needs nothing from Emu198x at all.

A guiding rule: Play198x is a thin consumer of Emu198x's chip and CPU cores for the formats that need a player, and decodes pure-data formats directly. It never reimplements chip emulation; the boundary is governed by the umbrella Play198x decision record.

## Repositories

- **[play198x](https://github.com/play198x/play198x)** — the media player/viewer workspace: `play198x-core` and `play198x-web`.
- **[docs](https://github.com/play198x/docs)** — design notes, and user documentation in time.

## Part of the 198x family

Play198x is the future media player/viewer sibling in the 198x family, sharing the same hardware-reference layer as the curriculum, emulator, assembler, build-tools, and catalogue projects.

## Foundations

Every project in the 198x family shares three documents: [why it exists](https://github.com/play198x/.github/blob/main/MANIFESTO.md), [the principles it decides by](https://github.com/play198x/.github/blob/main/PRINCIPLES.md), and [how it works on a subject](https://github.com/play198x/.github/blob/main/PRACTICE.md).
