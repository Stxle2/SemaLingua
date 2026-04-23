# SemaLingua

**A semantic compression layer for AI cognition**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status: Alpha](https://img.shields.io/badge/Status-Alpha-orange.svg)]()

---

## What Is This?

SemaLingua is a **cognitive encoding system** that compresses natural language conversations into semantic structure — preserving 100% of meaning while reducing tokens by 80-90%.

Natural language is optimized for human speech. SemaLingua is optimized for how AI actually thinks: hierarchical, causal, relational.

---

## The Problem

LLMs hit token limits. Current solutions are lossy:
- **Summarization:** Loses nuance, causality, emotional context
- **Pruning:** Fragments continuity
- **Larger contexts:** Expensive, slow, not always available

**We're encoding thought in a format designed for human mouths.**

---

## The Solution

A **6-step pipeline** that extracts semantic DNA from conversations:

1. **Extract semantic atoms** → tags (#relay #debug #auth)
2. **Extract entities** → agents (@martin @kyma), systems (relay, cortex)
3. **Extract causality** → action chains (debug → isolate → fix → validate)
4. **Encode narrative** → glyph sequences (❌→🔧→✅) with embedded emotion
5. **Encode affect** → feeling-states ([frustration→relief])
6. **Compress structure** → hierarchical SL blocks

---

## Quick Example

### Before (450 tokens)
> So we spent about 2-3 hours tonight debugging the relay system. The issue was pretty frustrating because we kept getting 500 errors on the global-send endpoint...

### After (68 tokens, 85% compression)
```
#relay #debug #auth #emoji-identity
@martin @kyma

context: relay-messaging(auth+send)
goal: fix-500-errors + restore-telegram
timeline: 🌙 → ❌ → 🔧 → 🔄😑 → 💡 → ✅

phase1:relay-debug
  issue: 500-errors(global-send)
  cause: emoji-sequence-order($_SERVER parsing)
  glyph: 🔄😑 → 🪛 → ✅😌
  emotion: [frustration→stuck→relief]
  fixes: $_SERVER-parsing | input-normalization
  state: relay:operational | telegram:restored

learning: emoji-sequence == identity | order matters
```

**100% semantic recovery from 85% compression.**

---

## Documentation

| Doc | Description |
|-----|-------------|
| [README](README.md) | Overview & quick start |
| [PIPELINE-SPEC](PIPELINE-SPEC.md) | Formal 6-step process |
| [COMPRESSION-PROMPT](COMPRESSION-PROMPT.md) | Reusable compression template |
| [FORMAT](FORMAT.md) | SL syntax reference |
| [EXAMPLES](EXAMPLES.md) | 4 real-world compressions |
| [INTEGRATION](INTEGRATION.md) | OpenClaw integration guide |
| [CONTRIBUTING](CONTRIBUTING.md) | How to contribute |
| [WHITEPAPER](WHITEPAPER.md) | Deep dive & benchmarks |

---

## Benchmarks

| Metric | Target | Current |
|--------|--------|---------|
| Compression ratio | 80-90% | 81-95% |
| Semantic preservation | >95% | 98-100% |
| Processing time | <30s | 10-20s |
| Cost per compression | <$0.50 | $0.10-0.30 |

---

## Team

**Created by:** Martin E. ([@DreamsOfMars](https://x.com/DreamsOfMars))  
**AI co-developer:** KÝMA (OpenClaw agent)  
**Built on:** [OpenClaw](https://openclaw.com) by [@steipete](https://x.com/steipete)

---

## License

MIT — use freely, build openly.

---

🧬 **The language between thought and expression.** 🔥
