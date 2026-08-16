# Judging Winning Conditions



## Product in one sentence

Given a clinical indication such as rheumatoid arthritis, the system builds a verified literature knowledge graph, generates multiple hypotheses within controlled exploration limits, evaluates the hypothesis space across scientific and real-world constraints, and produces a traceable next action.

## Core challenge requirement: an end-to-end co-scientist

### What it means

The system must perform a defined scientific or drug-development workflow from beginning to end. It should gather evidence, use relevant tools and databases, generate and test hypotheses, produce structured output, and expose how it reached its conclusions.

### How we satisfy it

Our workflow connects five specialist modules through a strict orchestrator:

1. **Evidence mapping:** Paperclip literature → verified findings → knowledge graph
2. **Hypothesis generation:** graph traversal → multiple competing hypotheses
3. **Recruitability:** ClinicalTrials.gov precedent → modeled enrollment feasibility and counterfactuals
4. **Economics:** structured program evidence → access, affordability, and screening-grade ROI
5. **Molecular tractability:** Paperclip precedent + Proto computation → small-molecule tractability dossier

The hypotheses fan out across scientific evaluation dimensions. The orchestrator executes dependent module boundaries in a controlled order, validates every input and output, and preserves each module's native qualifiers.

### Proof to make visible

- Rheumatoid arthritis as the clinical indication
- Verified literature findings entering the knowledge graph
- Multiple hypotheses generated from that graph
- Evaluation results for each scientific and practical dimension
- A structured prioritized result and next action
- The orchestrator manifest showing what actually executed

---

## 1. Closing the loop

### What the judges mean

The agent must do more than produce a static analysis. It should analyze new information, propose the next experiment or evidence-gathering action, and change that proposal when the result changes.

### How we satisfy it

- Every hypothesis identifies its weakest point and can issue an exact request back to the evidence layer:

  - `expand_node`
  - `resolve_link`
  - `test_gap`

- The recruitment forecaster does not simply label a trial infeasible. It searches for the smallest biomarker-prevalence relaxation that reaches a feasible enrollment window.
- If no relaxation works, it reports the binding constraint rather than inventing a solution.
- Recruitment executes before economics, allowing modeled enrollment delay to change launch timing and ROI.
- New evidence can be incorporated into the graph and used to reevaluate the hypothesis space.

### Strongest proof

Show the same rheumatoid-arthritis thesis under two materially different results or assumptions:

1. The initial evidence produces one next action.
2. A changed result, disputed link, or recruitment constraint is introduced.
3. The proposed evidence request, trial design, or downstream economic result changes.

### Winning statement

> A failed evaluation is not the end of the workflow. It becomes the next scientific action.

---

## 2. Inspectability

### What the judges mean

A reviewer must be able to reconstruct why the system reached its conclusion. A polished answer without traceable evidence is not inspectable.

### How we satisfy it

#### Evidence-level inspectability

- Every accepted literature finding contains a verbatim quote verified against a Paperclip document.
- Findings, papers, entities, links, gaps, and disagreements have stable identifiers.
- Disagreement is explained only when the evidence supports an explanation; otherwise the system abstains.
- Nothing is silently removed because it received a low score.

#### Hypothesis-level inspectability

- Every hypothesis retains its graph path, supporting evidence, objection, citations, and verification status.
- Support, novelty, risk, and testability remain separate rather than being hidden inside one score.
- Verification proceeds through explicit gates: structure, citations, consistency, independence, falsifiability, and adversarial review.
- If a gate halts, later gates are labeled `SKIPPED`, never misrepresented as passes.

#### Evaluation-level inspectability

- Molecular precedent and computed tractability remain separate axes and are allowed to disagree.
- Economic outputs distinguish model output, reality anchors, configuration checks, and falsification controls.
- Recruitability outputs name the ClinicalTrials.gov records and assumptions behind the modeled result.

#### System-level inspectability

The orchestrator keeps these facts separate for every stage:

- Stage status
- Actual execution status
- Live, cached, fallback, or not-run origin
- Observed, inferred, or modeled basis
- Runtime maturity
- Warnings and qualifiers

It also records immutable setup data, artifact hashes, a revisioned `manifest.json`, and an append-only event log.

### Strongest proof

Open one hypothesis and trace it backward to its graph path and verified quote, then trace it forward through an evaluation result and the orchestrator manifest.

Also show one result with a warning, fallback, disagreement, or abstention. Honest failure labeling is part of the product.

### Winning statement

> Judges do not have to trust our final answer. They can reconstruct both the science and the execution that produced it.

---

## 3. Validation

### What the judges mean

The system's correctness must be tested against something outside its own reasoning. Model confidence and self-evaluation are not validation.

### How we satisfy it

#### Strongest scientific validation: recruitment forecasting

- Predictions are backtested against completed clinical trials.
- Retrospective runs use evidence horizons to reduce leakage.
- In a run limited to evidence available on `2018-01-01`, the system scored dupilumab in eosinophilic esophagitis as fully recruitable; approval in that indication followed in 2022.
- Real terminated trials cite recruitment failures matching the modeled failure mode.
- The engine has rejected a proposed model improvement when fresh backtest data showed that it harmed performance in another disease.

#### Evidence and execution validation

