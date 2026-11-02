# Provisional engineering gap analysis

**Status: PROVISIONAL.** This is a targeted comparison, not evidence that a proposed method is globally novel. The [literature matrix](chapter1_literature_matrix.md) records primary-source access, findings, and the unverified remainder of the 40-item index.

## Candidate comparison

| Direction | Evidence and strongest competing work | Feasibility and decision |
|---|---|---|
| Unseen-user calibration efficiency | Rao et al. (2026) report online subject-independent MI with supervised updates; Xiong and Wei (2022) already investigate low-data alignment and augmentation; Singh et al. (2019) study small calibration sets. | Suitable for public data and a simple baseline. Chosen as the primary comparison; no claim of a novel algorithm or first calibration-free system. |
| Cross-session minimal recalibration | Ma et al. (2022) measure cross-session degradation and adaptation on five sessions. | Secondary evaluation on SHU; its cleaned, task-only trials do not support an idle-command conclusion. An unseen-user test and a known-user later-session test answer different questions. |
| Signal-quality-aware decoding | Schmoigl-Tonis et al. (2023) document existing online artifact methods; Cho et al. (2017) provide controlled artifacts. | Important confound, but a separate algorithm adds scope and needs suitable real-time artifact labels and baselines. Monitor quality and report exclusions; do not assert novelty or improvement. |
| Reliability-aware adaptation | Song et al. (2022) already reduce false positives in a calibrated MI setup; Nagel and Spüler (2019) and Zhou et al. (2020) study asynchronous detection in visual BCIs. | Include acceptance and rejection as outcomes, not a claim of inventing thresholding. Compare at equal operating thresholds and calibrated budgets; inactivity data are limited. |
| EEG plus gaze/EOG | Lee et al. (2013) show webcam checking in a visual speller; Zhou et al. (2020) combine SSVEP and EOG. | Existing hybrid work, added sensor demands and unequal suitability across users. No justified MI-specific incremental benefit is established here. Exclude from primary prototype. |

## Selected contribution and comparison

**Provisional title:** Calibration-Efficient Interpretation of Motor Imagery EEG Commands for an Assistive Brain–Computer Interface.

**Question:** How do the amount of labelled new-user calibration and the command acceptance threshold affect motor imagery command classification and rejection performance for previously unseen users?

The proposed contribution is an undergraduate-scale, reproducible comparison of pooled versus user-specific conventional classifiers across explicit calibration budgets, with selective rejection and a live EEG interface if equipment can be secured. It may reveal a useful empirical operating trade-off. It is not established to be a new method or a literature-wide gap. Rao's supervised online learning is especially close and may subsume aspects of the intended design; its full paper and related citations must be inspected, including non-control protocol, electrode placement, amount and timing of labelled data, and baseline details. Xiong and Wei's low-calibration comparisons likewise require a direct protocol-level comparison before describing originality.

**Contradictory evidence:** Rao's abstract reports effective online use with no offline calibration; thus claims that calibration is always necessary would be false. Cross-session adaptation can improve accuracy in Ma et al.'s benchmark; that does not prove it improves the proposed unseen-user setting. Song's low sensitivity shows that rejecting false positives need not produce a usable interface. Visual hybrid systems' good results do not demonstrate that a camera helps MI.

**Validity:** Hold out participants, sessions and blocks before any learned processing; calibrate thresholds on source validation or explicitly allocated target validation data only. Report calibration samples including those consumed by threshold tuning, distinguish labelled from unlabelled adaptation, report participant-level paired differences, and use true non-control segments for false events per minute. Dataset rest is a controlled proxy, not evidence about unconstrained inactivity. Cross-session and cross-user results must be separately reported. See Section 1.6 for the planned baselines and split.

**Feasibility:** The verified Ganglion and Cyton prices exceed the entire hardware ceiling before delivery and accessories. No safe and compatible purchase within USD 300 delivered has been established, so the mandatory live artifact cannot currently be promised. Supervisor must establish whether a suitable purchase is available within budget or whether the approved scope and resources can change. Offline experiments alone cannot satisfy the user's physical-prototype requirement.

## Remaining novelty and evidence questions

1. Review the full Rao article and closest subsequent studies for identical low-channel, unseen-user calibration and rejection comparisons, including online labelled updates and the true independent test protocol.
2. Verify the 32 index entries not checked in this pass, search additional specialist databases and citation chains, and record screening counts; this targeted search is incomplete.
3. Confirm that a fixed three-channel montage and source-trained CSP are statistically stable on each dataset; do not claim it works until evaluated.
4. Establish whether the rest periods, timing annotations and any live protocol support a meaningful false-event estimate with adequate non-control exposure. Confirm SHU data licence and access.
5. Establish a device, delivery quote, electrical safety, supervisor support and ethics route before treating live evaluation as feasible.
