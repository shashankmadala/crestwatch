# AI Disclosure

CrestWatch is a Congressional App Challenge 2026 entry. This file is the
plain record of how AI was used to build it.

> [!IMPORTANT]
> **The 2026 rules, word for word:** "The use of AI tools in app development
> for the Congressional App Challenge is permitted, provided that all AI
> usage is fully disclosed in the submission materials. AI may only be used
> to support specific aspects of the project and **must not constitute the
> entirety of the technical development**. Participants are expected to
> demonstrate significant individual contributions and technical
> understanding of their app."
>
> Right now AI has done the technical work in this repository. Every commit
> so far was made with Claude Code. All of them are tagged `[ai-assist]`
> except eight merge commits from Oct 23, 2026 titled "Merge branch
> 'cw/…' into integration", which Claude Code made while it combined its
> work packages. That does not meet the rule yet. **The
> student team must do real technical work themselves and commit it under
> their own names, without the `[ai-assist]` tag and without an AI
> co-author line, before submitting.** The list is under
> [What the team still has to do](#what-the-team-still-has-to-do).

## The product uses no AI

CrestWatch itself is public data and arithmetic: river gauge readings,
forecasts, ground heights, and subtraction. No AI model runs in the app or
makes any prediction. AI was used to build the software.

## Tools used

- **Claude Code (Anthropic).** An AI coding tool. It wrote the code, tests
  and docs described below.

## What AI wrote

Claude Code wrote essentially all of the application code, the tests, and
the docs in this repository, from the first commit on Aug 25, 2026 to now.
That includes:

- The project setup (Next.js, Vitest, Playwright, CI).
- All of the application code: the screens, the API routes, the adapters
  for the public data services, the verdict math in `lib/surveyor.ts`, and
  the verdict thresholds in `lib/config.ts` (`BANDS`).
- All of the words the app shows (`lib/copy.ts`), including the verdict
  sentences. No student has tuned them yet, even where an earlier comment
  in that file said "hand-tuned by the team". An AI commit wrote that
  comment.
- The unit tests, the end-to-end tests, and the recorded test data.
- The README, this file, `docs/SUBMISSION.md`, `docs/DEMO_SCRIPT.md`, and
  the empty template in `docs/VALIDATION.md`.
- An adversarial review of the verdict math, the API routes, the data
  adapters and the client trust boundaries. It found 19 real defects, for
  example a river that had already crested hiding a second crest still
  coming. They were fixed in commit `446f012` with regression tests.
- This week's audit (Oct 23, 2026): several Claude Code agents tested the
  app on desktop and mobile, checked accessibility, upstream data risks and
  the submission rules, and wrote a list of findings. Claude Code agents
  then fixed those findings in separate work packages. All of that code is
  AI-written too.

Commits made with Claude Code are tagged `[ai-assist]` in the commit
message. Eight are not: the merge commits from Oct 23, 2026 titled "Merge
branch 'cw/…' into integration". Claude Code made those too, while it
combined the work packages. So until the team commits its own work, every
commit in the history is AI work, tagged or not.

## What the team has done

TEAM: write this section yourselves, in your own words. List only what you
actually did (for example the idea, decisions you made, testing with
families, the validation pass). Leave it empty rather than guess.

## What the team still has to do

None of these is done. Tick a box only when the work is really finished and
committed by a student.

- [ ] **Validation pass.** Check 10 real addresses and the 2019 replay
      against NWS inundation maps, FEMA flood zones and news photos, and
      fill in `docs/VALIDATION.md` yourselves (steps in
      `docs/SUBMISSION.md`).
- [ ] **Threshold decision.** Decide the verdict bands in `lib/config.ts`
      (`BANDS`) from what the validation pass shows. Change them, or write
      in `docs/VALIDATION.md` why 0.5 ft and 3.5 ft stay.
- [ ] **About page stats.** Re-check the 2019 figures on the About page
      ("over half a million acres", "about six months") against Mississippi
      Today or MPB coverage, and add a source link.
- [ ] **The verdict sentences.** Read every verdict sentence in
      `lib/copy.ts` and change any you would say differently. Until you
      do, no comment in the code should say a student tuned them.
- [ ] **The video.** Film it yourselves, in your own voices, with each
      participant's name, and say that AI wrote the code
      (`docs/DEMO_SCRIPT.md`).
- [ ] **Explain the math.** Every teammate can explain, without notes, how
      gauge zero plus the river stage becomes the water's height above sea
      level, and how that is compared with the ground height at an address.
      Judges may ask, and the rules let them ask to see the source code.

## Where this disclosure goes in the submission

The rules say AI use must be disclosed "in the submission materials", not
only in this repository. Say it in the written answers (the technical
difficulty answer is a natural place) and in the video. `docs/SUBMISSION.md`
has the checklist.
