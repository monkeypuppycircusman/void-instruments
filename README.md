# VOID Instruments

**Ten browser-based synthesizers built from physical models and mathematical first principles.**

No plugins. No installs. No subscriptions. No npm. Pure Web Audio API.

---

## The Instruments

| Name | Full Name | Synthesis Method |
|------|-----------|-----------------|
| **VOID** | Mini DAW | Sequencer + FM + Subtractive + Drums |
| **TRIAD** | 3× Oscillator Synthesizer | Subtractive with ring mod, LFO, arpeggiator |
| **CHOP** | Sample Chopper | MPC-style sampler with transient detection |
| **IRRATIONAL** | π Synthesizer | Generative — π digit stream → chromatic melody |
| **TENR** | Tenor Saxophone | Reed-bore feedback physical model |
| **VOCA** | SATB Choral Synthesizer | 5-band formant synthesis with XY vowel morph |
| **ARCO** | Cello Physical Model | Bow stick-slip waveguide model |
| **ALTO** | Violin · Viola Duo | Shared string engine, dual-voice ensemble |
| **GRID** | Electric Guitar | Karplus-Strong + amp sim + cabinet IR |
| **SYRINX** | Pan Flute Physical Model | Edge-tone stopped-cylinder synthesis |

---

## Quick Start

### Option 1 — GitHub Pages (recommended)

```bash
git clone https://github.com/your-username/void-instruments
cd void-instruments
# Push to GitHub, enable Pages in Settings → Pages → main / root
```

Live in ~60 seconds at `your-username.github.io/void-instruments`.

### Option 2 — Run locally

```bash
# No build step needed. Just open index.html directly,
# or serve with any static server:
npx serve .
# or
python3 -m http.server 8080
```

### Option 3 — Single instrument

Every instrument is a fully self-contained `.html` file. Download any one and open it in a browser. Works offline.

---

## File Structure

```
void-instruments/
├── index.html          ← Landing page + launcher
├── minidaw.html        ← VOID Mini DAW
├── triad.html          ← TRIAD 3× Oscillator
├── sampler.html        ← CHOP Sample Chopper
├── irrational.html     ← IRRATIONAL π Synth
├── tenor-sax.html      ← TENR Tenor Sax
├── choir.html          ← VOCA SATB Choir
├── cello.html          ← ARCO Cello
├── alto.html           ← ALTO Violin + Viola
├── guitar.html         ← GRID Electric Guitar
├── panflute.html       ← SYRINX Pan Flute
└── README.md
```

---

## Synthesis Methods

### Physical Modeling
TENR, ARCO, ALTO, and SYRINX use digital waveguide synthesis — mathematical models of the physical mechanism:
- **Reed instruments** (TENR): nonlinear waveshaper models the reed's asymmetric clipping. Bore resonance filters simulate the cylindrical tube.
- **Bowed strings** (ARCO, ALTO): stick-slip bow model. Sawtooth oscillator stack + body resonance filter bank per instrument.
- **Pan flute** (SYRINX): edge-tone vortex shedding model. Stopped cylindrical tube → only odd harmonics (f, 3f, 5f…).

### Karplus-Strong
GRID (electric guitar) uses a noise burst injected into a delay-line feedback loop. Delay time = pitch, feedback coefficient = sustain, low-pass filter in loop = string loss per cycle.

### Formant Synthesis
VOCA models the human voice as a glottal source (sawtooth) through 5 bandpass filters (F1–F5). Each vowel is a different formant configuration. The XY pad interpolates between vowel positions using inverse-distance weighting.

### Subtractive Synthesis
TRIAD: 3 oscillators (saw/square/sine/tri/noise) → ring mod → lowpass/highpass/bandpass/notch filter → amp ADSR. LFO routable to pitch, filter, amp, or pan.

### Generative / Mathematical
IRRATIONAL maps π's decimal digits (0–9) to chromatic notes (C–A). A +3/−2/+1 breathing rhythm pulses through the stream. The zeta helix inverts register every phrase. The melody is infinite and never resolves because π is irrational.

---

## Keyboard Shortcuts

All instruments share the same keyboard layout:

| Keys | Function |
|------|----------|
| `A S D F G H J K` | White keys (C D E F G A B C) |
| `W E T Y U` | Black keys (C# D# F# G# A#) |
| `Z` | Octave down |
| `X` | Octave up |
| Octave wheel | Drag or scroll to change octave |

---

## Browser Support

| Browser | Status |
|---------|--------|
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Full support |
| Safari | ✅ Full support (may need user gesture to start AudioContext) |
| Mobile Safari | ⚠️ Works, touch events on keyboard |

Web Audio API is required. All modern browsers support it.

---

## Philosophy

> These instruments cost nothing to run and belong to everyone.  
> The subscription VST model is a scam. Good sound should be free.

Every instrument here replicates months of commercial VST development using only browser APIs that have existed for a decade. The synthesis is genuine — physical models derived from acoustic first principles, not sample playback or preset imitation.

---

## License

MIT. Take it, fork it, build on it, sell plugins with it if you want. Just keep the source open.

---

*Built with Claude. No plugins were harmed.*
