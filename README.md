# Q1 — VoiceArena Benchmark Blog

**Task:** Turn VoiceArena's vote log into a serious, publishable AI benchmark blog.  
**File:** `index.html` (self-contained, no dependencies)  
**Word count:** ~2,400 words  
**Audience:** TTS researchers, model builders, speech teams at frontier AI labs

---

## Topic Chosen

**"What 44,387 Human Votes Reveal About TTS Failure Across Six Languages"**

### Why This Topic

After studying the vote log, two things stood out as genuinely non-obvious:

1. **The comment/defect-tag layer is structurally different from every other TTS benchmark.** Most benchmarks produce scores. VoiceArena produces explanations. That distinction is worth an entire blog — because explanations let you diagnose, not just rank.

2. **Failure profiles are language-stratified in ways that aggregate leaderboards hide.** A model ranked third overall can rank first in English and sixth in Arabic. Those require different fixes. That finding isn't surfaced by win rates alone — it's only visible when you look at the comment and tag distribution by language.

The topic isn't "here are the leaderboard results." It's "here is what human feedback reveals about *why* models fail, and why that signal is more useful than the ranking itself." That's a meaningful difference, and it's a story that would interest the engineers and researchers at ElevenLabs, Cartesia, Google, and other teams whose models are being evaluated.

### What Was Rejected and Why

- **"Model X vs Model Y comparison"** — too close to generic benchmark marketing. Would feel like a press release for whoever ranked first.
- **"How VoiceArena works"** — methodology explanation is a means, not an insight. The audience already understands pairwise evaluation.
- **"Leaderboard update"** — score summaries without the failure analysis are low-information for model builders.

---

## Blog Structure

| Section | Purpose |
|---------|---------|
| How VoiceArena Works | Establish why pairwise + comments is structurally different from MOS-based eval |
| Five Failure Modes | Lead with the data — the distribution of defect tags across 44k votes |
| Prosody: Still the Hardest Problem | Deep dive on the #1 failure category and why automated metrics miss it |
| Pronunciation Failures Are Larger Than Most Benchmarks Suggest | 26k+ tags; multilingual transfer gap |
| Failure Profile Changes by Language | The core language-stratified insight |
| What Evaluators Notice That Metrics Often Miss | Table: evaluator complaints vs. automated metric coverage |
| Why Comments Beat Rankings for Model Improvement | The structural argument for qualitative feedback |
| Recommendations for Model Builders | Four actionable takeaways |
| State of TTS | Closing synthesis |

---

## Key Data Points Used

| Metric | Value | Source |
|--------|-------|--------|
| Total votes analyzed | 44,387 | VoiceArena vote log |
| Robotic/unnatural voice tags | 16,873 | Vote log defect tags |
| Mild mispronunciation | 16,222 | Vote log defect tags |
| Severe mispronunciation | 10,641 | Vote log defect tags |
| Irregular pacing | 10,499 | Vote log defect tags |
| Total pronunciation defects | 26,000+ | Combined mild + severe |
| Languages covered | 6 | EN, HI, JA, PT, VI, AR |

---

## Reference Material Studied

- **VoiceArena** — `voicearena.com`, `voicearena.com/tts-methodology`
- **LMArena / Chatbot Arena** — `lmsys.org/blog/2023-05-25-leaderboard/` — framing, how to present pairwise results
- **Scale AI Voice Showdown** — `scale.com/blog/voice-showdown` — how to make model comparisons credible to researchers
- **Speko Cartesia Drift blog** — `benchmarks.speko.ai/blog/cartesia-drift` — how failure analysis can focus on a single model without being a hit piece
- **Artificial Analysis** — `artificialanalysis.ai` — data density, how to present multi-model comparisons
- **LMArena X/Twitter** — studied how they distribute evaluation findings to technical audiences

---

## Design Decisions

- **Typography:** Playfair Display (headings) + Source Serif 4 (body) — editorial feel appropriate for a serious research publication, not a startup blog
- **Color:** Warm paper/ink palette with a terracotta accent — readable, credible, not corporate-blue
- **Layout:** Single-column article with sticky sidebar stats — mirrors how serious benchmark publications are structured (e.g., Artificial Analysis reports)
- **Data visualization:** Horizontal bar chart table for defect frequencies; language cards for the per-language breakdown; badge system for metric coverage gap table
- **No images or external media:** Everything renders from CSS and HTML — loads instantly, no broken assets

---

## What Was Not Changed

The blog is based entirely on real data from the VoiceArena vote log. No numbers were invented. No model names were named in ranking order (to avoid the piece reading as a press release for one model). The findings are presented as patterns from the data, not as absolute verdicts.
