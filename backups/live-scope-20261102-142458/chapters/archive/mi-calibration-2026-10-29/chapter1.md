# Chapter 1: Introduction

**PROVISIONAL DRAFT — supervisor, evidence and equipment confirmation required**

**Provisional title:** Calibration-Efficient Interpretation of Motor Imagery EEG Commands for an Assistive Brain–Computer Interface

**Student:** [Name and registration number]  
**Programme:** [Degree programme]  
**Supervisor:** [Name]  
**Date:** [Date]

## 1.1 Introduction

A brain–computer interface (BCI) translates measurable brain activity into signals for communication or control. A non-invasive BCI records activity without surgically implanted electrodes, often using electroencephalography (EEG). Such interfaces have been investigated alongside assistive technologies for people whose movement or speech limits ordinary interaction, including interfaces for selecting messages and controlling devices [1, 2]. A research demonstrator can investigate interaction principles without establishing clinical benefit or replacing existing assistive equipment.

An EEG interface must acquire small signals at suitable scalp locations, process them in time, distinguish intended actions from competing activity and deliver understandable feedback. Differences among users and recordings complicate this pipeline, while errors may result in an unintended selection or a missed command [2, 3]. Training a decoder on data collected from each new user can improve its fit but creates an additional task before use. This proposal investigates the engineering trade-off between individual calibration and reliable interpretation of motor imagery commands, subject to the feasibility of obtaining suitable EEG equipment.

## 1.2 Brief background information about the project

Scalp EEG electrodes measure voltage differences associated with electrical activity in the brain, mixed with other electrical and physiological signals. Electrode positions are commonly described using the international 10–20 or 10–10 systems. An amplifier samples electrode voltages relative to a reference; the placement, reference and contact quality influence what information reaches the decoder. Sensorimotor positions such as C3 and C4 are relevant to hand motor imagery, whereas visual paradigms typically use posterior electrodes [2, 4, 5].

A typical pipeline records EEG, filters frequencies of interest, segments data into time windows, derives features, and uses a classifier to select a class. A decision layer then determines whether to issue a command or wait, and an interface displays the outcome. Motor imagery (MI) asks a user to imagine movement, producing changes in sensorimotor rhythms. P300 interfaces use event-related responses to attended stimuli, while steady-state visually evoked potential (SSVEP) interfaces detect responses related to repetitive visual stimulation [2, 5]. These paradigms differ in required training, stimuli, electrode positions and user capabilities. MI is provisionally selected here because two-class public datasets and central electrode layouts permit direct comparison of user and session transfer; it is not presumed superior for all users.

EEG may be affected by eye movements, muscle activity, electrode motion and electrical interference. Filtering cannot guarantee that the remaining signal represents only brain activity, and a method suitable offline may not be suitable in real time [6]. Differences in physiology, attention, electrode contact and session conditions can change the relationship between features and labels. Calibration collects labelled examples from the intended user; it is distinct from setup time and from unlabelled adaptation. A zero-labelled-calibration system may still require setup or unlabelled data.

In an asynchronous interface, a command can be attempted at a user's chosen time. The decoder must distinguish control from non-control as well as identify the intended command. A stricter acceptance threshold may reduce false activations at the expense of missed or delayed commands [7]. Eye tracking, a webcam, electrooculography (EOG) and inertial measurement units (IMUs) can offer supplementary observations, but introduce requirements and may exclude users who cannot reliably perform the necessary movements [7, 8]. Their benefit must be measured against a comparable EEG-only system.

## 1.3 Literature review to focus on gap analysis

### Calibration and transfer

Calibration reduction is an established research area. Singh et al. [9] evaluated spatially regularised covariance-based classification in limited-sample MI settings, whereas Xiong and Wei [10] used alignment and augmented training examples on two datasets. These are different methods and their reported accuracy is not directly comparable across datasets and protocols. Neither paper establishes that a small calibration set always suffices in live use.

Rao et al. [11] provide a particularly important counterexample to any claim that calibration-free live MI has not been achieved. Their abstract describes a subject-independent model trained on data from 100 healthy people and online experiments involving healthy participants and stroke patients. Reported accuracy increased from 69% initially to 81% and then 86% after supervised online updates; a subject-specific comparison was 80%. Their use of labelled online data means that “no offline calibration” does not mean no user-specific information or effort. The abstract does not establish the entire calibration accounting or permit replication of the experiments; the full article should be checked before a stronger comparison is claimed.

