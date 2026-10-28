# Chapter 1: Introduction

**PROVISIONAL — artifact-category task, dataset access, originality, prototype feasibility, and approvals require supervisor confirmation.**

**Provisional title:** Subject-Disjoint Benchmarking of Lightweight EEG Artifact-Category Identification for BCI Signal-Quality Triage

**Student:** [Name and registration number]  
**Programme:** [Degree programme]  
**Supervisor:** [Name]  
**Date:** [Date]

## 1.1 Introduction

Electroencephalography (EEG) records voltage differences at the scalp and is used by non-invasive brain–computer interfaces (BCIs) to estimate user intent. EEG amplitudes are small, and recordings also contain physiological and instrumental activity. In a wearable system, electrode contact, reduced channel coverage and movement complicate signal interpretation. A signal-processing system that identifies the kind of contamination could support quality monitoring or route windows for later handling; it does not, by itself, remove artifacts or demonstrate better BCI commands [1, 2].

Artifact management is often described as detection, category identification, rejection, or correction. These tasks answer different questions. This proposal focuses on assigning one of a defined set of artifact labels to an EEG window using existing annotated recordings. It evaluates the engineering trade-off between classification performance and computational cost. **The proposed evidence is clinical/public-data benchmarking, not validation on wearable hardware.** The live prototype requirement remains blocked pending access to an approved complete EEG system within the total US$300 budget.

## 1.2 Brief background information about the project

EEG acquisition requires electrodes, differential amplification, reference and ground arrangements, analog-to-digital conversion, and a stream that exposes raw time-series data. A wearable device may use dry electrodes and fewer channels than a clinical cap. This changes signal quality and the spatial information available to an algorithm. A model trained on full clinical montages cannot be called wearable-validated merely by selecting a few channels in software [1].

Artifacts include ocular activity (eye movement and blinks), muscle activity (including chewing), body movement, electrode disturbances, and power-line interference. Sources can overlap in time. A detector labels a window as contaminated or clean; a category identifier distinguishes the contamination class; source identification makes a more specific attribution. Rejection excludes a window, while correction estimates a less-contaminated signal. A classification score does not establish successful rejection or preservation of neural information. Downstream BCI benefit requires a separate task-level evaluation [1, 3].

## 1.3 Literature review to focus on gap analysis

Arpaia et al.'s systematic review searched six databases through 24 April 2025 and included 58 studies. Under its coding criteria, only two studies attempted artifact-category or source identification. Inoue et al. (2019) used frequency analysis and described distinguishing ocular, muscular and movement artifacts, but the review notes unclear methodological detail and limited evidence for discrimination. Zhang et al. (published in 2022; DOI contains 2021) proposed a single-channel, staged, category-aware pipeline for ocular, muscle and power-line artifacts, linked to targeted removal. The review also describes Grosselin et al. (2019) as distinguishing clean, broadly ocular/movement-contaminated, and masseter/temporalis muscle signals. These papers already rule out “first multi-artifact identification” as a defensible claim [1, 4–6].

Work published after that review narrows the apparent gap further. Palmisciano et al. (2026) evaluated a low-density dry-electrode eyewear pipeline on 29 subjects using leave-one-subject-out testing. It combines artifact detection, a convolutional-recurrent three-class discriminator (blinks, horizontal eye movements, facial movements), and correction. The abstract reports balanced accuracy 0.84 and median macro-F1 0.83 for artifact classification; this directly defeats novelty claims for a generic wearable multi-class classifier or gated category-management pipeline. Full methods are available through the publisher, but a source-code or independent replication check was not performed [7].

A separate 2026 local-global time/time-frequency network uses TUAR and a private temporal-lobe epilepsy dataset. Its task includes five TUAR artifact labels and six labels in the private data, including seizure-associated blink and rhythmic-chewing labels. It reports a random 80:20 split with five-fold cross-validation; although the paper also tests on a separate private dataset, the within-public-dataset split does not establish subject-disjoint generalization. Its network and its label distinctions already cover broad multi-class classification and feature-fusion novelty [8]. Zhang et al.'s single-channel work additionally combines detection with category-specific removal, so those contributions are also established [5].

TUAR offers annotations for eye movement, chewing, shivering, electrode-pop/static/lead artifact, and muscle artifact. Access requires an application, registration, SSH keys and rsync. It is a clinical corpus rather than wearable EEG; channel labels and montage must be resolved for each recording, and access terms, usable subject IDs, label overlap and class distributions must be checked after approval [9]. The 2026 local-global paper reports using 310 TUAR recordings (99.98 hours), bipolar re-referencing, and extracted artifact windows; this is useful evidence about a possible dataset protocol, not independent confirmation of its data splits [8].