- Every literature quote is string-verified against retrieved source text.
- Deterministic graph assembly has reproducibility self-tests.
- JSON schemas validate every module boundary in both directions.
- The orchestrator applies semantic validation in addition to schema validation.
- Artifact hashes prevent modified outputs from being rendered as authentic run results.

#### Honest limitations

- Recruitability remains a simulation, not probability of approval.
- The hypothesis generator does not yet have retrospective scientific validation.
- ROI reality anchors are plausibility checks, not calibration or prospective validation.
- Synthetic economic fixtures remain `NOT_DECISION_GRADE`.
- Deterministic replay proves consistency, not empirical correctness.

### Strongest proof

Present the recruitment hindcast and predicted-versus-actual backtest, then explicitly separate scientific validation from schema checks, reproducibility, and interpretability.

### Winning statement

> We validate externally where external outcomes exist, and we label every other form of evidence for exactly what it proves—and what it does not.

---

## 4. Creative and meaningful use of sponsor tools

### What the judges mean

Sponsor technology must perform a load-bearing function in the scientific workflow. A logo, unused dependency, or environment variable is not an integration.

### Paperclip

Paperclip is used directly in two specialist modules:

1. **Research Evidence Mapper**
   - The only source of scientific papers
   - Supplies every paper, finding, verified quote, UniProt accession, and figure-caption finding in the graph
   - No fallback corpus is used; if Paperclip is unavailable, the stage fails visibly

2. **Small-Molecule Tractability Review**
   - Supplies drugs, bioactivities, structures, family precedent, terminated-program evidence, and modality information
   - Its retrieved precedent forms one complete axis of the tractability dossier

Without Paperclip, the knowledge graph cannot be built and the molecular-precedent axis is empty.

### Proto

Proto is used directly in the molecular tractability module:

- Foldseek structural-neighbor search
- ESMFold predicted-structure fallback
- Boltz-2 structure and affinity tools
- BioEmu computational tooling

Proto supplies computed structural evidence. It is deliberately kept separate from Paperclip's retrieved precedent so agreement and conflict remain visible.

### Orchestrator contribution

The orchestrator does not invoke Paperclip or Proto itself. It transports their provenance and module-native warnings without rewriting, averaging, or falsely attributing them.

### Tamarind and Benchling

No verified integration is present. Do not claim either sponsor unless a real call site and workflow contribution are added.

### Strongest proof

- Show a verified Paperclip quote entering the graph.
- Show Paperclip-derived molecular precedent.
- Show a Proto-derived structural result.
- Show their provenance preserved in the final manifest or inspector.

### Winning statement

> Paperclip grounds what is known. Proto computes what structure suggests. We preserve both—and preserve their disagreement.

---

## 5. Differentiation: controlled scientific exploration

### What it means

The system should explore genuinely new hypotheses without becoming an unbounded idea generator.

### How we satisfy it

Exploration is controlled at two distinct levels:

1. **Biomarker exploration range:** level 1, established, through level 10, untested but plausible
2. **Hypothesis boldness:** a separate scale controlling how adventurous the reasoning may be within each biomarker

For the current rheumatoid-arthritis setup:

- Biomarker range: 1 through 10
- Maximum biomarkers: 5
- Shared literature cap: 100 papers
- Hypothesis boldness: 1 through 6
- Maximum hypotheses per biomarker: 5

This separates **where the system searches** from **how boldly it reasons**, while making breadth, branching, and computational cost explicit.

### Strongest proof

Compare outputs from narrower and broader biomarker or boldness settings while showing that the evidence, objection, citation, and verification requirements remain unchanged.

### Winning statement

> We expand the search space without relaxing the audit standard.

---

## Cross-cutting winning condition: the system cannot misrepresent a run

The orchestrator is the only component allowed to say what actually executed.

It:

- Pins every module to an exact commit and schema pair
- Refuses to start if a checkout has drifted
- Validates live and fallback artifacts
- Preserves invalid live output instead of promoting it
- Labels cached and fallback results explicitly
- Abstains when no honest input exists
- Prevents custom programs from borrowing the rheumatoid-arthritis golden-profile cache
- Refuses to render artifacts whose hashes have changed

This is a major inspectability advantage: a readable interface cannot silently imply that every stage ran live or that every output is decision-grade.

## Final judge checklist

- [ ] The clinical indication is rheumatoid arthritis.
- [ ] Multiple hypotheses are visibly generated.
- [ ] Exploration controls and limits are explained.
- [ ] Every shown hypothesis has evidence, an objection, and provenance.
- [ ] Scientific evaluation dimensions are clearly separated.
- [ ] A changed result produces a changed next action.
- [ ] The recruitment backtest or hindcast is shown.
- [ ] Paperclip and Proto each perform a visible, load-bearing operation.
- [ ] No Tamarind or Benchling integration is claimed without evidence.
- [ ] Simulations are labeled as simulations.
- [ ] Economic synthetic outputs are labeled `NOT_DECISION_GRADE`.
- [ ] The orchestrator manifest is shown alongside the interface.
- [ ] Live, cached, fallback, failed, and skipped states are not visually conflated.
- [ ] The final output contains a prioritized hypothesis and a concrete next step.

## Final positioning

> We turn a rheumatoid-arthritis question into verified evidence, multiple controlled hypotheses, multi-dimensional evaluation, and a traceable next action—while preserving exactly what the system knows, what it inferred, what it modeled, and what actually ran.