Session variability is also documented. Ma et al. [12] collected two-class MI on five days from 25 people and reported benchmark averages of up to 68.8% within session, 53.7% across sessions and 78.9% with adaptation. These are results of their specific procedures, not guaranteed effects of adaptation in other populations. The distinction between labelled and unlabelled adaptation, the data used for each comparison, and the original analysis must be inspected before drawing detailed causal conclusions. Lee et al. [5] provide multiple paradigms and sessions from 54 participants, allowing evaluation beyond one small dataset.

### Signal quality and unintentional activation

Artifact reduction has a substantial literature, and the systematic review by Schmoigl-Tonis et al. [6] documents methods for motion artifacts in online BCI. Low signal quality can cause incorrect decisions, but removing an artifact does not by itself demonstrate a reduction in unwanted commands. A classifier can confidently label an idle window as a command even when the EEG is clean; an artifact detector and a decision threshold address different failure modes.

Song et al. [3] evaluated a low-channel decision approach in a pilot involving healthy participants and people with stroke. Their system used participant-specific calibration and threshold adjustment; its online evaluation included 14 participants and reported sensitivity below 30% alongside false-positive measures. This illustrates a meaningful sensitivity–false-positive trade-off, although the rehabilitation task, control periods and devices differ from a two-command assistive interface. Zhou et al. [7] used SSVEP and blink EOG in 10 healthy participants and reported 95.42% accuracy and a 0.8% false-positive rate under their own experimental definitions. These outcomes cannot be compared numerically with Song et al. because the paradigms, protocols and denominators differ. Nagel and Spüler [13] also studied asynchronous detection in a visual BCI, further demonstrating that rejection is not a new concept.

### Additional sensing and choice of problem

EEG and eye sensing have already been combined. Lee et al. [8] reported that webcam gaze information prevented some incorrect selections in an SSVEP spelling experiment with 10 healthy participants; Zhou et al. [7] combined visual EEG and EOG. These examples demonstrate potential, not incremental benefit for MI commands or for every user. Gaze and intentional blinking can be difficult for some intended users, and a camera introduces placement, lighting and privacy constraints. This project therefore starts with EEG alone. A camera, EOG or IMU is not part of the primary contribution; adding one would require matched EEG-only and multimodal conditions and a defensible access need.

The most defensible provisional question is how a simple, low-channel MI decoder behaves across unseen users when labelled target-user data is progressively introduced, and how command acceptance changes the accuracy–rejection trade-off. It joins established ideas in a controlled comparison rather than asserting a new class of algorithm. The contribution could be a reproducible calibration budget and decision-reliability evaluation, plus a live research demonstrator. It is not yet established that this particular combination is novel: the closest studies, including Rao et al. [11], require full-text comparison, and a suitable within-budget recording device has not been identified. See the accompanying gap analysis and literature matrix.

## 1.4 Problem Definition

Individual differences and changes between EEG recording sessions can reduce the reliability of an MI decoder trained on other data, while collecting labelled examples from each user imposes a calibration burden [5, 10, 12]. If commands are accepted during non-control or classified incorrectly, an assistive interface can perform an unintended action; if acceptance is too conservative, intentional actions can be missed or delayed [3, 7]. These consequences matter to a person attempting to communicate or control a computer and to anyone assisting with setup. The reviewed evidence demonstrates these difficulties under particular protocols, rather than proving their frequency in everyday assistive use.

Existing alignment, limited-sample classification and online adaptation methods have reduced or avoided some offline calibration in particular studies [9–11]. Rao et al. [11] show that useful online performance with no offline calibration is possible, but their supervised updates consume labelled online information. Song et al. [3] demonstrate a distinct attempt to limit false positives with individual calibration. These results support investigation of the trade-off, not a claim that reliable zero-calibration operation is universally impossible or that the proposed combination has not been attempted. The effects of calibration amount and acceptance threshold must be evaluated with matching data partitions and appropriate non-control recordings.

The research problem is the uncertain reliability of motor imagery EEG command interpretation for previously unseen users when individual calibration is substantially reduced.

## 1.5 Aims and Objectives

