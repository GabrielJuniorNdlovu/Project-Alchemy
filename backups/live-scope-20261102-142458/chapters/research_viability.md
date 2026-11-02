# Research viability: wearable EEG artifact-category identification

**Overall verdict: PROVISIONAL; physical prototype BLOCKED.** The general research direction is scientifically relevant, but broad category-classifier novelty is no longer defensible after Palmisciano et al. (2026). A narrow subject-disjoint and compute-aware benchmark on TUAR is testable conditionally, but its originality and suitability for the DCE capstone require supervisor approval.

## Research gap and contribution

Arpaia et al. (2025) found only two category/source studies in its review through 24 April 2025, including Inoue et al. and Zhang et al. That review does not cover later work. Palmisciano et al. (2026) already report a low-density dry eyewear pipeline with detection, three-category classification, correction and leave-one-subject-out evaluation (29 participants). A separate 2026 local-global classifier uses five TUAR categories and a private epilepsy cohort, although its public-data split is random 80:20 rather than subject-disjoint as reported. Zhang et al. already describe staged category-aware single-channel artifact removal.

Therefore, do not claim first artifact classifier, first wearable category identification, first three-class wearable model, or first gated pipeline. Candidate contribution: compare a compact feature-based and compact neural baseline under identical TUAR subject-disjoint splits while measuring macro-F1/balanced accuracy, model size and CPU latency. This is an engineering benchmark, not a new algorithm or wearable validation. Whether it is sufficiently original is **uncertain**; the cited closest studies do not prove the precise comparison absent.

## Data and software feasibility

TUAR v3.0.1 supplies five named artifact labels, but access is application-based and requires account registration, SSH key setup and rsync. It is clinical EEG, not a wearable dataset. Before method development, verify access terms, identities, per-record channel/montage, overlapping labels, class counts and enough subjects for grouped testing. The published local-global study shows a TUAR workflow is possible, but does not establish this project's access or leakage-safe protocol.

A two-model CPU benchmark and stored-data replay demonstrator are computationally plausible; measure runtime on the actual computer. The local-global paper used an RTX 3090 for a larger network, so avoid copying its architecture or presuming its compute footprint. Software feasibility cannot satisfy the physical-prototype condition.

## Physical prototype gate

**BLOCKED under current evidence and US$300 total cap.** No complete acquisition configuration is confirmed within US$100–300 delivered to Zimbabwe. The previous OpenBCI estimate (Ganglion board US$624.99 + required dongle US$19.99 + electrodes from US$44.99) was already US$689.97 before conductive paste, leads/mounting needs, freight, customs and import. A board-only listing is not an EEG system. For artifact-category acquisition, placement depends on the target classes: frontal/near-eye positions help ocular events, temporal/face-adjacent sites help jaw/facial EMG, while motion and electrode-contact issues need appropriate placement and possibly reference sensors. A system with only a few channels cannot be presumed to support every category. It must expose raw time-series EEG, suitable sampling and synchronized labels, and include compatible electrodes, reference/ground, mounting, acquisition interface, safety documentation and full landed cost. No uncertified or unapproved human-recording setup is an acceptable substitute.

No institutional device loan or lab access is confirmed. Supervisor decision required: authorize confirmed equipment access or additional resources, or revise the required physical-prototype scope formally. Until then, a replay tool is only a software artifact.

## Validity, ethics and timeline

Use participant-disjoint and recording-grouped splits, non-overlapping windows, and training-only learned preprocessing/tuning. The primary metrics should include macro-F1, balanced accuracy and per-class recall, plus subject-level uncertainty and measured compute. Report label-overlap policy, class balance and exclusions. A clinical-dataset result cannot be described as wearable or BCI-benefit validation.

TUAR is clinical data. Follow access terms, secure storage and non-redistribution requirements; confirm whether University of Zimbabwe review or an exemption applies. Live human collection needs prior ethics approval and equipment safety review. Two-semester software work is plausible if access is timely; live prototype feasibility is not. Budgeted delivery/import quotes and institutional access are missing.

## Decisions for supervisor

1. Is a reproducible subject-disjoint performance/compute benchmark sufficient original contribution, given Palmisciano and the 2026 TUAR study, or is a materially different research direction required?
2. Is TUAR access/data use approved, and can corpus-level label/channel/participant audit begin under the applicable ethics determination?
3. What complete, institutionally approved EEG system can be accessed for total delivered cost within US$300, or will the live physical prototype requirement/resources be formally changed?

## Evidence limits

Targeted primary-source checks through 29 October 2026; not a comprehensive novelty search. Arpaia and the 2026 local-global article full texts were inspected. Palmisciano abstract plus indexed publisher sections were reviewed; full code, independent reproduction and complete device details were not checked. Zhang publisher record/abstract was reviewed, not full methods. TUAR official access page was reviewed; the corpus data, license, class balances and annotation overlap were not inspected. No Zimbabwe shipping/import quote, local supplier, approved lab, ethics decision or safety certification was verified. Consensus quota was exhausted and Zotero local API access was denied in the earlier workspace audit; connector records are not used as claim evidence.
