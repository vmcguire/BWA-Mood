# BWA-Mood

Tiny UI plugin: set + broadcast the song's single emotion. Every other plugin reads from shared/emotion/.

**Category B** · **Tier 5** · part of the
[Bandwidth Audio](https://github.com/vmcguire) plugin ecosystem.

---

## What this is

BWA-Mood is the smallest plugin in the catalog and the most leveraged. Its only job: let the user pick the song's emotion (one enum + intensity + secondary modifiers) and broadcast that to shared/emotion/.

From there, every Cat B and Cat E plugin reads it and biases its output toward emotional coherence. The locked thesis: one song = one emotion. Set once per project. Constrains every downstream decision.

For the broader story of *what BWA is building and why*, see
[BWA-Architecture](https://github.com/vmcguire/BWA-Architecture) —
specifically:

- [`USER-STORY-MAP.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/USER-STORY-MAP.md)
  — where this plugin sits in the bedroom-producer journey (Stage 0 — CONCEIVE).
- [`ECOSYSTEM.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/ECOSYSTEM.md)
  — the full product map and the dual-surface / single-DSP architecture.
- [`docs/MARKET-PAIN-AND-ATTACKS.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/MARKET-PAIN-AND-ATTACKS.md)
  — what this plugin attacks (the pain it solves) and how.

## How this fits with the rest of BWA

BWA-Mood ships on **two surfaces** — same DSP, different UI:

1. **Standalone VST3** — drops into any DAW like a FabFilter / iZotope plugin.
   That's what this repo releases.
2. **Embedded cell inside BWA-Mix** — appears as a per-band / per-group cell
   processor inside BWA-Mix's track grid, sharing BWA-Mix's already-running
   band split and contributing to ecosystem-level cross-plugin features.

Both surfaces consume the **same authoritative DSP module**. Fix a bug once,
fixed everywhere.

## Status

🔴 Not built. Stub repo created as release destination. Build target: Phase E1.

## Releases

Versioned `.vst3` builds for macOS land in this repo's
[Releases](https://github.com/vmcguire/BWA-Mood/releases). Build from
source if you want — see `CLAUDE.md` for the dev surface (it's not this repo).

## License

Proprietary. Distribution + license terms pending storefront launch — see
[BWA-Architecture/docs/GO-TO-MARKET.md](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/GO-TO-MARKET.md).
