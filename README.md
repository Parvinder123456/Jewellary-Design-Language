# Jewelry Design Language (JDL)
**Version 0.1 — Engagement Rings**

A formal grammar for parsing, composing, and manufacturing Indian retail jewelry.

---

## 📖 The Thesis

Jewelers do not design from nothing. They recombine a finite vocabulary of known elements — shanks, heads, prongs, accents, finishes. A master in Karol Bagh, shown a Pinterest screenshot, silently parses it into this vocabulary and reproduces it. The vocabulary is transmitted through apprenticeship, not written down. 

**JDL writes it down.**

Once the grammar exists, three things become possible that are impossible today:
1. **Vision models** can parse photos into JDL (a classification problem they solve well) instead of generating 3D geometry (a problem they solve badly).
2. **A synthesizer** composes the JDL into CAD that is manufacturable by construction — because every primitive is pre-engineered to cast.
3. **The JDL itself** becomes a portable format jewelers, customers, casting houses, appraisers, and insurers can all read.

---

## 🏗️ Grammar Overview

JDL is hierarchical. A piece is composed of components. Components have required parameters and optional modifiers. Invalid combinations are not expressible — the grammar rejects them at parse time, which is why generated CAD is guaranteed manufacturable.

### Top-Level Structure

```yaml
piece: ring
  shank: <shank_element>
  head: <head_element>
  center_stone: <stone_element>       # required for engagement rings
  accent: <accent_element>            # optional, repeatable
  gallery: <gallery_element>          # optional
  finish: <finish_element>
  metal: <metal_spec>
  size: <size_spec>
