# Concise Presenter Notes


## 1. Problem

There is an urgent global need to turn the growing volume of biomedical knowledge into novel, testable therapeutic ideas faster.

Today, critical connections remain buried across papers, databases, molecular evidence, and clinical results, slowing discovery and delaying treatments for diseases.

The United States needs this capability to strengthen its scientific leadership, biotechnology sector, and health security;

Other countries need it to access advanced drug-discovery reasoning without requiring enormous research teams;

and the world needs it to respond more quickly to chronic diseases, rare conditions, and emerging health threats.

Our system addresses this need by generating multiple evidence-grounded hypotheses, testing them across scientific and real-world constraints, and showing researchers which experiment is most defensible to run next.


One clinical indication can produce many plausible mechanisms, targets, and experiments.

Choosing the wrong path early sends every downstream step in the wrong direction.

But the evidence needed to choose is fragmented across literature, biological databases, molecular tools, clinical trials, and economic constraints.

A conventional AI system gives us one confident answer. We need to know which hypothesis deserves the next experiment, and why.

## 2. Solution

**`[LABrador]` is an inspectable co-scientist for therapeutic discovery.**

We begin with a clinical indication.

Paperclip retrieves the literature, and every accepted finding is tied to a verified quote.

Those findings become a knowledge graph of mechanisms, targets, relationships, disagreements, and gaps.

From that graph, we generate **multiple competing hypotheses**.

Each hypothesis carries its graph path, supporting evidence, objections, citations, and verification status.

## 3. Controlled novelty

**The scientist controls how far the system explores.**

**Controlled exploration**

The graph produces multiple hypotheses within explicit scientific and computational limits.

We control exploration at two separate levels.

First, the biomarker range determines where we search from established biomarkers at level 1 to plausible candidates at level 10. For this run, we explore the full range, with a maximum of five biomarkers and one shared budget of 100 literature papers.

Second, hypothesis boldness determines how adventurous the reasoning can be within each biomarker.

This separates **where we search** from **how boldly we reason**, while keeping breadth, cost, and branching explicit.

The audit standard never changes. Every hypothesis retains its graph path, evidence, objection, citations, and verification status.


**The dial expands the search. It does not relax the evidence.**

## 4. Parallel evaluation

**We do not select a winner before testing the alternatives.**

Every hypothesis enters the evaluation gauntlet in parallel:

- Mechanism of action
- Preclinical and clinical evidence
- Small-molecule tractability
- Economic and access feasibility
- Clinical-trial recruitability

Paperclip supplies real molecular precedent. Proto provides computational tractability tools.

Their results can disagree and we expose that disagreement instead of hiding it inside one score.

The economic station identifies missing evidence instead of inventing it.

The recruitment station uses real ClinicalTrials.gov precedent to estimate whether a trial can enroll, how long it may take, and what constraint causes failure.

All results return to a shared comparison layer, revealing which hypothesis survives—and why the others fail.

## 5. Why it matters

We generate multiple grounded hypotheses, stress-test them simultaneously, and let the evidence determine the next experiment.

That gives scientists controlled exploration, built-in opposition, and a reproducible decision trail.


## 6. Winning conditions

**Closing the loop.**

The system can request a graph expansion, link resolution, or gap test. The recruitment station can find the smallest biomarker relaxation that rescues enrollment or prove that none works.

New evidence triggers another parallel evaluation round.

**Inspectability.**

Every conclusion resolves to verified quotes, graph relationships, evidence, objections, verification gates, tool calls, and execution history.

Judges do not have to trust the answer. They can reconstruct it.

**External validation.**

Our recruitment forecaster is tested against real completed trials.

Using only evidence available in 2018, it gave dupilumab in eosinophilic esophagitis a green light four years before approval in that indication.

Every prediction remains explicitly labeled as simulated.

**Meaningful sponsor use.**

Paperclip is load-bearing in literature retrieval, knowledge-graph construction, and molecular precedent.

Proto is load-bearing in computational tractability.

Their outputs directly change how hypotheses are evaluated.

**End-to-end completion.**

Clinical indication → verified graph → multiple hypotheses → parallel evaluations → prioritized hypothesis → testable next experiment.
