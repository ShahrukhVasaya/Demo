# Demo: single research agent

A supervised research workspace based on Edward Oughton's
[Week 6 notebook](https://github.com/edwardoughton/Agentic-GeoAI/blob/main/06_01_single_research_agent_github_voice.ipynb).
One local coding assistant chooses searches, reads sources, records evidence,
revises its investigation, and exports a briefing for human review.

**Status: setup complete; research has not been performed.**
The starting topic is U.S. inland-waterway freight, copied from the notebook's
example and editable in research_brief.md.

## Start an investigation

1. Open this repository in your local coding assistant. It needs web search,
   source-reading, and file-writing tools. This workflow requires no Python
   application, notebook kernel, or model API key; your assistant needs its
   normal account access.
2. Edit [research_brief.md](research_brief.md) for your topic. Add your candidate
   contribution and evidence that would undermine it.
3. Send the contents of [prompts/investigate.md](prompts/investigate.md) to the
   assistant. Explicitly tell it to read [AGENTS.md](AGENTS.md).
4. Inspect the new files under runs/. Check a cited source and its supporting
   section yourself. Review access labels, competing work, actual tool actions,
   and budget counts before publishing results.

The Markdown files configure your local agent; they do not start a background
service. The research loop is objective → search → inspect → record evidence →
choose next action → revise → stop. Only one agent performs research.

## Files and state

| Path | Purpose |
| --- | --- |
| AGENTS.md | Evidence standards and single-agent rules |
| research_brief.md | Topic, questions, scope, and stopping budget |
| prompts/investigate.md | Prompt that starts a bounded investigation |
| runs/ | Permanent evidence, activity log, gap assessment, and briefing per run |
| reports/latest.md | Self-contained latest briefing, initially marked pending |
| decisions/ | Human-reviewed decisions after discussion |
| prompts/review-by-voice.md | GitHub retrieval verification and discussion prompt |
| prompts/continue.md | Next investigation based on human decisions |
| CLAUDE.md | Points Claude Code to the shared research instructions |

Each run permits at most **6 queries, 8 source retrieval attempts, and 4 retained
papers**. Failed retrievals count. Stop earlier when sufficient evidence exists.
Unknown metadata stays unknown; no invented results or novelty claims.

## Publish reviewed research

After checking the files, stage the exact new run and any reviewed decisions,
alongside reports/latest.md and deliberately edited setup files. For example,
replace YOUR_RUN_ID before running these commands:

```powershell
git status --short
git diff --check
git add reports/latest.md runs/YOUR_RUN_ID
git diff --cached
git commit -m "Publish reviewed research investigation"
git push origin main
```

Do not commit credentials or restricted full texts. Preserve old runs and avoid
force-pushing. Verify the published report's run ID and phrase on GitHub.

## GitHub → phone discussion → local agent

Authorize this repository in your phone assistant's GitHub connection where
supported. Use [prompts/review-by-voice.md](prompts/review-by-voice.md) to retrieve
and verify the report in text before discussing it by voice. Connection and
voice support depend on your account; local Git sign-in is separate from the
phone assistant's repository access.

Review the discussion's decision summary and save it under decisions/ with its
run ID and date. Then use [prompts/continue.md](prompts/continue.md) with your local
assistant. This is a deliberate human handoff: phone discussion does not
automatically write files or launch another investigation.