The remaining undergraduate-scale contribution is therefore **not a novel classifier or a wearable-generalization claim**. A narrowly framed engineering benchmark could compare a compact conventional classifier and a small neural baseline for the fixed TUAR label set under the same subject-disjoint splits, reporting macro-F1/balanced accuracy alongside model size, inference latency and memory. Whether this is sufficiently original for the DCE capstone is unresolved: the closest papers do not establish that this exact paired performance/compute protocol is absent, but the task is a comparative evaluation and not a new algorithm. It also lacks real wearable validation and downstream BCI evaluation. If the supervisor requires algorithmic novelty or a live wearable contribution, this gap is not yet defensible.

Search record, 29 October 2026: targeted queries included “wearable EEG artifact category identification Inoue Zhang Arpaia”, “gated artifact management pipeline low-density eyewear EEG Palmisciano”, “TUAR EEG artifact corpus access annotations”, and the exact DOI/title for the 2026 local-global paper. Sources: PMC full text, publisher full text, PubMed record, official TUH documentation, and publisher record for Zhang. Arpaia, Zhang and the local-global paper were reviewed in full text; Palmisciano’s abstract and accessible publisher metadata/method sections were inspected, but no independent reproduction or code audit was done; TUAR claims use official corpus documentation. This was targeted citation chaining, not an exhaustive search through 29 October 2026.

## 1.4 Problem Definition

Artifact labels can help a BCI signal-quality layer decide which windows require attention, but methods report different tasks, datasets, references, metrics and recording populations. Reported accuracy values cannot be ranked directly across studies. Existing work already establishes category-aware and low-density wearable identification, along with larger neural multi-class models on clinical EEG [1, 5, 7, 8]. The unresolved engineering question is narrower: under participant-disjoint evaluation of TUAR’s fixed categories, does a compact classical model provide a useful performance-versus-compute trade-off against a compact neural baseline? Any result would apply to the selected clinical corpus and label mapping, not to wearable devices or downstream BCI performance. Dataset access and DCE acceptance of a benchmark-only contribution are unconfirmed.

The research problem is the lack of a controlled, subject-disjoint comparison of artifact-category classification performance and computational cost for compact baseline models on the selected annotated EEG corpus.

## 1.5 Aims and Objectives

**Aim:** To implement and evaluate a reproducible, computationally bounded artifact-category classification benchmark for TUAR EEG as a candidate signal-quality component for non-invasive BCI engineering.

**Research question:** On TUAR recordings, how do a compact feature-based classifier and a compact neural classifier compare in subject-disjoint macro-F1 and balanced accuracy, model size, and per-window inference latency for the five documented artifact categories?

**Objectives:**

1. Within the first project phase, document TUAR access, participant/recording identifiers, annotations, channel montage, overlapping-label handling, class counts and usable duration; freeze a label and inclusion protocol before training.
2. Implement a feature-based classifier and a compact 1-D CNN using identical non-overlapping windows and the same prespecified, channel-compatible input, with all scaling and model selection fitted inside training folds.
3. Evaluate both methods with subject-disjoint outer splits, no recording or adjacent-window overlap across partitions, and training-only validation; report per-class precision/recall, macro-F1, balanced accuracy, confusion matrices and bootstrap subject-level uncertainty where the number of held-out subjects permits.
4. Measure model parameter/file size and warm/cold per-window CPU inference latency on one specified computer, then document whether a safe, complete and approved live acquisition system can be obtained within US$300; do not represent offline replay as a live EEG prototype.

## 1.6 Methods and Instruments

This design science project will build a software signal-quality classification artifact and test it on annotated EEG. It will not train until access and the label protocol are confirmed. Primary data: TUAR v3.0.1, requested from the official NEDC process. The five labels are EYEM, CHEW, SHIV, ELPP and MUSC. The official documentation describes it as a subset of clinical TUEG. Extract label intervals from official annotation files; because simultaneous labels and clean segments may occur, inspect annotation semantics before choosing mutually exclusive classification. If overlap exists, define a multi-label task or exclude ambiguous windows by a documented rule; do not silently force a single label. Include a clean/no-artifact class only if the annotations define it sufficiently for the intended task. [8, 9]

