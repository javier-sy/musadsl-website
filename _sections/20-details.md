---
anchor: details
title: MusaDSL in detail
menu: Details
order: 20
---
MusaDSL separates compositional logic from audio rendering, letting you build complex musical
structures independently of the devices used to play them.

The devices can be anything you can connect to via MIDI (Synths, DAWs, etc.), OSC (Max/MSP, SuperCollider, PD, etc.)
or any other protocol you implement to connect to your sound generating artifacts.

This architecture supports the exploration of generative systems, algorithmic composition and live coding.

### Key features

- **Advanced sequencer** with microsecond precision for polyrhythmic and polytemporal structures, with multiple clock sources (internal, MIDI, external).
- **Generative tools**: Markov chains, Variatio, GenerativeGrammar and Darwin genetic algorithms.
- **Series**: lazy iterators with functional operations (transform, filter, invert, combine, slice, repeat) and specialised generators (Fibonacci, harmonic series, constrained random).
- **30+ scales and modes** in 9 families (Greek modes, pentatonic, blues, symmetric, bebop, ethnic, melodic minor&hellip;) with equal-temperament and just-intonation support.
- **Chord system** with quality, extensions, voicings and chord&ndash;scale navigation.
- **Datasets and Score**: structured representation of musical events (scale grades, MIDI pitches, dynamics) with multi-voice organisation.
- **Neumalang** &mdash; textual notation system with support for scale grades and ornaments.
- **Matrix operations** for transforming sonic and musical structures.
- **Transcription** to MIDI and score generation in MusicXML with ornament expansion.
- **Cross-platform MIDI communication** for connecting to instruments and controllers.
- **Polyphonic MIDI voice management** with automatic voice allocation.

MusaDSL is free software, GPL-3.0-or-later: see [License](#license) for what that
means for you and for the commercial license.
