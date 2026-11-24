# Free Lite: The Judge Calibrator Agent

**One file. The most quoted, least verified number in AI development,
audited.**

Every team shipping an agent has a judge score: "the new prompt scores
4.6 out of 5." Almost none of them can answer the follow-up question —
*how often does that judge agree with a human on your data?* Until that
number exists, the judge score is evidence about the judge, not about
your system. And uncalibrated judges have habits: they pass nearly
everything, they reward confident verbosity, they grade their own
model family's outputs more leniently, and they drift silently when
the model behind them changes.

This free agent replaces the vibe with a measurement. It writes an
anchored rubric before it writes a prompt, builds a calibration set
labeled by a human first, and reports agreement the honest way — raw
agreement *and* Cohen's kappa, false passes separated from false
fails, and bias experiments (position, verbosity, self-preference)
run as tests, not suspicions. Its verdict is one of three: the judge
may gate, may only advise, or is not usable yet — with the numbers
that decide it.

## Install (2 minutes)

1. Copy `judge-calibrator.md` into `~/.claude/agents/` (create the
   folder if it doesn't exist).
2. Add this line to your global `~/.claude/CLAUDE.md`:

   ```
   - Any LLM-as-judge work goes to the judge-calibrator subagent. No judge gates a release until its agreement with human labels is measured on our data.
   ```

3. Start a fresh session and point it at the judge your team already
   quotes. Judge the agent by its output: a calibration report with
   kappa and false-pass rate, and a gate/advise/unusable verdict. If
   your judge is solid, you'll get the proof. If it isn't, you'll get
   the exact experiment that shows where it breaks.

## The catch (there isn't one — there's a full kit)

A calibrated judge is one of the five eval jobs that decide whether
an agent is actually improving. The full **Agent Evals Starter Kit
for Claude Code** covers the other four, in the same style:

- **eval-designer** — suites built from named claims, the cheapest
  honest grader per claim, pass bars set before results exist
- **golden-dataset-builder** — golden sets from real traces and
  incidents: verbatim inputs, defensible labels, decontamination
  checks, gaps named in writing
- **regression-diff-analyst** — run comparisons case-by-case: what
  flipped, why, and whether the movement is inside the noise band
- **red-team-prober** — adversarial probe ladders against named
  claims, with the benign-lookalike controls that catch over-broad
  guardrails too
- Plus the guide: routing lines for all five, a worked example each,
  and one end-to-end run from "no evals" to a gated release decision

FULL KIT: https://fleetops.gumroad.com/l/zoyte

_Free lite license: use it personally or in your business, modify it
as you like. Please don't resell it. Not affiliated with Anthropic._
