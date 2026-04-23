# SemaLingua Compaction — OpenClaw Integration Proposal

## Problem
OpenClaw's built-in compaction uses prose summarization:
- Verbose (~30% compression)
- Loses semantic detail
- Burns tokens on the summary itself
- No structured format for cross-session continuity

## Solution: Two paths

### Path A: Custom `memoryFlush` prompt (works TODAY)

OpenClaw already has `compaction.memoryFlush` — a pre-compaction agent turn.
We override the prompts to write a SemaLingua handover instead of prose notes.

```json
{
  "agents": {
    "defaults": {
      "compaction": {
        "reserveTokensFloor": 20000,
        "memoryFlush": {
          "enabled": true,
          "softThresholdTokens": 4000,
          "systemPrompt": "Session nearing compaction. Write a SemaLingua-compressed handover of the FULL session to handover-compact.sl. Use: #tags, emoji glyphs (🔄✅❌🪛💡), [emotions], key:value notation, arrows (→) for causality. Preserve ALL facts: names, dates, URLs, numbers, decisions. Target 80-90% compression. This file will be read on session restart to restore full context.",
          "prompt": "Write the SemaLingua handover now to handover-compact.sl. Include: current goals, progress, blockers, decisions, technical state. Reply NO_REPLY after writing."
        }
      }
    }
  }
}
```

**Pros:** Works immediately, no code changes
**Cons:** The compaction itself is still prose (SL handover is just a safety net)

### Path B: Custom compaction engine (GitHub PR)

Add `compaction.mode: "custom"` with a user-defined compression prompt.

**Proposed config:**
```json
{
  "agents": {
    "defaults": {
      "compaction": {
        "mode": "custom",
        "customPrompt": "Compress the following conversation into SemaLingua format: #tags, emoji glyphs, [emotions], key:value, arrows. Preserve all facts. Target 80% compression.",
        "customSystemPrompt": "You are a SemaLingua encoder. Output only the compressed format."
      }
    }
  }
}
```

**What changes in OpenClaw core:**
1. `src/agent/compaction.ts` — add `custom` mode alongside `default`
2. When `mode === "custom"`, use `customPrompt` instead of built-in prose prompt
3. The compressed output replaces the conversation summary (same as today)
4. Fallback: if custom compression fails, use default mode

**Minimal diff:** ~50 lines in compaction handler + config schema update.

### Path C: Hook-based (cleanest, future-proof)

The hook proposal (GitHub Discussions) suggests `preCompaction` / `postCompaction` events.
A SemaLingua hook would:
1. `preCompaction` → intercept, write SL-compressed summary
2. Return the compressed text as the new conversation context
3. No core code changes needed — pure plugin

**Status:** Hook proposal exists but not yet implemented in OpenClaw.

## Recommendation

1. **Today:** Deploy Path A (memoryFlush override) — zero risk, immediate benefit
2. **This week:** Submit GitHub Issue proposing Path B (custom compaction prompt)
3. **Future:** Path C when hook system supports compaction events

## Impact
- 80-90% compression vs ~30% prose
- Structured format enables cross-agent context sharing
- SemaLingua becomes a standard cognitive layer, not just our internal tool
- Aligns with publication strategy (Substack, GitHub, whitepaper)
