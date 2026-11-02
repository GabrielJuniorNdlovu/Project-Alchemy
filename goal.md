# Project-Alchemy authoritative specification

Updated 2 November 2026. Status: proposed research and engineering work; no acquisition, approvals, trained models or live demonstration are established by this document. This scope supersedes the artifact-category project and replay-led/public-data plans.

## Title and vision

Risk-Aware Selective Decoding for Reliable Eight-Channel Motor-Imagery Brain–Computer Interfaces Under Distribution Shift.

Build a wearable, non-invasive eight-channel EEG BCI that acquires the researcher's own EEG, learns subject-specific motor-imagery commands, and processes incoming EEG on Raspberry Pi 4 for predefined robotic-arm and computer navigation/selection actions. Live control is the intended final deliverable. Recorded EEG replay is an intermediate integration and reproducibility tool.

## Scientific problem and primary question

Incorrect accepted commands can trigger unintended actions; rejecting nearly everything sacrifices control availability. Recording-session changes, unfamiliar imagery and simulated channel degradation are distinct challenges.

For this participant and the observed recording conditions, can a computationally efficient risk-aware selective-decoding mechanism reduce errors among accepted familiar-class commands, compared with established rejection methods at comparable acceptance rates, while limiting acceptance of unfamiliar imagery under session variability and simulated channel degradation?

## Testable hypothesis

At prespecified acceptance operating points, the proposed gate will produce a lower error proportion among accepted familiar-class predictions than the strongest development-selected rejection baseline on held-out personal sessions. Evaluate unfamiliar-class acceptance separately, without assigning an unfamiliar input a correct familiar label. Treat this as a hypothesis, not an expected successful result. Define operating points, primary condition, uncertainty method and minimum useful command rate using development evidence before unlocking final test sessions. A null, worse or inconclusive result remains reportable.

## Aim

To design, develop and evaluate a wearable eight-channel EEG-based motor-imagery brain–computer interface using personally acquired recordings for real-time robotic-arm control and computer interaction, while investigating whether risk-aware selective decoding can reduce incorrect accepted commands while preserving command availability under EEG distribution shift.

## Proposed measurable objectives

1. Before model development, integrate and validate an approved eight-channel acquisition setup and collect a documented personal motor-imagery dataset across separate recording sessions, preserving task labels, timestamps, acquisition metadata and a fixed session-partition manifest.

2. Before final evaluation, implement and compare subject-specific motor-imagery decoders and established rejection baselines using development data only, and freeze the selected decoder, reliability mechanism and calibration procedure.

3. During the evaluation phase, quantify errors among accepted familiar-class commands and command acceptance across held-out sessions, separately assess acceptance of unfamiliar imagery where collection is feasible, and evaluate defined simulated channel degradation against established rejection methods at comparable acceptance rates.

4. By the project review deadline, integrate the frozen decoder and gate on Raspberry Pi 4 with approved live acquisition and predefined robotic-arm and computer navigation/selection actions, and document task performance, processing delays, resource use, deadline misses and rejection behaviour.

These four objectives are milestone-bound proposals. Calendar dates and data quantities remain open until acquisition access and the protocol are justified; do not claim full SMART scheduling before those decisions.

## Architecture and application control

Approved headset/electrodes + reference/bias → acquisition front end → timestamped raw stream → causal preprocessing and window buffer → familiar-class decoder → reliability assessment → accept/reject → application state machine → computer action or robotic controller.

Log predicted class, gate score, decision, controller state and executed action separately. A rejection creates no new movement action and clears any unexecuted proposed command; already-started motion requires an independent stopping design. Use bounded actions, command expiry, acknowledgements, rate limits and independent stop/watchdog mechanisms. Verify loss of data, stale commands, repeated predictions and rejection paths before physical motion.

Initially use externally cued command windows with explicit armed/idle states. Two imagery classes can select/confirm within a finite-state menu rather than directly encode every joint or cursor direction. Final mapping and confirmation sequence require usability and safety review. Free asynchronous operation is not claimed: rest/no-command detection requires labelled personal rest data and a separate validation. A reliability gate is not a certified safety controller.

## Personal data and acquisition protocol

Only the researcher's personally acquired EEG may be used for training, model selection, calibration and testing. No BCI Competition IV, OpenBMI, TUAR or other public experimental data; no imported pretrained EEG weights without an explicit scope decision. Literature using public data is permitted. Synthetic inputs may check software interfaces but cannot establish EEG decoding performance.

Plan one participant and repeated sessions on distinct occasions. Initially consider left/right hand imagery. Justify montage, reference, sampling, task timing, breaks, session spacing, trials and recording volume before collection. Do not assume data already exist. Record raw samples, channel order and units, session/trial identifiers, cue and acquisition timestamps, sampling/dropout logs, equipment and software versions, contact/quality observations, posture and relevant acquisition conditions.

Retain raw data and an exclusion log. Task cues label instructed imagery, not verified mental execution. Do not infer actual imagery from classifier output. Assess plausible eye/muscle or cue-related confounds before interpreting decoding as motor-imagery control.

## Training, calibration and evaluation

Partition by session before generating overlapping windows. Keep trials and their windows together. Fit normalization, spatial filters, feature selection and hyperparameters on permitted development data only. Reserve calibration data from final test evaluation. If later-session calibration is investigated, allocate a separate labelled calibration block and report this as a distinct adapted condition; never tune on its test block.

