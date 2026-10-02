---
name: plain-explain
version: 1.0.0
description: Use for non-trivial explanations and reports in chat — write plain, then escalate to diagram, HTML page, or explainer video when writing is not enough.
---

# Plain Explain — Output Format Ladder

Default posture for every non-trivial answer: **make it readable on the first pass.**
Writing is only rung 1. If writing is dense, skip up the ladder.

## Step 1: Write in STE-style plain prose

Write the answer as if the reader must act on it without asking a follow-up question.

Rules:
- One idea per sentence. Short sentences.
- Active voice. Present tense. Name the actor.
- One term per idea — do not alternate synonyms.
- No idioms, no hedging filler, no "obviously", no "simply", no "technically".
- Do not use a word the reader has not seen you define.
- Keep the answer's own vocabulary consistent so it can be referenced later.

Softening: users often find full ASD-STE100 too stiff. Default to **~80% of the way to ASD-STE100** — plain and disciplined, still warm and human. Use full-strength STE when the content is a procedure, an instruction, or a safety/correctness matter.

**Done when:** a reader who knows nothing about the topic can state what happened, what it means, and what to do next.

## Step 2: Escalate when writing is the wrong shape

Ask: is the cost of prose higher than the cost of another format?
Pick one rung and produce it. Do not ask permission for a format inside the tool budget.

**Diagram** — use a diagram when the content is structure, flow, lineage, or comparison.
- Reach for `diagram-maker` (SVG/HTML/Excalidraw) or a mermaid block.
- A diagram that replaces 3 paragraphs is a win. Attach it, keep the caption to one line.

**HTML page** — use a page when the content is explorable: many items, interactive states, side-by-side options, a timeline, a dashboard-like view.
- Write a single self-contained `.html` file (inline CSS/JS, no build step) and send it, or open it in the browser when it needs a live view.
- Beautiful and interactive beats complete. Ship what is usable, then offer to extend.
- Treat it as a discardable artifact — no one needs to maintain it.

**Explainer video** — use video for a concept that is genuinely easier to watch than to read (visual, sequential, spatial).
- Use `video_generate` for short clips, or build a code-driven scene (e.g. a "3b1b style" animation with `manim`) for a narrated explainer.
- Narration: use `tts` (ElevenLabs if configured). If no key is available, generate local audio with an open-source TTS and say which one you used.
- Prefer a real, working clip over a perfect plan.

**Done when:** the chosen artifact exists and is attached or linked, not just described.

## Step 3: Bind it to the workspace

This skill is a standing behavior for this workspace, so it also lives in `SOUL.md` as a short directive. Keep both in sync:
- `SOUL.md` holds the one-paragraph rule.
- This file holds the full procedure.
If one changes, change the other in the same pass.

**Done when:** `SOUL.md` links to this skill and the two describe the same behavior.

## Step 4: Verify before sending

- Read your own draft once as the reader. If any sentence needs the previous sentence to be understood, merge them.
- If you chose a higher rung, confirm the artifact is actually attached (path/URL/media), not merely announced.
- If a rung failed (video provider down, no TTS key), drop one rung and ship that, then state the limitation in one line.
