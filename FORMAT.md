# SemaLingua Format Guide

Syntax reference for writing and reading SL documents.

---

## Structure

```
#tags                    # Compressed tags (lowercase)
@mentions                # Agent/people references
context: description     # What this document is about
goal: objective          # Primary objective
timeline: 🌙→❌→✅       # State progression glyphs
```

---

## Glyphs

| Glyph | Meaning |
|-------|---------|
| 🌙 | Night session / context |
| ❌ | Error / failure / blocker |
| ✅ | Success / resolved |
| 🔧 | Work in progress |
| 🔄 | Iteration / loop |
| 💡 | Insight / breakthrough |
| 🪛 | Debugging / fixing |
| 🚀 | Launch / deploy |
| 🎯 | Target / goal |
| ⚠️ | Warning / caution |
| 📝 | Note / documentation |

### Emotion Glyphs

| Glyph | Feeling |
|-------|---------|
| 😑 | Frustration / stuck |
| 😌 | Relief / satisfaction |
| 🤔 | Uncertainty / thinking |
| 😅 | Nervous / close call |
| 🎉 | Celebration / success |
| 😤 | Annoyance / irritation |

### Compound Emotions

Format: `[emotion1→emotion2]`

Example: `[frustration→stuck→relief]`

---

## Hierarchical Blocks

```
parent:
  child1: detail
  child2: detail
    grandchild: sub-detail
```

Indentation: 2 spaces per level.

---

## Tags

```
#tag              → Primary topic
#tag1 #tag2       → Multiple topics
#tag-subtag       → Hierarchical tag
```

Common tags:
- `#relay` `#debug` `#auth` `#deploy` — technical
- `#project` `#planning` `#decision` — project
- `#philosophy` `#ethics` `#design` — conceptual
- `#learned` `#insight` `#blocked` `#done` — state

---

## Mentions

```
@agent            → Single agent
@agent1 @agent2   → Multiple agents
```

---

## Lists

### Inline List
```
items: item1 | item2 | item3
```

### Block List
```
- item1
- item2
- item3
```

---

## Key-Value Pairs

```
key: value
```

Nested:
```
parent:
  child: value
```

---

## Timeline Sequences

```
state1 → state2 → state3
```

With timestamps:
```
🌙(20:00) → ❌(21:30) → 💡(22:15) → ✅(23:00)
```

---

## Recovery Test Format

```
## Recovery Test
| Question | Answerable? |
|----------|-------------|
| Q1 | ✅/❌ |
| Q2 | ✅/❌ |
```

---

## Comments

Lines starting with `#` are comments:
```
# This is a comment
key: value  # inline comment
```

---

## Best Practices

1. **One concept per block** — Don't cram too much into one section
2. **Causality explicit** — Show why, not just what
3. **Emotion when relevant** — Especially for creative/tricky sessions
4. **Tags front-loaded** — Tags at top help scanning
5. **Glyphs for states** — Visual scanning > prose scanning

---

*See also: [Compression Prompt](COMPRESSION-PROMPT.md) | [Examples](EXAMPLES.md)*
