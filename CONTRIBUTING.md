# Contributing to Play198x

Thanks for taking a look. Play198x is the 198x family's development workbench —
an IDE that drives Asm198x and Emu198x. It is **deferred**: gated on those two
projects maturing first, so there is no build to contribute to yet.

This file applies to every repo in the [play198x](https://github.com/play198x) org.

## Right now

The most useful contribution is **discussion** — how the workbench should feel,
what the edit → assemble → run → debug loop should do, which editor or runtime to
build on. Open an issue or start a discussion.

## When the build starts

The stack isn't chosen yet (a VS Code extension and a TUI are both on the table).
Once it is, this file gains the concrete build/check commands the other family
repos have. Two principles are already fixed:

- **Thin front-end, not a new backend.** Play198x consumes Emu198x's
  scriptable / MCP surface and Asm198x's CLI; it does not reimplement assembly or
  emulation.
- **Agent-native parity.** Anything a human can do in Play198x, an agent can do
  through the same tool surface. A human-only path is a bug.

## Commits and PRs

Clear, imperative commit subjects that describe the effect; explain the *why* in
the body. One concern per PR. Conventional-commit prefixes (`feat:`, `fix:`) are
welcome but not required.
