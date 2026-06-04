# Play198x

The retro media player/viewer for the 198x family — plays and previews vintage media without booting a whole machine.

Audio (SID, AY/YM, tracker formats), images (IFF/ILBM, C64 koala/hires, Spectrum SCR), and animation (Amiga ANIM, FLI/FLC). The boundary with [Emu198x](https://github.com/emu198x): Emu198x *executes programs* (boots a machine); Play198x *renders media* — a different verb.

## Status — decided, not yet started

Not built yet, and deliberately so. Play198x has no near-term pull; the repos exist to hold the work, which waits for a concrete need — curriculum media previews, or a preview surface for Cat198x's catalogue.

A guiding rule: Play198x is a thin consumer of Emu198x's chip and CPU cores for the formats that need a player, and decodes pure-data formats directly. It never reimplements chip emulation.

## Repositories

- **[play198x](https://github.com/play198x/play198x)** — the media player/viewer (placeholder for now).
- **[docs](https://github.com/play198x/docs)** — design notes, and user documentation in time.

## Part of the 198x family

A sibling project to retro-computing curriculum, emulator, assembler, build-tools, and cataloguing work that share a hardware-reference layer.
