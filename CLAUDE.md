# BWA-Mood — read before doing anything

> ✅ **This is the CANONICAL home for BWA-Mood.** All serious DSP, IP, and
> process for this plugin live **here**, in `~/Developer/BWA-Mood/`. Author here — always.
>
> The `bwa-fx-ecosystem` monorepo is **NOT** a second source of truth for this
> plugin — it is only a build/assembly workspace that gives **BWA-Mix** the slice
> it needs to embed this FX as a *cell* (via a **symlink** back into this repo).
> **Never author plugin IP in the monorepo.** If any of this plugin's DSP still
> lives inside BWA-Mix or a monorepo copy, the job is to bring it **here** — the
> standalone is always the destination.
>
> **Why:** every BWA plugin ships two surfaces — standalone VST3 **and** an
> embedded BWA-Mix cell — off **one** canonical `dsp/` module that lives in this
> repo. Single-source DSP is locked (`ECOSYSTEM.md` Principle 3).
> Topology: `BWA-Architecture/docs/REPO-CANONICALIZATION-PLAN.md`.

## What this plugin is

- **Category:** B (Generative / Emotional — UI plugin)
- **Tech tree tier:** Tier 5
- **Role:** Project-level emotion state writer. Reads/writes shared/emotion/.
- **Pain attacked:** Make emotion a first-class project-level state. No DAW does this; without it, every micro-decision is in an emotional vacuum.
- **Scope verdict:** project-global (it's the thing every other plugin reads)
- **Band tier behavior:** Not tier-gated. The emotion bus is foundational.

Full row in
[`MARKET-PAIN-AND-ATTACKS.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/MARKET-PAIN-AND-ATTACKS.md)
— search for `BWA-Mood`.

## Before you write code — the canonical guides (single source of truth)

> These are maintained in **one place** so they stay correct as the ecosystem
> changes. This file deliberately holds only what is specific to BWA-Mood; every
> general rule — required reading, what to reuse, what to publish, the
> anti-patterns, the done-checklist, the release ritual — lives in the docs
> below. Do not re-derive a rule that isn't here; look it up there.

Read in order (all under `~/Developer/BWA-Architecture/`):

1. **`docs/LLM-ONBOARDING.md`** — thesis, 6-category taxonomy, locked decisions, anti-patterns. **Read first.**
2. **`docs/REUSE-MAP.md`** — what already exists and where. Reuse, never rebuild (band split, meters, Metal, widgets, brand theme, constants).
3. **`docs/PLUGIN-AUTHORING.md`** — the build drill: dev surface, dual-surface contract, **what you must publish for other workers**, the done-checklist, the release ritual.
4. **`docs/MARKET-PAIN-AND-ATTACKS.md`** — the row for **BWA-Mood**; internalize the pain + attack before any DSP.

(On GitHub: browse these under `vmcguire/BWA-Architecture/docs/`.)

## Release ritual

This repo is canonical — release straight from it. After the release commit on `main`:

```bash
git push origin main
```

Then cut a GitHub Release here (`vmcguire/BWA-Mood`) and attach the notarized `BWA-Mood.vst3`.
No `git subtree push` from the monorepo — that flow is retired. See `docs/PLUGIN-AUTHORING.md §7`.
