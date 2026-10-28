# Critical academic review of Chapter 1

**Assessment: PROVISIONAL — not ready for submission or execution.** This is an author-requested local critique, not an independent peer review. The author and supervisor remain responsible for the proposal and source checks. The peer-review skill's journal-review intake is designed for a confidential externally assigned review; there is no such assignment here. Its local critical-review principles have been applied without representing this as an editorial decision.

## Quality gates

| Gate | Status | Evidence and required action |
|---|---|---|
| Research gap | **Unresolved** | Calibration-free online MI and rejection methods exist; Rao et al. (2026) is an especially close competitor. Complete full-text comparison and citation chaining before claiming originality. |
| Alignment | **Provisionally met** | Title, problem, question and objectives address MI calibration and command reliability; review whether the two-class demonstrator meets DCE expectations. |
| Experimental validity | **Partial** | Held-out user/session, threshold validation and baselines are specified. Event-matching, chronological target splits, target validation allocation, minimum sample availability and confidence intervals require a detailed preregistered protocol. Offline rest is constrained. |
| Physical prototype | **Blocked** | No suitable owned device is verified within USD 300 delivered; vendor prices exceed the ceiling before accessories. Establish safe compatible equipment and a delivered quote, or formally reassess requirements. |
| Citation integrity | **Partial** | 13 cited scientific publications have title, first author, year and identifier matched using publisher or PubMed records. Several claims rely on abstracts, and full claim-by-claim verification, correction/retraction checks, and most index entries remain outstanding. The local verifier could not reach external APIs. |
| Ethics | **Unresolved** | No institutional pathway, application, approval, approved safety procedure or participant protocol has been verified. |

## Template compliance

- [x] Sections 1.1–1.12 present in the same order as the supplied DCE template; optional 1.10 included.
- [x] Sections 1.7.1 and 1.7.2 included; 1.4 ends with a separate, uncited sentence stating the problem.
- [x] Aim, research question, four measurable objectives, methods, technical/operational/economic feasibility, ethics, budget and relative two-semester timeline included.
- [ ] Student, registration, programme, supervisor, date, institutional citation style and calendar milestones need confirmation.
- [ ] Originality, an affordable live system, ethics and safety approvals are not demonstrated. The listed budget is an infeasible benchmark, not a viable purchase plan.

## Priority findings and actions

1. **Critical — equipment and safety (1.6, 1.8, 1.11).** Ganglion board plus dongle and the minimum advertised electrode price already total USD 689.97; essential components, shipping and import fees remain unquoted. A listing does not demonstrate electrical safety or that a particular accessory set works. Obtain a complete destination-specific quote and documented supervisor/institutional safety assessment. If no device fits, agree a revised scope or resources; do not claim a simulated or offline interface meets the live requirement.
2. **Critical — originality (1.3–1.5).** The chapter offers an empirical comparison rather than a proven new algorithm. Rao's full study and the nearest comparison methods may already evaluate overlapping calibration and decision conditions. Read their full methods and compare data partitions, target information, thresholds, acquisition and outcomes; narrow the contribution or change direction if no defensible distinction remains.
3. **Major — incomplete literature audit (matrix).** Eight of the 40 workspace-index references are covered by the reviewed matrix; 32 remain unverified. Thirteen scientific publications are cited in the draft, below the requested aspirational 20–30. Search and verify additional recent competing studies and negative findings; do not add sources merely to meet a count. Search-result counts were not recorded, and a systematic review cannot be claimed.
4. **Major — reference and claim checks (throughout).** Rao, Singh, Lee 2013 and Nagel are represented using abstracts, limiting comparison of calibration and outcome definitions. The citation-verification script returned DNS failure for a known DOI, so no script-based batch verification occurred. Primary records were consulted through web access, but metadata matching is not full claim verification. Check references, corrections/retractions, quoted metrics, source sections, all claims and the final style manually or with a working verifier. The listed 2015 Lim webcam study is not the distinct 2013 Lee conference paper; confirm its metadata separately.
5. **Major — decision layer and data partitions (1.6).** Two-class maximum confidence alone is not demonstrated to detect non-control; uncalibrated LDA scores can be misleading. Define an operational control/non-control comparison, event merging, refractory period, latency reference, threshold sweep and non-control recording duration before evaluation. Ensure each calibration budget includes every target label used for training or tuning. Reserve validation data without silently increasing the stated budget; use source-only threshold selection if a target budget cannot support disjoint validation. Source and target data must use compatible reference and channels; verify per dataset. Report missing or rejected data.
6. **Major — external validity (1.3, 1.6, 1.10).** PhysioNet task-rest periods are short cued intervals; do not interpret performance on them as spontaneous real-world inactivity. SHU releases cleaned trials and is not a natural artifact challenge. Define safe live evaluation and enough non-control exposure for meaningful rates, report denominators and uncertainty, and avoid claims about disability populations without appropriate participants and approval.
7. **Major — ethics and timing (1.9, 1.11).** The UZ pathway and review duration are unverified. Confirm the responsible committee, required application, privacy requirements, safety approvals, data retention, withdrawal terms and recruitment before a pilot. Build actual deadlines and procurement lead times into the timeline.
8. **Moderate — methodological specification (1.6).** CSP with three channels and very small samples may fail or overfit; the stated log-variance fallback is an alternative comparator, not an equivalent method. Prespecify its use, preprocessing, hyperparameter grid, train/validation splits, repeated random seeds, target trial selection and analysis unit. Inspect dataset licensing, particularly SHU and BNCI CC BY-ND, before use or redistribution. Confirm source access and channel nomenclature.
9. **Moderate — evidence scope and writing (1.2–1.3).** IMUs and signal-quality checks are introduced briefly but not quantitatively compared. If these are retained as plausible alternatives, add directly relevant verified studies and compare benefit, sensor demands and limitations. The webcam and EOG evidence concerns visual paradigms and cannot establish benefits for MI. References should support every substantive claim, especially statements about practical consequences and threshold behaviour.
10. **Moderate — pilot inference and objectives (1.5–1.7).** Define sample size or precision rationale and distinguish descriptive pilot feasibility from an adequately powered user comparison. The live objective is conditional on hardware and approval; this dependency should be explicitly accepted by the supervisor.

## Supervisor confirmations

- Approve the exact title, definition of originality and whether an empirical engineering comparison meets capstone requirements.
- Resolve the live-device and USD 100–300 delivered-cost conflict; confirm available computing, laboratory support and safety oversight.
- Confirm the ethics application route, recruitment, risk assessment and research data handling.
- Confirm citation style, chapter length, university deadlines, and whether the live demonstration and small healthy-adult pilot meet assessment criteria.

## Checks performed and limits

- Extracted template text directly from the DOCX XML; no changes to source documents. Checked that all 12 section headings appear and that Section 1.4 ends with the required standalone sentence.
- Ran the local unslop linter: index 0.0 over 3,528 words; this measures wording patterns, not scientific validity.
- Attempted the local DOI verifier against 10.1371/journal.pone.0263641; DNS failed, so manual primary-record matching through the web was used instead.
- SciSpace returned paper records; its autogenerated summaries were checked against primary sources when cited. Consensus search quota was exhausted. Zotero local API access returned operation not permitted; no library contents were read or changed.
- No independent human peer review, full systematic search, dataset experiments, prototype operation, electrical safety test, university-policy confirmation, or comprehensive claim-to-source audit was performed.
