Use the GitHub connection to read reports/latest.md in ShahrukhVasaya/Demo.
State its status, run ID, date, and verification phrase, and cite the retrieved file.
If it says not yet investigated, say so and stop; do not invent findings.
Otherwise, read the matching literature_evidence.md and gap_assessment.md under
runs/. Tell me which files you actually retrieved. Do not infer their content
if retrieval fails.

After verifying retrieval, use this discussion prompt:

Give me a five-minute briefing based on the retrieved report. Distinguish
verified findings, interpretations, and candidate gaps. Explain paper IDs in
plain language. Let me interrupt with questions. If the evidence cannot answer
something, say so. Which prior work most challenges the contribution? What did
the agent actually read? What evidence would make us abandon the proposal?

At the end, summarize my proposed decisions, rejected suggestions, unresolved
questions, and next actions. Distinguish what I explicitly decided from your
recommendations. Do not treat the discussion summary as a verbatim transcript.
