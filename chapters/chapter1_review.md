# Critical academic review: artifact-category Chapter 1

**Status: PROVISIONAL, not submission-ready.** This is a local critical review of the author’s proposal, not an independent external peer review.

## Quality gates

| Gate | Status | Review |
|---|---|---|
| Research originality | **Unresolved** | Palmisciano (2026) already reports wearable low-density three-class classification with leave-one-subject-out; local-global paper uses TUAR multi-class labels. Current narrow contribution is comparative benchmarking only. Supervisor must confirm capstone originality threshold. |
| Research question | **Conditionally testable** | Paired classifier comparison on fixed TUAR labels is testable if access, labels, participant IDs and overlap semantics support subject-disjoint splits. |
| Data suitability | **Partial** | TUAR is clinical, not wearable; no generalization claim can be made. Corpus-level metadata and class balance are uninspected. |
| Method validity | **Planned, not executed** | Group by participant and recording; disallow overlapping windows across partitions; fit transforms on training data only. Need lock model size, window duration, channel mapping, tuning protocol, runtime hardware/software and uncertainty estimator after corpus audit. |
| Prototype feasibility | **Blocked** | No complete safe and compatible EEG system verified below US$300 delivered. Offline replay does not satisfy live acquisition. |
| Ethics/data access | **Unresolved** | TUAR access/data-use terms and UZ review/exemption pathway require confirmation. Any live study needs prior approval and safety review. |
| Template | **Met structurally** | Sections 1.1–1.12 included; required 1.7 subsections present; 1.4 ends with a separate standalone problem statement. |
| Citation support | **Partial** | Core comparisons are tied to primary/publisher sources to stated depth; Zhang and Palmisciano details remain abstract/index level for some methods. The local-global bibliographic author record needs a final check; Grosselin is not independently retrieved. |

## Priority actions

1. Confirm whether the benchmark itself counts as original engineering research. If new algorithm or live wearable validation is required, the current gap fails that gate.
2. Request TUAR access and inspect the actual annotation files, labels, subjects, channels, overlap and access terms before freezing the protocol.
3. Obtain a complete documented device/access plan with landed Zimbabwe costs and institutional safety approval, or formally agree a scope/resource change.
4. Complete bibliographic verification for Grosselin; inspect full methods for Palmisciano and Zhang before strong protocol comparisons.
5. Add exact runtime platform, channel mapping, window length, hyperparameter protocol, per-class uncertainty and split design after dataset audit. Do not report any planned metric as a result.

## Checks and limitations

The local unslop script and citation/reference syntax checks should be run if their documented inputs can be supplied. The literature-review skill's search workflow is targeted here, not a full multi-database systematic review; the mandatory schematic-generation recommendation is out of scope because no figures are requested and no figure asset or networked schematic should be introduced without a need. Consensus was quota-limited and Zotero local access unavailable in the prior workspace audit. No dataset downloaded, model trained, live recording performed, safety test run, Zimbabwe import quote obtained, or institutional policy verified.
