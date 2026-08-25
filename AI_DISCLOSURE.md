# AI Disclosure

CrestWatch is a Congressional App Challenge entry. Competition rules allow
AI tools with full disclosure, as long as AI is not the entire technical
work. This file is the running record of that disclosure. Commits where AI
wrote code are tagged `ai-assist` in the commit message.

**The product itself uses no AI.** CrestWatch is public federal data and
arithmetic — gauge readings, elevations, and subtraction. AI was used to
build the software, not to make predictions.

## Tools used

- Claude Code (Anthropic) — code scaffolding and implementation assistance

## What AI wrote

- Project scaffolding (Next.js, Vitest, Playwright, CI)
- First drafts of application code, marked `ai-assist` in git history

## What the team wrote / owns

The team is responsible for — and must be able to explain — every part of
this list. Items start as AI drafts and are hand-tuned by the team before
submission:

- [ ] The Surveyor verdict thresholds (`lib/config.ts` BANDS) — tuned
      against the Appendix H validation pass
- [ ] The verdict sentence copy (`lib/copy.ts`)
- [ ] The accuracy validation (`docs/VALIDATION.md`) — 10 real addresses
      checked against NWS inundation maps and 2019 flood photos
- [ ] The story stats on the About page, re-verified against sources

Judges will ask how the elevation math works. The explanation the team
gives must be their own.