Pre-register a common input channel set only after inspecting TUAR electrode documentation and the 2026 study’s used bipolar derivations. Do not call channel subsetting hardware emulation. Use fixed, non-overlapping windows; report duration as a parameter selected from annotation coverage and classification latency needs. Baselines: feature-based Random Forest or regularized linear classifier; compact 1-D CNN. The question is a paired engineering benchmark, not an architecture novelty claim. All normalization, feature selection, class weighting and tuning must use training data only. Split by participant, and group whole recordings within participant; keep test labels untouched. If identities or annotations do not permit this, report the benchmark as infeasible rather than split random windows.

Metrics: macro-F1, balanced accuracy, classwise precision/recall, confusion matrix and subject-level uncertainty; compute metrics over the same held-out windows. Report parameter count/file size and inference latency under fixed hardware/software conditions. Report any rejection or correction separately only if implemented and validated against an appropriate reference. The prototype is a software replay tool that streams stored windows through the classifier and displays class/latency; it is not a physical EEG acquisition prototype. A live signal route is conditional on a complete approved device, institutional safety review and procurement within budget.

## 1.7 Expected results and Significance of the project

### 1.7.1 Expected results

Expected outputs are a documented TUAR label pipeline, two reproducible baseline implementations, a subject-disjoint evaluation, compute measurements and a software replay demonstrator. No accuracy advantage is predicted. The experiment may show a performance/compute trade-off, no useful difference, or dataset and label limitations that prevent a reliable comparison.

### 1.7.2 Significance of the project

A controlled benchmark can clarify the limits of compact artifact-category models on an annotated clinical EEG corpus and provide a reproducible starting point for BCI signal-quality triage research. It will not establish wearable generalization, safer BCI decisions, clinical utility, artifact correction, or improved command decoding. Those require separate acquisition-domain and downstream evaluations.

## 1.8 Feasibility study

Software processing and a small CPU classifier are technically plausible with the available research environment; TUAR access is conditional on the formal request process and data handling terms. The 2026 comparator used a single RTX 3090 for its larger model, which this project need not reproduce; benchmark-sized baselines still require measured execution before feasibility is asserted [8].

**Physical prototype gate: BLOCKED.** No complete, safe, compatible EEG acquisition system with electrodes, accessories, shipping and Zimbabwe import costs has been verified at or below US$300. The prior checked OpenBCI board-only and accessory estimates exceeded the ceiling before freight/import. No equipment loan or lab access is confirmed. A stored-data replay application is not a substitute for the required physical prototype. Supervisor must decide whether to approve equipment access/additional funding or change the requirement/scope. No human recording with uncertified or unapproved electronics is an acceptable workaround.

## 1.9 Ethics Consideration

No human recording is planned for the initial public-data benchmark. TUAR is clinical data; comply with its access/data-use conditions, avoid re-identification, store files securely, and do not redistribute restricted data. Confirm whether institutional ethics review or an exemption determination is required before access or analysis. Any later live recording requires prior institutional approval, informed consent, an approved protocol, and a documented safety assessment of the complete acquisition device. Approval is not yet established.

## 1.10 Delimitations and Limitations of the research

The planned task is window-level identification among five TUAR artifact categories, subject to annotation compatibility. It excludes artifact source attribution beyond these labels, removal/correction, online deployment, clinical diagnosis, and proof of downstream BCI improvement. The study is limited by clinical acquisition conditions, possible class imbalance/overlapping labels, corpus access and montage heterogeneity. Subject-disjoint results on TUAR do not validate wearable, dry-electrode, low-channel or cross-device performance. No physical acquisition is claimed while the budget gate is blocked.

## 1.11 Budget and Timelines

### Provisional budget

| Item | Estimate/status |
|---|---:|
| EEG amplifier/device | No complete suitable system verified within cap |
| Electrodes, reference/ground, leads, mounting and consumables | Unquoted; must be included in delivered system quote |
| Shipping to Zimbabwe and customs/import costs | Unquoted |
| **Hardware total** | **US$100–300 cap; feasibility blocked until complete quote/access is confirmed** |
| Software and CPU evaluation | Use existing computer/software where available; ownership/specification to confirm |

Do not purchase or record until exact compatibility, safety documentation, total landed cost and supervisor approval are documented.

### Provisional two-semester timeline

