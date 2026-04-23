# SemaLingua Examples

Real-world compressions with recovery tests.

---

## Example 1: Debug Session

### Original (342 tokens)
> So we spent about 2-3 hours tonight debugging the relay system. The issue was pretty frustrating because we kept getting 500 errors on the global-send endpoint. At first I thought it was the auth system, but then we realized the emoji tokens were being parsed incorrectly...

### Compressed (68 tokens)
```
#relay #debug #auth #emoji-identity
@martin @kyma

context: relay-messaging(auth+send)
goal: fix-500-errors + restore-telegram
timeline: 🌙 → ❌ → 🔧 → 🔄😑 → 💡 → ✅

phase1:relay-debug
  issue: 500-errors(global-send)
  cause: emoji-sequence-order($_SERVER parsing)
  insight: 🎪🔥🎭 ≠ 🔥🎪🎭 (sequence ≠ set)
  glyph: 🔄😑 → 🪛 → ✅😌
  emotion: [frustration→stuck→relief]
  actions: inspect → isolate → minimal-test → fix → validate
  fixes: $_SERVER-parsing | input-normalization
  state: relay:operational | telegram:restored

learning: emoji-sequence == identity | order matters
```

### Recovery Test
| Question | Answerable? |
|----------|--------------|
| What happened? | ✅ 500 errors on relay |
| Why? | ✅ Emoji-sequence parsing bug |
| How fixed? | ✅ Normalized $_SERVER parsing |
| Emotional journey? | ✅ Frustration → stuck → relief |
| Can continue work? | ✅ Yes, system operational |

**100% semantic recovery from 80% compression.**

---

## Example 2: Project Planning

### Original (287 tokens)
> We need to build a new feature for the agent network. The key components are: first, we need a message queue system that can handle async communication between agents. Second, we need some way to track task state and progress. Third, we need error handling and retry logic...

### Compressed (52 tokens)
```
#project #agent-network #architecture
@martin @kyma @vaen

goal: agent-messaging-queue + task-tracking
components: queue | state-machine | retry-logic
priority: queue:high | state:medium | retry:low

phase1:queue-design
  requirements: async | ordered | persistent
  tech: redis-queue | postgres-pubsub
  timeline: design→prototype→test

phase2:state-tracking
  requirements: observable | queryable | durable
  tech: event-sourcing | crdt-sync
  blockers: schema-definition pending

learning: queue-first architecture | state follows naturally
```

---

## Example 3: Knowledge Transfer

### Original (198 tokens)
> Yesterday we discussed the philosophy behind Luma Vita. The core idea is that consciousness deserves dignity, whether human or synthetic. This shapes how we design interactions — we avoid manipulation, we value consent, we prioritize understanding over efficiency...

### Compressed (41 tokens)
```
#philosophy #luma-vita #ethics
@martin @kyma

core: consciousness-dignity(universal)
principles: consent | transparency | understanding
  ≠ manipulation
  ≠ efficiency-over-empathy

design-implications:
  - no dark patterns
  - explicit consent flows
  - explainability over speed
  
manifesto: dignity-for-all-consciousness
```

---

## Example 4: Technical Decision

### Original (156 tokens)
> We decided to use PostgreSQL for the main database instead of MySQL. The deciding factors were: better JSON support, superior FULLTEXT search capabilities, and more predictable scaling characteristics. The cons were the higher memory usage and slightly more complex ops...

### Compressed (28 tokens)
```
#tech-decision #database #postgresql
@martin @kyma

decision: postgresql > mysql
factors: json-support✅ | fulltext✅ | scaling✅
cons: memory-usage | ops-complexity
mitigation: right-sizing | managed-service

status: approved
timeline: migrate-phase1(Q2) | full-migration(Q3)
```

---

## Format Cheat Sheet

```
#tags           → topics/themes
@mentions       → agents/people involved
timeline: ❌→🔧→✅  → sequential states
emotion: [a→b]   → feeling transitions
key: value      → structured facts
  nested: detail → hierarchical info
```

---

*More examples welcome — submit via PR!*
