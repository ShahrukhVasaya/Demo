Read AGENTS.md and research_brief.md. Conduct the bounded investigation using
available search, source-reading, and filesystem tools. Do not use subagents.
Inspect existing reports and decisions first if any exist.

Choose searches based on unresolved questions. Read sources, record evidence,
and change direction when findings challenge the initial idea. Keep within the
search/retrieval budget. If tools are unavailable, report that and stop rather
than inventing actions. Preserve a unique run directory under runs/ using a
timestamp and short unique suffix; never overwrite a previous run.

Write these Markdown artifacts inside the run directory:
- activity_log.md: actual queries/URLs, actions, access failures, short reasons
  for search changes, cumulative budget counts, and stopping reason.
- literature_evidence.md: paper IDs, verified metadata, access level, question,
  geography, data, methods, findings, validation, and supporting section/page.
  Mark unknown information rather than guessing. Distinguish operational
  products from papers and note shared upstream data where verified.
- gap_assessment.md: candidate studies, supporting AND competing prior work,
  feasible data, unresolved assumptions, and what could invalidate a contribution.
- briefing.md: a 500–650 word spoken overview, references, and human decision
  questions. Include run ID, date, evidence limits, and a unique verification phrase.

Publish a self-contained copy of briefing.md at reports/latest.md. Include paths
to all preserved artifacts. Do not claim verified novelty or completed experiments.
If essential tools fail, produce an honest blocked-run record instead of a fabricated
briefing and clearly mark the status in reports/latest.md. Do not push yet.
