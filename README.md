# plain-explain

An OpenClaw skill: pick the clearest output format for every non-trivial answer.

Most answers arrive as a wall of dense text. This skill replaces that default with a
ladder. Climb only as far as the content needs.

## The ladder

1. **Plain writing (default)** — ASD-STE100-style controlled language. Short sentences,
   active voice, one term per idea, no jargon or filler. Tuned to about 80% of full
   ASD-STE100, so it stays warm and human. Full strength for procedures and
   correctness-critical content.
2. **Diagram** — use when the content is structure, flow, lineage, or comparison.
   A diagram that replaces three paragraphs is a win.
3. **HTML page** — use when the content is explorable: many items, interactive states,
   side-by-side options, a timeline. One self-contained file, no build step.
4. **Explainer video** — use when a concept is genuinely easier to watch than to read.
   Short generated clip, or a code-driven animation with TTS narration.

## Why

As models get better, more work moves up into oversight and understanding. The output
format then matters more than the volume of text. A custom artifact is cheap now.

## Install

Drop `SKILL.md` into your agent's skills directory, or install from ClawHub.

## Files

- `SKILL.md` — the skill.
