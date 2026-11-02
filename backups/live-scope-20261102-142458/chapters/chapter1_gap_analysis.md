# Provisional artifact-identification gap analysis

**Status: no algorithmic or wearable-classifier novelty is established.** The only candidate retained for supervisor review is a controlled performance/compute benchmark on TUAR; whether this meets the DCE originality requirement is unresolved.

## Candidate comparison

| Candidate | Prior evidence | Data/evaluation fit | Decision |
|---|---|---|---|
| Generic multi-class artifact identification | Inoue et al. and Zhang et al. identified multiple categories; Palmisciano et al. classify three categories from low-density eyewear EEG; 2026 local-global network classifies multiple clinical artifact labels. | Labels exist in TUAR and the two newer studies, but datasets and label definitions differ. | Reject as novelty claim. Already established. |
| Gated detection → class identification → correction | Palmisciano et al. report this complete low-density eyewear pipeline and subject-disjoint testing. | Their task is closer than proposed, includes correction and real wearable data. | Reject as a proposed new pipeline. A reimplementation is not itself a gap. |
| Single-channel category-aware artifact removal | Zhang et al. (2022 issue; DOI 2021) propose staged identification and targeted suppression of ocular, muscle and line-noise artifacts. | Published method and simulated/CHB-MIT validation; not the same multiclass benchmark. | Reject as novel. Reproduction could be an engineering exercise only. |
| Larger local/global time + time-frequency classifier | 2026 local-global study uses five TUAR classes and a private epilepsy cohort; reports random 80:20 split with five-fold CV and cross-dataset test on private data. | Direct label overlap with TUAR; compute-heavy model and clinical task. | Reject architecture novelty. Its within-TUAR protocol does not report subject-disjoint validation in the reviewed methods. |
| Lightweight classifier benchmark on held-out TUAR subjects | Prior work already includes compact/efficient artifact models; Arpaia reviews inconsistent metrics, and newer models use unequal datasets/protocols. | TUAR offers five documented labels but clinical EEG, application access, montage heterogeneity and label overlap require audit. Could compare compact feature-based and compact CNN models under same split. | **Retain only as a provisional comparative engineering question.** Novelty is modest and unverified; no wearable-generalization claim. |
| Cross-dataset/device transfer | Palmisciano has an independent eyewear benchmark; the local-global article reports TUAR-to-private-clinical transfer. | Label maps, montage, acquisition and populations are not harmonized; a true wearable dataset may have incompatible labels. | Do not select until compatible, licensed datasets are found and harmonization tested. |

## Established versus unresolved

- **Established:** artifact detection, category-aware identification, single-channel multi-artifact handling, low-density wearable three-class classification, subject-disjoint evaluation in Palmisciano, and clinical multi-class artifact labeling/classification.
- **Not established:** direct comparability of published scores; benefit of artifact labels to downstream BCI; equivalence of TUAR and wearable EEG; a novel method from merely combining known classifiers; safe live hardware under the project budget.
- **Task distinctions:** identification predicts a category. Detection predicts contamination status. Rejection excludes segments. Correction estimates modified signal. Source identification makes a finer attribution. The selected benchmark tests only category prediction unless separately justified outcomes are added.

## Narrow candidate question

*On TUAR recordings, how do a compact feature-based classifier and a compact neural classifier compare in subject-disjoint macro-F1 and balanced accuracy, model size, and per-window CPU inference latency for the five documented artifact categories?*

This is testable only if access is granted, annotation overlap semantics and usable participant IDs support the split, and a common channel representation can be defined. Every window/recording from a held-out participant must remain outside training and model selection. No adjacent or overlapping windows may cross partitions. Fit transforms and thresholds using training/validation partitions only. Report subject-level uncertainty and classwise results. The 2026 local-global study's reported random 80:20/CV protocol makes a grouped evaluation a useful methodological contrast but does not prove that this exact comparison is novel.

## Originality risks and supervisor gate

1. Palmisciano et al. is a direct wearable competitor; novelty must not be claimed from Arpaia et al.'s 2025 “only two studies” finding alone because that search ended before Palmisciano's 2026 article.
2. TUAR benchmarking already appears in the local-global paper. The contribution can only be the controlled, subject-disjoint, compute-aware comparative protocol if the DCE accepts such an empirical contribution.
3. The proposed data are clinical rather than wearable. A low channel subset cannot simulate dry electrodes, motion, headgear or hardware noise.
4. If novelty must be a new classifier or wearable validation, **no defensible gap is identified** with the currently confirmed data and resources.
5. Before finalizing: verify TUAR data terms and annotation overlap; confirm DCE's interpretation of original contribution; obtain complete safe hardware/access decision if physical acquisition remains compulsory.

## Search and evidence note

Targeted searches on 29 October 2026: “wearable EEG artifact category identification Inoue Zhang Arpaia”; exact Palmisciano title/DOI; exact local-global title/DOI; TUAR official documentation. Sources: primary publisher full texts, PubMed abstract, TUH official corpus documentation. Full text reviewed: Arpaia and local-global article. Palmisciano abstract plus publisher-indexed methods/results only; Zhang publisher record/abstract. These searches were not exhaustive. Consensus quota and Zotero local API access were unavailable in the earlier workspace audit; no database-wide screening was done.