**Aim:** To develop and evaluate a calibration-efficient method for interpreting intentional motor imagery EEG commands in a non-invasive assistive BCI research demonstrator.

**Primary research question:** How do the amount of labelled new-user calibration and the command acceptance threshold affect motor imagery command classification and rejection performance for previously unseen users?

**Objectives:**

1. Compare evidence and publicly available MI datasets to specify a two-command task, suitable central channels and a reproducible user-independent evaluation protocol before method development.
2. Implement a pooled cross-user decoder and a limited-calibration adaptation method, and compare them with pooled and user-specific baselines at zero, 5, 10 and 20 labelled trials per class and an available full-calibration condition.
3. Quantify participant-level balanced accuracy, calibration effort and the acceptance–rejection trade-off on held-out data; report false activations during separately labelled non-control periods only where those periods are available and appropriate.
4. Integrate the selected decoder with live, safely acquired EEG and a two-command computer interface, then measure command outcomes and response latency in consenting adults under an approved protocol, subject to confirmed equipment and ethics clearance.

The trial counts define experimental conditions, not promised improvements. Full calibration is the number of training trials actually available after holding out validation and test data, reported for each dataset. Cross-session analysis is a secondary objective where session labels and data volume permit.

## 1.6 Methods and Instruments

### Research design and datasets