| Period | Activity and gate |
|---|---|
| Semester 1, months 1–2 | Supervisor confirms gap, benchmark scope, ethics/data-use route; submit TUAR access request. |
| Semester 1, months 2–3 | Audit labels, participant IDs, channels, overlap and class counts; freeze protocol or stop if unsupported. |
| Semester 1, months 3–4 | Implement training-only preprocessing and compact baselines; check grouped splits. |
| Semester 2, months 1–2 | Complete subject-disjoint evaluation, uncertainty and compute measurement. |
| Semester 2, months 2–3 | Build offline replay demonstrator; resolve live hardware gate with supervisor. |
| Semester 2, months 3–4 | Write results, limitations and final dissertation; demonstrate only the artifact actually implemented. |

Dates, application lead times and assessment milestones require supervisor confirmation.

## 1.12 Conclusion

The proposed migration responds to a real signal-quality problem, but the broad novelty claim has been overtaken by wearable category-classification work published in 2026. A narrow subject-disjoint performance/compute benchmark on TUAR may be testable, but it is a modest comparative contribution, clinical-data-only and subject to access and DCE approval. The required live EEG prototype remains blocked under the verified budget evidence; no live or wearable validation is promised.

## References

*Provisional IEEE-style references. Publisher or dataset documentation was reviewed to the extent recorded below; university style requirements and complete claim-level checks remain pending.*

[1] P. Arpaia et al., “A Systematic Review of Techniques for Artifact Detection and Artifact Category Identification in Electroencephalography from Wearable Devices,” *Sensors*, vol. 25, no. 18, art. 5770, 2025, doi: [10.3390/s25185770](https://doi.org/10.3390/s25185770). Full text reviewed.

[2] J. W. Britton et al., *Electroencephalography: An Introductory Text and Atlas of Normal and Abnormal Findings in Adults, Children, and Infants*, American Epilepsy Society, 2016, Appendix 4. [Online](https://www.ncbi.nlm.nih.gov/books/NBK390358/). Chapter section reviewed.

[3] Y. van Stigt et al., “The effect of artifact rejection on the performance of a convolutional neural network based algorithm for binary EEG data classification,” *Biomedical Signal Processing and Control*, vol. 85, art. 105032, 2023. doi: [10.1016/j.bspc.2023.105032](https://doi.org/10.1016/j.bspc.2023.105032). Metadata/abstract only in this pass.

[4] R. Goto et al., “Recording and Characterization of EEGs by Using Wearable EEG Device,” in *2019 19th International Conference on Control, Automation and Systems*, pp. 194–197, 2019, doi: [10.23919/ICCAS47443.2019.8971564](https://doi.org/10.23919/ICCAS47443.2019.8971564). Abstract/record reviewed; classification task differs from the proposed fixed corpus benchmark.

[5] C. Zhang et al., “Automatic Removal of Multiple Artifacts for Single-Channel Electroencephalography,” *Journal of Shanghai Jiao Tong University (Science)*, vol. 27, no. 4, pp. 437–451, 2022, doi: [10.1007/s12204-021-2374-5](https://doi.org/10.1007/s12204-021-2374-5). Publisher abstract/full bibliographic record reviewed; accessible full methods were not inspected.

[6] M. Grosselin et al., “Automatic EEG signal cleaning based on classification of signal quality: a preliminary study,” *Journal of Neural Engineering*, vol. 16, no. 3, 2019. DOI/reference details to verify from Arpaia et al. before final citation. Cited in [1]; not independently retrieved in this pass.

[7] A. C. Palmisciano et al., “A gated artifact management pipeline for low-density eyewear EEG,” *Physiological Measurement*, vol. 47, no. 9, 2026, doi: [10.1088/1361-6579/ae99ab](https://doi.org/10.1088/1361-6579/ae99ab). PubMed abstract and publisher-indexed evidence reviewed; study reports 29 participants, leave-one-subject-out and three artifact classes; source/code not independently audited.

[8] Q. Yu, C. Lin, W. Wang, Z. Feng et al., “Automatic EEG artifact detection using a local-global feature fusion network in time and time-frequency domains,” *Acta Epileptologica*, vol. 8, art. 7, 2026, doi: [10.1186/s42494-026-00248-4](https://doi.org/10.1186/s42494-026-00248-4). Full publisher text reviewed; author list is abbreviated here.

[9] Neural Engineering Data Consortium, “Temple University EEG Corpus: TUH EEG Artifact Corpus (TUAR) documentation,” version 3.0.1, accessed 29 Oct. 2026. [Official documentation](https://isip.piconepress.com/projects/nedc/html/tuh_eeg/). Access procedure, corpus description and five artifact labels reviewed; license and per-record overlap/class balance not settled by the landing page.
