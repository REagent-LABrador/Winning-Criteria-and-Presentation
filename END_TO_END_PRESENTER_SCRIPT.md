# LABrador End-to-End Presenter Script

> **How to use this:** Read the normal text aloud. Text in `[brackets]` is an action and is not spoken. Short pauses are intentional. If the screen does not match the expected state, use the truth-label fallback lines near the end rather than improvising.

## 1. Opening: the need

[OPEN ON THE SETUP SCREEN. DO NOT CLICK YET.]

There is an urgent global need to turn biomedical knowledge into novel, testable therapies faster.

For a complex disease like rheumatoid arthritis, the problem is not a lack of research. The problem is converting a massive, fragmented scientific record into new hypotheses that are both imaginative and defensible.

Manual review is slow and naturally returns researchers to familiar targets.

Generative AI can produce more ideas, but novelty without grounding creates hypotheses that are difficult to trust, reproduce, or test.

The United States needs a faster path from biomedical research to therapeutic programs to strengthen scientific leadership, biotechnology, and health security.

Other countries need access to advanced drug-discovery reasoning without requiring enormous research teams.

And globally, we need a faster way to respond to chronic disease, rare conditions, and emerging health threats.

That is why we built LABrador.

LABrador expands the hypothesis space without lowering the scientific standard—and helps eliminate weak ideas before expensive laboratory and clinical work begins.

## 2. Configure the scientific search

[POINT TO RHEUMATOID ARTHRITIS.]

We begin with rheumatoid arthritis as the clinical indication.

[POINT TO BIOMARKER EXPLORATION RANGE.]

The first control defines where we search.

Level one represents established biomarkers. Level ten represents candidates that are untested, but still scientifically plausible.

For this run, we search the full range from one through ten, with a maximum of five biomarkers.

[POINT TO MAXIMUM LITERATURE PAPERS.]

We use one shared literature budget of up to one hundred papers.

[POINT TO HYPOTHESIS BOLDNESS.]

The second control defines how boldly we reason within each biomarker.

Here, we allow hypothesis boldness from level one through level six, with up to five hypotheses per biomarker.

This separation matters.

Biomarker range controls **where we search**. Hypothesis boldness controls **how adventurous the reasoning can be**.

Neither control relaxes the audit standard.

[START OR OPEN THE RUN.]

## 3. Build the evidence graph

[OPEN THE KNOWLEDGE-GRAPH VIEW.]

LABrador begins by building a bounded scientific world.

Paperclip retrieves the literature. It is the only source of papers for the evidence-mapping stage.

Every accepted finding must resolve to a verified quote from a real source. If the quote cannot be verified, it does not enter the graph.

[SELECT A NODE OR LINK WITH EVIDENCE.]

The system converts those findings into a knowledge graph of mechanisms, targets, relationships, disagreements, and unanswered gaps.

The model can reason over this graph, but it cannot silently introduce evidence that is not present.

[OPEN A DISAGREED LINK OR GAP, IF AVAILABLE.]

Contradictions are not averaged away. When studies disagree under different conditions, the conditions remain visible. When no explanation is supported, the system abstains.

This graph is the inspectable foundation for everything that follows.

## 4. Generate multiple hypotheses

[MOVE TO THE HYPOTHESIS VIEW.]

From the graph, LABrador generates multiple competing hypotheses.

We do not ask one model for one answer and then search for evidence that supports it.

Each hypothesis retains:

Its path through the graph.

Its supporting evidence.

A serious objection.

Its citations.

And its verification status.

[OPEN ONE HYPOTHESIS.]

Verification is explicit. The system checks graph structure, citations, consistency, source independence, falsifiability, and adversarial objections.

If a gate fails, later gates are marked as skipped. A skipped test is never displayed as a pass.

The result is controlled exploration: more ideas, without lowering the standard required to trust them.

## 5. Evaluate the hypothesis space

[SHOW THE EVALUATION BRANCHES OR STAGE RESULTS.]

The hypotheses now fan out across multiple evaluation dimensions.

We test mechanism and clinical evidence.

Small-molecule tractability.

Economic and access feasibility.

And clinical-trial recruitability.

These evaluations answer different questions, and their results are allowed to disagree.

### Molecular tractability

[OPEN THE TRACTABILITY RESULT.]

The tractability station keeps two evidence axes separate.

Paperclip retrieves real molecular precedent: drugs, compounds, bioactivity, structures, and terminated programs.

Proto supplies computational evidence through structural-neighbor search and specialized tractability tools.

Retrieved precedent and computed tractability are never averaged into one misleading number.

If they conflict, LABrador shows the conflict.

### Clinical recruitability

[OPEN THE RECRUITABILITY RESULT.]

The recruitment station uses real ClinicalTrials.gov precedent to estimate whether a proposed trial can enroll, how long enrollment may take, and what constraint is driving failure.

This is recruitability—not probability of approval.

Every output remains explicitly labeled as simulated.

### Economics

[OPEN THE ECONOMIC RESULT.]

The economic station separates pricing, access, affordability, cash flow, and risk-adjusted value.

If the submitted evidence is insufficient, it does not fabricate certainty. It returns the missing inputs as a work order.

When synthetic inputs are used, the result remains clearly labeled `NOT_DECISION_GRADE`.

The orchestrator runs recruitment before economics, so modeled enrollment delay can change launch timing and ROI.

## 6. Show the closed loop

[OPEN THE NEXT-ACTION OR COUNTERFACTUAL OUTPUT.]

LABrador does not end with a score.

When a hypothesis is weak, it produces a precise next action: expand a graph node, resolve a disputed link, or test an unanswered gap.