The project will follow a design science research cycle: specify an engineering problem, build an artifact, evaluate it quantitatively and use the observations to revise it. Controlled offline comparisons precede a live prototype evaluation; neither the method nor an improvement is assumed successful. The primary data source is the [PhysioNet EEG Motor Movement/Imagery dataset](https://physionet.org/content/eegmmidb/1.0.0/) [14]: 109 volunteers, 64 EEG channels at 160 Hz, with imagined left and right fist movements and labelled rest intervals. Its Open Data Commons Attribution License 1.0 permits access subject to its terms. Rest is cued and constrained; its labels support a controlled non-control proxy, not claims about all everyday inactivity.

For cross-session evaluation, the [SHU dataset](https://doi.org/10.6084/m9.figshare.19228725.v1) associated with Ma et al. [12] contains 25 participants, five sessions, 32 channels and two hand-imagery classes. Its published trials were filtered and bad segments removed, so they cannot establish robustness to unobserved artifacts; confirm the data licence on the repository before use. The [BNCI 001-2014 dataset](https://bnci-horizon-2020.eu/database/data-sets) contains nine participants, two sessions, 22 EEG and three EOG channels and four MI classes; use its left/right classes as a small secondary comparison, subject to its CC BY-ND 4.0 terms. Its task trials do not establish naturalistic non-control performance. Restrict each dataset to a prespecified common subset of available central electrodes, provisionally C3, Cz and C4, while retaining the original reference information. Dataset characteristics and acquisition differences limit direct cross-dataset comparisons.

### Decoder and comparators

Use band-pass-filtered sensorimotor EEG and common spatial pattern (CSP) features with regularised linear discriminant analysis (LDA), a conventional interpretable baseline [10]. The candidate method pools labelled source-user examples and adds the available target-user calibration trials, with regularisation selected using training data only. Compare (A) pooled source-only model with no target-user data; (B) pooled plus 5, 10 or 20 labelled target trials per class; and (C) subject-specific CSP–LDA trained on the same limited budgets and on the available full training set. Pooling and regularisation are established techniques; the experiment tests their practical trade-offs rather than claiming the components are novel. If the fixed three-channel montage makes CSP unstable, document failure and compare a regularised log-variance–LDA baseline using identical splits.

For each held-out participant, keep all their evaluation trials out of source training. Split their sessions or runs chronologically into calibration/validation and final test blocks; leave test blocks untouched when selecting preprocessing parameters, channel choices, calibration examples and thresholds. Repeat calibration sampling using recorded seeds, without splitting overlapping windows from one trial or recording across partitions. Inner validation must be drawn only from source participants and permitted target calibration data; with no target calibration, set thresholds using source-only validation. Include a separately specified cross-session test on later sessions for known users, with earlier sessions for training and any permitted adaptation. Fit filters that learn parameters, feature transforms, normalisation, classifier and threshold inside each training fold. Do not use test labels or whole-test-session statistics for adaptation. Report failures and excluded recordings with reasons.

A decision layer compares the highest class score against a threshold chosen on validation data; report the full acceptance curve rather than selecting a test-set threshold. Scores are not assumed to be calibrated probabilities. For true labelled non-control, count distinct false command events per minute of non-control time, using fixed windows, a prespecified refractory interval and event-merging rules. Report missed command trials and false rejections as fractions of labelled intentional trials, and distinguish an accepted wrong class from a rejected command. Report balanced accuracy for the two MI classes, per-user results and participant-level paired differences with uncertainty intervals. Report trial counts, elapsed calibration time if measured, decision latency, and computer resources; trial counts alone are not time measurements. On datasets without appropriate non-control intervals, report only class accuracy and selective rejection, not false activations. No statistical significance or clinical benefit is assumed.

### Live research prototype

The planned architecture is **scalp electrodes → battery-powered EEG acquisition device and wireless or otherwise safety-reviewed interface → computer running acquisition, filtering and decoder → two-command message-selection interface with visible feedback**. Confirm channel placement, sampling, raw data access, software driver, battery isolation and supervised safe use for the actual device before recording. A physically connected amplifier must acquire live EEG; replay and simulation may assist development but cannot satisfy the live prototype objective. Measure end-to-end latency from labelled task onset to displayed command and count errors in explicitly instructed control and non-control periods. A small adult pilot is an engineering feasibility exercise, not a clinical trial. Offline performance does not validate the live system.

## 1.7 Expected results and Significance of the project

### 1.7.1 Expected results

Expected deliverables are an implemented decoding and decision procedure, reproducible comparative results for the stated calibration budgets, a dissertation presenting both favourable and unfavourable results, and a functioning live EEG demonstrator if equipment and approvals are secured. The experiments will determine whether limited calibration changes command classification and rejection under the specified conditions. No improvement is assumed.

### 1.7.2 Significance of the project

Scientifically, the comparison can clarify how calibration effort relates to MI classification and rejection under reproducible conditions. Engineering value lies in a measured low-channel implementation and documented prototype constraints. Assistive relevance is prospective: a reliable low-burden interface could support communication or computer control, but a healthy-adult pilot cannot establish clinical effectiveness or accessibility for a particular impairment [1, 3].

## 1.8 Feasibility study

**Technical:** Public datasets and standard scientific computing tools enable initial offline work. A live demonstration requires a suitable amplifier, electrodes, reference and ground, reliable streaming and a compatible central montage. OpenBCI lists a four-channel Ganglion at USD 624.99, excluding electrodes and its required dongle, and an eight-channel Cyton at USD 1,249 without electrodes [15, 16]. Their prices alone exceed the entire USD 100–300 hardware allowance. The Ganglion is a useful specification benchmark, not an affordable confirmed solution. Availability and suitability of another device, electrical safety and local delivery remain unverified.

**Operational:** No laboratory equipment, supervisor support, computing specification, recruitment route or ethics clearance is confirmed. Training, electrode application, artifact handling, participant scheduling and pilot repetitions must fit within two semesters. A working development computer and software access are assumptions to verify. Recordings must not begin before approval and a safety assessment.

**Economic:** On currently verified vendor listings, a complete owned research acquisition system cannot be shown to fit the budget. Procurement quotes must cover the device, essential electrodes, interface, shipping and Zimbabwe import costs. If a suitable safe device cannot be acquired for at most USD 300 delivered, the physical-prototype requirement and project scope must be reassessed with the supervisor; an offline-only substitution would not satisfy this proposal.

## 1.9 Ethics Consideration

A detailed participant protocol and the responsible University of Zimbabwe review route remain to be confirmed with the supervisor and relevant institutional office. Obtain written institutional ethics clearance and device safety approval before recruiting or recording. Recruit consenting adults initially; explain procedures, potential discomfort, data use, voluntary participation and withdrawal, including any practical limits on withdrawing anonymised data. Establish eligibility and exclusion criteria with the reviewing body and stop on request or discomfort.

Use suitable battery-powered, electrically safe recording equipment under supervision, follow manufacturer instructions and hygiene procedures, and avoid unassessed mains-connected custom circuits. Store EEG and consent records separately with coded identifiers, restricted access, encryption, and an approved retention and deletion schedule. EEG can contain sensitive personal information. If a camera is later justified, obtain specific consent and define image handling, minimisation and retention. MI does not require flickering stimuli; if the paradigm changes to a visual stimulus, obtain appropriate safety screening and review. No approval or clinical effectiveness is claimed.

## 1.10 Delimitations and Limitations of the research

**Delimitations:** The primary experiment uses non-invasive EEG, two hand-imagery commands, an EEG-only decoder and a computer-based demonstrator. It focuses on calibration budgets, classification and the acceptance–rejection trade-off; it does not assess clinical treatment or powered mobility control.

**Limitations:** The reviewed public datasets use different amplifiers, montages and constrained tasks. Their participants do not represent all intended assistive users, and short labelled rest intervals do not reproduce real-world inactivity. A small live pilot cannot establish population-level clinical benefit. Session analysis depends on usable data and the equipment available. The device, its safe operation, delivered price, ethics pathway and recruitment are unconfirmed; each could require a change of scope. The proposed method is not yet established as novel.

## 1.11 Budget and Timelines

### Provisional hardware budget

The total permitted hardware expenditure is USD 100–300, including delivery and import charges. The following reference configuration exceeds the ceiling and is **not an approved budget**.

| Item | Published price or status | Source / qualification |
|---|---:|---|
| Ganglion four-channel board | USD 624.99 | [Vendor listing](https://shop.openbci.com/products/ganglion-board); board, case, battery and charger; electrodes and dongle excluded |
| Required Ganglion dongle | USD 19.99 | [Vendor listing](https://shop.openbci.com/collections/all) |
| Gold cup electrodes | From USD 44.99 | [Vendor listing](https://shop.openbci.com/collections/openbci-products); exact configuration and quantities unconfirmed |
| Consumables, mounting and any adapters | Unquoted | Quote required; do not assume the listed electrodes are a complete kit |
| Shipping and Zimbabwe import charges | Unquoted | Obtain destination-specific seller and customs quotes |
| Contingency | Unallocated | Cannot be established within the ceiling with this configuration |
| Minimum of listed components | **USD 689.97** | Before remaining accessories, shipping and import charges; exceeds USD 300 by USD 389.97 |

Prices viewed 28 October 2026; availability, taxes and delivery must be reconfirmed. Confirm whether the electrode listing provides enough electrodes and leads before using it in any purchase calculation. The minimum is illustrative, not a complete purchase quote.

### Relative two-semester timeline

| Period | Planned activity and decision |
|---|---|
| Semester 1, months 1–2 | Review sources, validate gap and datasets, agree proposal and safety requirements. |
| Semester 1, months 2–3 | Obtain quotations and assess the hardware gate; seek supervisor decision if the budget cannot support live acquisition. |
| Semester 1, months 3–4 | Implement leakage-controlled public-dataset baselines and record initial comparisons. |
| Semester 2, months 1–2 | Develop and evaluate limited-calibration method; finalise protocol and submit ethics application. |
| Semester 2, months 2–3 | Subject to procurement and approvals, integrate live acquisition and conduct supervised pilot recordings. |
| Semester 2, months 3–4 | Analyse results, write dissertation, review limitations and prepare demonstration. |

Actual dates, institutional review times and examination milestones require confirmation. Procurement and ethics delays may prevent the live stage.

## 1.12 Conclusion

EEG-based BCIs offer a possible interaction channel, but user and session variability, calibration burden and erroneous decisions complicate practical use. This proposal investigates a bounded two-class MI calibration and decision-reliability trade-off using public datasets and a planned live demonstrator. The scientific originality, safe equipment acquisition within budget and approval pathway remain unresolved, so the proposal is provisional.

## References

*Provisional IEEE-style numerical references; university citation requirements and each citation's final source check require supervisor review.*

[1] J. del R. Millán et al., “Combining Brain-Computer Interfaces and Assistive Technologies: State-of-the-Art and Challenges,” *Frontiers in Neuroscience*, 2010, doi: [10.3389/fnins.2010.00161](https://doi.org/10.3389/fnins.2010.00161).

[2] M. Rashid et al., “Current Status, Challenges, and Possible Solutions of EEG-Based Brain-Computer Interface: A Comprehensive Review,” *Frontiers in Neurorobotics*, vol. 14, 25, 2020, doi: [10.3389/fnbot.2020.00025](https://doi.org/10.3389/fnbot.2020.00025).

[3] M. Song et al., “An EEG-based asynchronous MI-BCI system to reduce false positives with a small number of channels for neurorehabilitation: A pilot study,” *Frontiers in Neurorobotics*, vol. 16, 971547, 2022, doi: [10.3389/fnbot.2022.971547](https://doi.org/10.3389/fnbot.2022.971547).

[4] H. Cho et al., “EEG datasets for motor imagery brain–computer interface,” *GigaScience*, vol. 6, no. 7, pp. 1–8, 2017, doi: [10.1093/gigascience/gix034](https://doi.org/10.1093/gigascience/gix034).

[5] M.-H. Lee et al., “EEG dataset and OpenBMI toolbox for three BCI paradigms: an investigation into BCI illiteracy,” *GigaScience*, vol. 8, no. 5, giz002, 2019, doi: [10.1093/gigascience/giz002](https://doi.org/10.1093/gigascience/giz002).

[6] M. Schmoigl-Tonis, C. Schranz and G. R. Müller-Putz, “Methods for motion artifact reduction in online brain-computer interface experiments: a systematic review,” *Frontiers in Human Neuroscience*, vol. 17, 1251690, 2023, doi: [10.3389/fnhum.2023.1251690](https://doi.org/10.3389/fnhum.2023.1251690).

[7] Y. Zhou, S. He, Q. Huang and Y. Li, “A Hybrid Asynchronous Brain-Computer Interface Combining SSVEP and EOG Signals,” *IEEE Transactions on Biomedical Engineering*, vol. 67, no. 10, pp. 2881–2892, 2020, doi: [10.1109/TBME.2020.2972747](https://doi.org/10.1109/TBME.2020.2972747).

[8] J.-H. Lee, J.-H. Lim, H.-J. Hwang and C.-H. Im, “Development of a hybrid mental speller combining EEG-based brain-computer interface and webcam-based eye-tracking,” *IEEE Engineering in Medicine and Biology Society Annual International Conference*, pp. 2240–2242, 2013, doi: [10.1109/EMBC.2013.6609982](https://doi.org/10.1109/EMBC.2013.6609982).

[9] A. Singh, S. Lal and H. W. Guesgen, “Reduce Calibration Time in Motor Imagery Using Spatially Regularized Symmetric Positives-Definite Matrices Based Classification,” *Sensors*, vol. 19, no. 2, 379, 2019, doi: [10.3390/s19020379](https://doi.org/10.3390/s19020379).

[10] W. Xiong and Q. Wei, “Reducing calibration time in motor imagery-based BCIs by data alignment and empirical mode decomposition,” *PLOS ONE*, vol. 17, no. 2, e0263641, 2022, doi: [10.1371/journal.pone.0263641](https://doi.org/10.1371/journal.pone.0263641).

[11] Z. Rao et al., “Calibration-Free Online Detection in Wearable Motor Imagery Brain-Computer Interfaces,” *IEEE Transactions on Neural Systems and Rehabilitation Engineering*, vol. 34, pp. 2604–2616, 2026, doi: [10.1109/TNSRE.2026.3695774](https://doi.org/10.1109/TNSRE.2026.3695774).

[12] J. Ma et al., “A large EEG dataset for studying cross-session variability in motor imagery brain-computer interface,” *Scientific Data*, vol. 9, 531, 2022, doi: [10.1038/s41597-022-01647-1](https://doi.org/10.1038/s41597-022-01647-1).

[13] S. Nagel and M. Spüler, “Asynchronous non-invasive high-speed BCI speller with robust non-control state detection,” *Scientific Reports*, 2019, doi: [10.1038/s41598-019-44645-x](https://doi.org/10.1038/s41598-019-44645-x).

[14] G. Schalk, “EEG Motor Movement/Imagery Dataset,” version 1.0.0, PhysioNet, 2009, doi: [10.13026/C28G6P](https://doi.org/10.13026/C28G6P).

[15] OpenBCI, “Ganglion Board (4-channels),” product listing, accessed 28 Oct. 2026. [Online](https://shop.openbci.com/products/ganglion-board).

[16] OpenBCI, “Cyton Biosensing Board (8-channels),” product listing, accessed 28 Oct. 2026. [Online](https://shop.openbci.com/products/cyton-biosensing-board-8-channel).
