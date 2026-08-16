# LABrador Five-Minute Presenter Script

> **Read only the normal text.** Bracketed text is a screen action. The timed script is approximately 650 spoken words. Fallback lines and judge answers come afterward and are not part of the five minutes.

## 0:00–0:35 — The need

There is an urgent global need to turn biomedical knowledge into novel, testable therapies faster.

For a disease like rheumatoid arthritis, the scientific record is enormous and fragmented. Manual review is slow and favors familiar targets. Generative AI can produce more ideas, but novelty without evidence is difficult to trust.

LABrador addresses both problems: it expands the hypothesis space, preserves scientific rigor, and exposes weak ideas before expensive laboratory and clinical work begins.

## 0:35–1:05 — Control the search

[POINT TO CONTROLS.]

We begin with rheumatoid arthritis.

The biomarker range controls **where we search**: level one is established; level ten is untested but plausible. We search the full range, with up to five biomarkers and one shared budget of one hundred papers.

Hypothesis boldness controls **how boldly we reason**. Here, we use levels one through six, with up to five hypotheses per biomarker.

The search expands. The audit standard does not change.

## 1:05–1:45 — Evidence to hypotheses

[OPEN KNOWLEDGE GRAPH.]

Paperclip retrieves the literature. Every accepted finding must resolve to a verified quote or it does not enter the graph.

Those findings become a knowledge graph of mechanisms, targets, disagreements, and unanswered gaps.

[OPEN HYPOTHESIS VIEW.]

From that graph, LABrador generates multiple competing hypotheses.

Each one retains its graph path, supporting evidence, serious objection, citations, and verification status.

We do not ask one model for one answer and then search for reasons to support it.

## 1:45–2:55 — Evaluate the hypothesis space

[SHOW EVALUATION RESULTS.]

The hypotheses fan out across mechanism and clinical evidence, small-molecule tractability, economic feasibility, and trial recruitability.

[OPEN TRACTABILITY.]

For molecular tractability, Paperclip retrieves real precedent—compounds, bioactivity, structures, and programs. Proto supplies computed structural evidence.

These axes can disagree. LABrador preserves the disagreement instead of averaging it into one misleading score.

[OPEN RECRUITABILITY.]

Recruitability uses real ClinicalTrials.gov precedent to estimate enrollment time and identify the binding constraint.

This is explicitly a simulation—not probability of approval.

[OPEN ECONOMICS.]

The economic model separates access, affordability, cash flow, and risk-adjusted value. Missing evidence remains missing; synthetic inputs remain labeled `NOT_DECISION_GRADE`.

Recruitment runs before economics, so enrollment delay can change launch timing and ROI.

## 2:55–3:30 — Close the loop

[OPEN NEXT ACTION OR COUNTERFACTUAL.]

LABrador generates and evaluates hypotheses across evidence, tractability, recruitability, and ROI. Scientists test the strongest candidate and feed the result back into LABrador. That result changes the knowledge graph and downstream evaluations, producing a revised hypothesis and next experiment.

## 3:30–4:10 — Inspectability and execution truth

[OPEN STAGE INSPECTOR OR MANIFEST.]

Every scientific conclusion traces from a verified quote, through the graph and hypothesis, into the evaluation.

The orchestrator then records what actually happened.

It pins module versions, validates every boundary, and separates stage status, actual execution, output origin, result basis, maturity, and warnings.

Live, cached, fallback, failed, and skipped are never silently conflated. If no honest input exists, the system abstains. If an artifact changes, its hash fails and the interface refuses to render it.

Judges do not have to trust the answer. They can reconstruct it.

## 4:10–4:40 — Validation and sponsors

[SHOW VALIDATION AND PROVENANCE.]

Our strongest external validation is the recruitment forecaster, which is backtested against completed trials.

Using only evidence available in 2018, it green-lit dupilumab for eosinophilic esophagitis four years before approval in that indication.

Paperclip and Proto are load-bearing: Paperclip grounds the literature graph and molecular precedent; Proto supplies computational tractability. The orchestrator preserves their provenance without rewriting it.

## 4:40–5:00 — Close

[RETURN TO OVERALL RESULT.]

LABrador moves from a rheumatoid-arthritis question, to verified evidence, to multiple controlled hypotheses, to multi-dimensional evaluation, and finally to a traceable next action.

It closes the loop. It is inspectable. It is externally validated where outcomes exist. And it uses sponsor tools for real scientific work.

More defensible ideas. More scrutiny. A better next experiment.

---



# One-Line Judge Answers

**What is novel?** We separately control where we search and how boldly we reason, then test multiple grounded hypotheses without lowering the audit standard.

**How do you close the loop?** Weaknesses become exact evidence requests or trial-design counterfactuals for the next cycle.

**How is it inspectable?** Every conclusion traces from source quote to graph to hypothesis to evaluation to manifest.

**How is it validated?** Recruitment is backtested against completed trials and has a leak-controlled historical hindcast.

**Where is Paperclip?** It is the literature source for the graph and supplies molecular precedent.

**Where is Proto?** It supplies computational structural evidence for tractability.

**Why rheumatoid arthritis?** It is evidence-rich, mechanistically complex, and recruitability can become decisive.

**Is recruitability approval probability?** No. It is modeled enrollment feasibility.

**Is ROI decision-grade?** Not with synthetic inputs; those outputs remain `NOT_DECISION_GRADE`.

**Did everything run live?** The manifest states exactly what was live, cached, fallback, failed, or skipped.
