---
layout: page
title: MusaLCE — Live Coding with MusaDSL
permalink: musalce
---

# MusaLCE — Live Coding with MusaDSL

**MusaLCE** (Musa Live Coding Environment) is the suite of components that turns [MusaDSL](https://github.com/javier-sy/musa-dsl) into a live coding environment: write Ruby in your editor, hear changes in real time as the sequencer keeps playing.

## Two ways to use it

### Standalone — bring your own REPL

You build your own `main.rb` with a sequencer, voices, clock and transport, and start `Musa::REPL::REPL.new(binding)` inside the sequencer's DSL context. Your editor connects on `localhost:1327` and sends Ruby fragments live. Maximum control over MIDI, clock, voices and your own DSL helpers.

Best when your target is **SuperCollider, Max/MSP, OSC apps, custom hardware** or you want the smallest possible footprint.

→ Reference: [musa-dsl/docs/subsystems/repl.md](https://github.com/javier-sy/musa-dsl/blob/master/docs/subsystems/repl.md)
→ Worked example: [`musadsl-demo/_demo-13-live-coding`](https://github.com/javier-sy/musadsl-demo)

### Suite workflow — musalce-server + DAW extension

When the target is **Ableton Live** or **Bitwig Studio**, install the [musalce-server](https://github.com/javier-sy/musalce-server) gem and the matching DAW extension. The server packages the REPL, the sequencer, the DAW handler and a Stream Deck surface for you, and exposes a `daw.*` API for transport, tracks, voices and Surface controls.

Internally, the suite is a **specialization** of the standalone case: `musalce-server` opens the same `Musa::REPL::REPL` after pre-building all the boilerplate.

→ Canonical architecture reference: [musalce-server/docs/architecture.md](https://github.com/javier-sy/musalce-server/blob/master/docs/architecture.md)
→ REPL commands reference: [musalce-server README](https://github.com/javier-sy/musalce-server#readme)

## Quick Start (suite workflow)

1. **Install the gem**: `gem install musalce-server`.
2. **Install the matching DAW extension**:
   - Bitwig 5+ → [MusaLCEforBitwig](https://github.com/javier-sy/MusaLCEforBitwig) (`.bwextension`)
   - Ableton Live 11+ → [MusaLCEforLive](https://github.com/javier-sy/MusaLCEforLive) (User Library Remote Script)
3. **Install the VSCode extension**: [MusaLCEClientForVSCode](https://github.com/javier-sy/MusaLCEClientForVSCode) (build local `.vsix` for now — not on the Marketplace yet).
4. **Start the server**: `musalce-server bitwig` or `musalce-server live`.
5. **Open VSCode**, write a `.rb` file, and send code with `Ctrl+Alt+Enter`.

For Live you'll also need a virtual MIDI bus (IAC Driver on macOS) so the server can drive Live's tempo — see the [MusaLCEforLive README](https://github.com/javier-sy/MusaLCEforLive#readme) for the walkthrough.

## Stream Deck integration (Bitwig only, optional)

Add [Pulso](https://github.com/javier-sy/pulso) to drive MusaLCE Surface controls (Toggle / Trigger / Encoder) from a physical Stream Deck. Pulso provides a Bitwig Bridge extension and a Stream Deck plugin; they talk to MusaLCEforBitwig over a dedicated OSC channel.

The full Surface protocol is documented in [pulso/docs/osc-protocol.md](https://github.com/javier-sy/pulso/blob/main/docs/osc-protocol.md). Stream Deck integration is currently **Bitwig only** — the Live side does not implement the Surface relay yet.

## Components

| Component | Repo | Used in standalone | Used in suite |
|---|---|---|---|
| [musa-dsl](https://github.com/javier-sy/musa-dsl) | core composition framework | ✅ | ✅ |
| [musalce-server](https://github.com/javier-sy/musalce-server) | REPL + sequencer + DAW handler + surface | — | ✅ |
| [MusaLCEforBitwig](https://github.com/javier-sy/MusaLCEforBitwig) | Bitwig controller extension | — | ✅ (Bitwig) |
| [MusaLCEforLive](https://github.com/javier-sy/MusaLCEforLive) | Live MIDI Remote Script | — | ✅ (Live) |
| [MusaLCEClientForVSCode](https://github.com/javier-sy/MusaLCEClientForVSCode) | VSCode REPL client | ✅ | ✅ |
| [Pulso](https://github.com/javier-sy/pulso) | Stream Deck bridge + plugin | — | optional (Bitwig only) |
