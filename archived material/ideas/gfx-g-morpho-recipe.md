# GFX G Morpho - parked idea (9 Oct 2026)

A vector / morphing additive synth, parked before any build. John's original recipe sketch is below as he supplied it
(it was a non-working outline: fixed 110 Hz pitch, no MIDI, a filter that reset every sample, output gain reading the
noise slider), followed by the build plan agreed in chat.

## Build plan (as proposed)
- Name: GFX G Morpho (no brand names).
- Four additive corner timbres A-D (bright saw cascade, hollow odd harmonics, nasal formant stack, metallic inharmonic),
  16-32 band-limited partials each, selectable spectra per corner, HARMONIC SPREAD 0.25-4.
- VECTOR X/Y pad (bilinear morph) with vector envelope and vector LFO; spectral noise layer.
- ZDF formant filter (200 Hz-10 kHz, LP/BP blend, key tracking, envelope); amp + filter ADSR; 8-voice poly, glide/mono,
  pitch bend, mod wheel, sustain; saturation drive; house instrument output section.
- Drift (best guess, to confirm): universal instrument drift plus a slow wander of the vector position.
- Iridescent / chameleon-inspired panel with a large vector pad, spectrum view, house preset bar; ~12 presets.

## Original recipe sketch
```
desc:Cameleonic Vector Synthesizer (Cameleon 5000 Emulation)
author:Custom
version:1.0
options:gmem=none

slider1:0.5<0,1,0.01>Vector X (A/B vs C/D)
slider2:0.5<0,1,0.01>Vector Y (A/C vs B/D)
slider3:1.0<0.25,4.0,0.01>Morph Harmonic Spread
slider4:1000<200,10000,1>Formant Center (Hz)
slider5:0.7<0.1,2.0,0.01>Formant Q / Resonance
slider6:2.5<1.0,10.0,0.1>Saturation Drive
slider7:0<0,1,1{Off,On}>Noise Generator (Spectral)
slider8:0<-24,12,0.1>Output Gain (dB)

Corner A: bright saw-like (1/n), B: hollow odd harmonics, C: formant-heavy nasal stack,
D: inharmonic bell partials (1, 1.414, 2.236, 3.162); bilinear vector weights
wA=(1-x)(1-y), wB=x(1-y), wC=(1-x)y, wD=xy; optional 128-band-style noise;
SVF formant filter (LP*0.5 + BP*1.5); atan saturation; output gain.
```