The recruitment station goes further.

If a trial design is too slow, it searches for the smallest biomarker relaxation that restores feasibility.

If no relaxation works, it names the binding constraint instead of inventing a solution.

That result becomes the next scientific input.

When the evidence or trial assumption changes, the next cycle recomputes the relevant evaluations and can produce a different next action.

A failed evaluation is not the end of the workflow.

It becomes the next experiment.

## 7. Show inspectability and execution truth

[OPEN THE MANIFEST OR STAGE INSPECTOR.]

Inspectability exists at two levels.

At the scientific level, every conclusion traces to quotes, graph paths, evidence, objections, verification gates, and tool calls.

At the system level, the orchestrator records exactly what happened.

For every stage, it keeps stage status, actual execution, output origin, result basis, runtime maturity, and warnings separate.

A result can be readable without pretending it was produced live.

A modeled result cannot silently become an observed result.

A cached or fallback artifact cannot silently become a successful execution.

The orchestrator pins module versions, validates every input and output, records artifact hashes, and refuses to render an artifact if its bytes have changed.

If no honest input exists, the stage abstains.

The system is designed not only to explain its science, but also to tell the truth about its own execution.

## 8. Explain external validation

[SHOW THE RECRUITMENT BACKTEST OR VALIDATION OUTPUT.]

Our strongest external validation comes from the recruitment forecaster.

It is backtested against completed clinical trials using predicted enrollment time versus observed results.

In a leak-controlled historical run using evidence available on January first, 2018, it gave dupilumab in eosinophilic esophagitis a full recruitability score.

Approval in that indication followed in 2022.

The model also identifies failure modes that match real registry-recorded recruitment failures.

We are careful about what this proves.

It validates enrollment forecasting—not clinical efficacy and not probability of approval.

Schema validation proves that components communicate correctly. Reproducibility proves that the same inputs produce the same outputs. Inspectability proves that reasoning can be reconstructed.

None of those are mislabeled as scientific validation.

## 9. Sponsor contribution

[SHOW PAPERCLIP AND PROTO PROVENANCE IN THE RELEVANT RESULTS.]

Paperclip and Proto are load-bearing parts of the scientific workflow.

Paperclip grounds the literature graph and supplies the retrieved-precedent axis of molecular evaluation.

Proto supplies computed structural evidence for tractability.

The orchestrator does not invoke either sponsor directly. It preserves their provenance and warnings without rewriting or averaging them.

Paperclip tells us what has been observed.

Proto helps compute what structure suggests.

LABrador preserves both—and preserves their disagreement.

## 10. Close

[RETURN TO THE OVERALL RESULT OR HYPOTHESIS COMPARISON.]

LABrador moves from a rheumatoid-arthritis question, to verified evidence, to multiple controlled hypotheses, to multi-dimensional evaluation, and finally to a prioritized, testable next action.

It closes the loop by turning weaknesses into new evidence requests or trial changes.

It is inspectable from the source quote all the way to the execution manifest.

It is externally validated where real outcomes exist, and honest where they do not.

And it uses Paperclip and Proto for load-bearing scientific work—not as logos added after the fact.

LABrador does not replace scientific judgment.

It gives scientists more defensible ideas, exposes weak paths earlier, and preserves exactly how every conclusion was produced.

More ideas.

More scrutiny.

A better next experiment.

---

# Truth-Label Fallback Lines

> Use only the line matching the screen. Never claim that every stage ran live.

## If a stage is live

> This stage completed live. The manifest records the executed module, artifact hash, and result basis.

## If a stage is cached

> This stage is using a validated cached artifact. The interface labels it as cached, and we are not presenting it as a live execution.

## If a live process failed and a fallback is displayed

> The live process failed, and the orchestrator preserved that failure. The readable result comes from a separately validated fallback and is labeled `DEMO_FALLBACK`.

## If a stage is skipped

> This stage did not have an honest compatible input, so the orchestrator abstained instead of borrowing an unrelated result.

## If economics is synthetic

> The economic pipeline completed, but these inputs are synthetic, so the result is correctly labeled `NOT_DECISION_GRADE`.

## If asked whether the stages run in parallel

> The hypothesis space fans out across independent evaluation dimensions. The orchestrator executes module boundaries in dependency order so outputs such as recruitment delay can correctly affect downstream economics.

---

# One-Line Answers if Judges Interrupt

**What is novel?**  
We separately control where we search and how boldly we reason, then evaluate multiple grounded hypotheses without relaxing the audit standard.

**How do you close the loop?**  
Weaknesses become exact evidence requests or trial-design counterfactuals, which become inputs to the next evaluation cycle.

**How is it inspectable?**  
Every conclusion traces from source quote to graph path to hypothesis to evaluation to a truth-labeled execution manifest.

**How is it validated?**  
The recruitment model is backtested against completed trials and has a leak-controlled historical hindcast; other checks are labeled as integrity or reproducibility, not scientific validation.

**Where is Paperclip used?**  
It is the sole literature source for the evidence graph and supplies the retrieved-precedent axis of molecular tractability.

**Where is Proto used?**  
It supplies computational structural evidence in the tractability module.

**Why rheumatoid arthritis?**  
It is a complex, evidence-rich disease where many plausible mechanisms compete and clinical recruitability can become a decisive constraint.

**Is recruitability probability of approval?**  
No. It is a modeled enrollment-feasibility score.

**Is the ROI result decision-grade?**  
Only with sufficient real inputs. Synthetic fixtures remain explicitly `NOT_DECISION_GRADE`.

**Did every stage run live?**  
Read the manifest. It separately records live, cached, fallback, failed, and skipped states.