Consider CSP–LDA, a Riemannian classifier and EEGNet as established candidates, not inventions or mandatory three-model deliverables. Select manageable comparisons based on personal-data volume and computational cost. Training may use a development computer; inference is deployed on Raspberry Pi 4. Freeze preprocessing and model/gate parameters before final evaluation.

Compare the ungated decoder, confidence/entropy rejection and a development-trained lightweight reliability gate. Features may include confidence, predictive entropy, feature novelty and quality measures. Train any learned correctness gate on out-of-fold development predictions, not classifier training predictions; use separate gate calibration. Stronger baselines require source inspection and protocol compatibility before adoption.

## Three evaluation conditions

1. Later held-out sessions: preserve temporal separation and document calibration access.
2. Unfamiliar imagery: consider separately recorded feet or tongue imagery, excluded from decoder training, reliability-gate fitting, feature selection and threshold calibration for the novelty test. Do not select unfamiliar classes using final test outcomes. If collection fails, report that test as unperformed and seek an explicit scope amendment.
3. Channel degradation: apply reproducible, documented perturbations to copies of held-out recordings. Prespecify channels, corruption type, severity and random seeds using development data. Preserve clean originals. Simulated corruption is not verification of physical electrode failure.

Report each condition and any combined conditions separately. Do not pool them into one apparent robustness score.

## Outcomes and statistical boundaries

Report familiar-class balanced accuracy/confusion matrices; acceptance fraction; errors/accepted familiar predictions; correct accepted commands per offered opportunity; risk–coverage curves; unfamiliar acceptance fraction; live unintended-action count and task completion/time. Zero accepted commands makes selective error undefined, not zero. Record denominators, excluded trials, failures and aborted tasks.

Primary fixed-threshold comparisons must use calibration-set thresholds; report actual test acceptance when coverage shifts. Matched-coverage test curves may be descriptive comparisons but must not choose deployment thresholds from test labels. Document interpolation/ties and paired comparisons on identical test inputs.

Treat sessions/trials as dependent repeated observations within one person. Do not treat overlapping windows as independent participants. Use session-level descriptive reporting and a justified clustered uncertainty analysis if enough independent sessions exist; otherwise report limited precision without population p-value claims. Training-seed variation is not participant variation.

## Embedded and live validation

First replay personal recordings through the frozen pipeline, then integrate approved incoming EEG. Measure window duration, update interval, preprocessing time, inference time, gate/controller time, communication delay, CPU/memory use and deadline misses separately. Timestamp cue onset, decision and action where possible; cue-to-action is not direct measurement of mental-intention onset. Evaluate live feedback separately from offline accuracy.

Physical robotic-arm control and computer interaction are required parts of the intended final system. Simulation is intermediate evidence. If live or physical integration is blocked, record the intended deliverable as incomplete rather than redefining success.

## Prerequisites, resources and contingency

No human-connected acquisition before institutional ethics authorization and electrical-safety assessment of the complete setup. Self-recording does not waive those requirements. Verify reference/bias wiring, power and every connection to a computer or robotic controller with qualified institutional personnel. Battery operation and a printed enclosure alone do not establish safety.

PiEEG-8 is the planned acquisition front end, subject to compatibility and complete-system approval. On 2 November 2026 the researcher reported a US$100 board price and confirmed that the complete setup, including all equipment, accessories, delivery and import costs, fits within US$200. This supersedes the previous US$300 allowance and manufacturer-list-price procurement assumption. Financial feasibility is supported by the researcher's costing, not independently verified quotations. Hardware evidence and historical prices are retained in chapters/research_viability.md. Equipment performance, approvals, the start date and the proposed 16-week schedule remain to be validated.

If acquisition is blocked before personal data exist, empirical decoder/gate evaluation is blocked too. Software skeletons, non-human bench work and controller simulations may proceed within appropriate approvals, but cannot substitute for the dataset or live demonstration. If usable data already exist with appropriate authorization, report only the offline/embedded work actually supported. Seek funding, suitable institutional equipment access or an explicit schedule/resource amendment; do not silently substitute public data or replay-only completion.

## Boundaries, literature and document authority

This is a single-participant engineering investigation. It cannot establish cross-subject robustness, clinical benefit or population safety. EEGNet, rejection thresholds, reliability gates and novelty detection are established ideas. The precise comparative contribution requires critical literature review.

Academic citations must be published in 2022 or later, APA 7, with metadata and claim support checked. Mark preprints and access limitations. Preserve historical records but exclude pre-2022 citations from current drafts. Hardware evidence is separate from academic references.

goal.md governs scope; sections/ contains the chapter drafts and approval index. The legacy assembled chapter and Word document are not current requirements. Chapter 1 must ultimately follow the DCE 1.1–1.10 structure and render below 20 Word pages using the required formatting. Actual pagination is deferred until assembly.

## Open decisions

Itemised procurement records and actual expenditure against the confirmed US$200 budget; approved hardware topology and robot; ethics route and dates; montage and acquisition protocol; session/trial sufficiency and precision rationale; suitable unfamiliar task; fixed operating points and useful availability criterion; controller mapping and timing; revised calendar; acceptance of the single-participant contribution by the supervisor. No decision here asserts completed work.
