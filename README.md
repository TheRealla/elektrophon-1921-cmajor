# Elektrophon 1921 — Pure Cmajor Emulation

A historically faithful digital recreation of **Jörg Mager’s Elektrophon (1921)** — one of the very first electronic musical instruments using heterodyne (beat-frequency) synthesis.

This patch is written entirely in **Cmajor**, delivering clean, real-time DSP with zero bloat.

## Historical Context

In 1921, German inventor and microtonal visionary **Jörg Mager** (1880–1939) built the **Elektrophon** while working with discarded vacuum tubes at the Lorenz radio factory in Berlin. Inspired by Ferruccio Busoni’s ideas on electronic music and Pythagorean "music of the spheres," Mager sought an "Alltongerät" — an ideal instrument capable of producing any frequency continuously, free from the discrete steps of keyboards or acoustic limitations.

The Elektrophon used two high-frequency oscillators (~50 kHz) whose difference produced audible beat tones — the same principle as Lev Termen’s Theremin (developed around the same time). Unlike the antenna-controlled Theremin, Mager’s design featured a **rotatable metal handle** (crank) for smooth, continuous glissando/portamento, with a semicircular chromatic/color-coded dial as a visual guide. Timbre came from basic filtering.

No original Elektrophon survives (lost to WWII bombing), and few (if any) direct sound recordings exist. This emulation revives its raw, unstable, vocal-like character for modern continuous controllers.

Later evolutions became the **Sphärophon** (1924), **Kurbelsphärophon** (1926 crank version), **Klaviatursphärophon** (1928 keyboard variant), **Partiturophon** (1930), and **Kaleidophon** (1939).

**Sources**: 120 Years of Electronic Music archive, Elektrische Klangmaschinen (Peter Donhauser, 2007), Wikipedia, contemporary accounts.

## Features

- True heterodyne synthesis: fixed ~50 kHz carrier beats against variable oscillator
- Fully continuous pitch (~15 Hz – ~12 kHz exponential range)
- Microtonal / infinite resolution — no steps
- Simulated crank inertia (velocity + damping) for mechanical feel
- Slow analog-style frequency drift / wobble for vintage instability
- Primitive one-pole timbre shaping with light resonance
- Direct amplitude control (no ADSR envelope — always "on" like early instruments)
- Soft saturation to tame peaks

## Controls / Parameters

| Parameter     | Range   | Description                                      | Typical Controller          |
|---------------|---------|--------------------------------------------------|-----------------------------|
| `pitchControl`| 0–1     | Continuous pitch mapping (exponential)           | Ribbon, MPE X-axis, knob    |
| `ampControl`  | 0–1     | Master amplitude / expression                    | Foot pedal, MPE pressure    |
| `timbre`      | 0–1     | Subtle tone color / resonance amount             | Knob, MPE Y-axis            |

## Philosophy

This is **not** a conventional synth plugin.

It is built as:

- A **continuous performance instrument**
- A **microtonal sound source**
- An expressive tool closer in spirit to voice, violin, or singing saw than piano/keyboard

Expect gliding tones, beating artifacts, slow portamento, and gentle instability — perfect for ambient, drone, experimental, or historically informed electronic music.

## Sound Character

Expect a somewhat hollow, ring-mod-like tone with characteristic heterodyne beating (especially at low pitches), slow warble from drift, and a raw, almost vocal quality when played expressively. The inertia makes large pitch sweeps feel physical and deliberate.

## Recommended Controllers

To get the most out of the continuous nature:

- Ribbon controller (e.g. Korg Kaossilator-style or Doepfer ribbon)
- MPE surfaces: Linnstrument, ROLI Seaboard, Haken Continuum, Joué Play
- High-resolution MIDI knob/fader + expression pedal
- Any smooth, high-resolution continuous controller

Avoid standard keyboards — they defeat the purpose.

## How to Use

1. Install a **Cmajor host/player**:
   - Cmajor reference host (https://github.com/cmajor-lang/cmajor)
   - Compatible DAWs/plugins via Cmajor export (VST3/AU/standalone coming soon)
   - Web-based Cmajor playground (if available)

2. Load `Elektrophon1921.cmajor`

3. Map your controller:
   - Pitch → pitchControl (0–1 full range)
   - Expression/pressure → ampControl
   - Mod wheel or secondary axis → timbre (start around 0.3–0.6)

4. Play slowly and expressively — embrace the glissandi and instability.

## Building / Modifying

The synthesis lives in a single file: `Elektrophon1921.cmajor`

- Edit parameters (carrierFreq, drift amount, inertia constants, etc.)
- Add stereo detune, LFO drift, better saturation, or output filtering if desired
- Cmajor compiles to efficient WebAssembly/LLVM — great for low-latency performance

## License

MIT License  
Copyright © 2026 theRealla (@realla_the)

Feel free to fork, modify, extend, or use in your projects. Attribution appreciated but not required.

If you make something cool with this — tag me @realla_the on X — I'd love to hear it.

Crank it, glide it, let the spheres sing. 🎛️✨
