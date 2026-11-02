# Literature Review — Non-Invasive EEG Brain–Computer Interfaces

**Compiled:** 28 October 2026
**Focus:** Assistive BCIs; signal noise/artifacts; unintended commands; EEG with eye tracking/EOG; low-channel and edge-AI systems.

> This index consolidates research papers mentioned during our BCI dissertation discussions. Links generally point to permanent DOI publisher pages, with Consensus/arXiv links where appropriate. These are not necessarily free full-text downloads. A linked article is not automatically evidence of a new research gap; evaluate its methods, baseline comparisons, and limitations before citing it.

## How to use this file

- Start with the review papers, then study the closest experimental work in Sections 2–4.
- Record each paper in a literature matrix: question, method, EEG channels/hardware, dataset, baselines, metrics, limitations, and gap hypothesis.
- Import papers into Zotero using their DOI wherever possible; do not automatically treat this list as a formatted final reference section.
- **Preprint note:** arXiv papers are identified as preprints and should be distinguished from peer-reviewed sources.

---

## 1. BCI foundations, reviews and assistive communication

- **Building Dependable EEG Classifiers for the Real World – It’s Not Just about the Hardware** (2009). Davis et al.; conference chapter. [Paper link](https://doi.org/10.1007/978-3-642-02812-0_42)
- **Combining Brain–Computer Interfaces and Assistive Technologies: State-of-the-Art and Challenges** (2010). Millán et al.; Frontiers in Neuroscience. [Paper link](https://doi.org/10.3389/fnins.2010.00161)
- **Stimuli and Feature Extraction Algorithms for Brain-Computer Interfaces: A Systematic Comparison** (2018). Bittencourt-Villalpando & Maurits; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2018.2855801)
- **Current Status, Challenges, and Possible Solutions of EEG-Based Brain-Computer Interface: A Comprehensive Review** (2020). Rashid et al.; Frontiers in Neurorobotics. [Paper link](https://doi.org/10.3389/fnbot.2020.00025)
- **Mind the Gap: State-of-the-Art Technologies and Applications for EEG-Based Brain–Computer Interfaces** (2021). Portillo-Lara et al.; APL Bioengineering. [Paper link](https://doi.org/10.1063/5.0047237)
- **Non-invasive EEG-based BCI spellers from the beginning to today: a mini-review** (2023). Maslova et al.; Frontiers in Human Neuroscience. [Paper link](https://doi.org/10.3389/fnhum.2023.1216648)
- **An Evaluation of the P300 Brain–Computer Interface, EyeLink Board, and Eye-Tracking Camera as Augmentative and Alternative Communication Devices** (2022). Elliott et al.; Journal of Speech, Language, and Hearing Research. [Paper link](https://doi.org/10.1044/2022_JSLHR-21-00572)

## 2. EEG artifacts, noise, signal quality and wearable reliability

- **Efficient Artifact Removal from Low-Density Wearable EEG Using Artifacts Subspace Reconstruction** (2021). Kumaravel et al.; IEEE EMBC. [Paper link](https://doi.org/10.1109/EMBC46164.2021.9629771)
- **Methods for motion artifact reduction in online brain-computer interface experiments: a systematic review** (2023). Schmoigl-Tonis et al.; Frontiers in Human Neuroscience. [Paper link](https://doi.org/10.3389/fnhum.2023.1251690)
- **An Empirical Model-Based Algorithm for Removing Motion-Caused Artifacts in Motor Imagery EEG Data for Classification Using an Optimized CNN Model** (2024). Megalingam et al.; Sensors. [Paper link](https://doi.org/10.3390/s24237690)
- **A Systematic Review of Techniques for Artifact Detection and Artifact Category Identification in Electroencephalography from Wearable Devices** (2025). Arpaia et al.; Sensors. [Paper link](https://doi.org/10.3390/s25185770)
- **Beyond the lab: real-world benchmarking of wearable EEGs for passive brain-computer interfaces** (2025/2026). Ronca et al.; online December 2025, Brain Informatics 2026 issue. [Paper link](https://doi.org/10.1186/s40708-025-00290-x)
- **Improved SSVEP Classification Through EEG Artifact Reduction Using Auxiliary Sensors** (2026). Kołodziej et al.; Sensors. [Paper link](https://doi.org/10.3390/s26030917)
- **Detection of eye movements and eye blinks using a portable two-channel EEG platform** (2026). Zhong et al.; Journal of Neuroscience Methods. [Paper link](https://doi.org/10.1016/j.jneumeth.2025.110616)

## 3. Asynchronous BCIs, false activations and command rejection

- **Asynchronous non-invasive high-speed BCI speller with robust non-control state detection** (2019). Nagel & Spüler; Scientific Reports. [Paper link](https://doi.org/10.1038/s41598-019-44645-x)
- **A Hybrid Asynchronous Brain-Computer Interface Combining SSVEP and EOG Signals** (2020). Zhou et al.; IEEE Transactions on Biomedical Engineering; also relevant to multimodal sensing. [Paper link](https://doi.org/10.1109/TBME.2020.2972747)
- **An EEG-based asynchronous MI-BCI system to reduce false positives with a small number of channels for neurorehabilitation: A pilot study** (2022). Song et al.; Frontiers in Neurorobotics. [Paper link](https://doi.org/10.3389/fnbot.2022.971547)
- **Enhancing Detection of Control State for High-Speed Asynchronous SSVEP-BCIs Using Frequency-Specific Framework** (2023). Ke et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2023.3246359)
- **BCI-Utility Metric for Asynchronous P300 Brain-Computer Interface Systems** (2023). Ma et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2023.3322125)
- **A Wearable Asynchronous Brain-Computer Interface Based on EEG-EOG Signals With Fewer Channels** (2023/2024). Hu et al.; first published 2023, IEEE TBME 2024 issue; also relevant to multimodal sensing. [Paper link](https://doi.org/10.1109/TBME.2023.3308371)
- **Temporal Out-of-Distribution Detection for Asynchronous Motor Imagery Brain-Computer Interfaces** (2026). Liu et al.; arXiv preprint — not assumed peer-reviewed. [Paper link](https://arxiv.org/abs/2605.01014)

## 4. EEG + eye tracking, EOG and multimodal sensing

- **Development of a hybrid mental spelling system combining SSVEP-based brain-computer interface and webcam-based eye tracking** (2015). Lim et al.; Biomedical Signal Processing and Control. [Paper link](https://doi.org/10.1016/j.bspc.2015.05.012)
- **A Novel Hybrid Mental Spelling Application Based on Eye Tracking and SSVEP-Based BCI** (2017). Stawicki et al.; Brain Sciences. [Paper link](https://doi.org/10.3390/brainsci7040035)
- **A Hybrid BCI Integrating EEG and Eye-Tracking for Assisting Clinical Communication in Patients With Disorders of Consciousness** (2024). Yi et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2024.3435016)
- **Dataset combining EEG, eye-tracking, and high-speed video for ocular activity analysis across BCI paradigms** (2025). Guttmann-Flury et al.; Scientific Data; dataset paper. [Paper link](https://doi.org/10.1038/s41597-025-04861-9)

## 5. Few-channel BCIs, calibration and cross-subject generalization

- **Channel selection methods for the P300 Speller** (2014). Colwell et al.; Journal of Neuroscience Methods. [Paper link](https://doi.org/10.1016/j.jneumeth.2014.04.009)
- **A Robust Low-Cost EEG Motor Imagery-Based Brain-Computer Interface** (2018). Yohanandan et al.; IEEE EMBC. [Paper link](https://doi.org/10.1109/EMBC.2018.8513429)
- **Subject-Independent Wearable P300 Brain-Computer Interface Based on Convolutional Neural Network and Metric Learning** (2024). Hu et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2024.3457502)
- **Multi-scale EEG feature decoding with Swin Transformers for subject independent motor imagery BCIs** (2026). Qamar & Abibullaev; Scientific Reports. [Paper link](https://doi.org/10.1038/s41598-025-32207-3)
- **Calibration-Free Online Detection in Wearable Motor Imagery Brain-Computer Interfaces** (2026). Rao et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2026.3695774)

## 6. Edge AI, TinyML and real-time embedded BCI inference

- **On-Device Implementation for Deep-Learning-Based Cognitive Activity Prediction** (2022). Saini & Satija; IEEE Sensors Letters. [Paper link](https://doi.org/10.1109/LSENS.2022.3156158)
- **TinyML for EEG Decoding on Microcontrollers** (2023). Tragoudaras et al.; IEEE ISCAS. [Paper link](https://doi.org/10.1109/ISCAS46773.2023.10181950)
- **Low-power EEGNet-based Brain-Computer Interface implemented on an Arduino Nano 33 Sense** (2023). Enériz et al.; IEEE DCIS. [Paper link](https://doi.org/10.1109/DCIS58620.2023.10335978)
- **On-device Learning of EEGNet-based Network For Wearable Motor Imagery Brain-Computer Interface** (2024). Bian et al.; ACM ISWC. [Paper link](https://doi.org/10.1145/3675095.3676607)
- **Edge AI-Brain-Computer Interfaces System: A Survey** (2025). Nguyen et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2025.3618688)

## 7. SSVEP user experience, fatigue and visual-stimulus design

- **Improving user experience of SSVEP BCI through low amplitude depth and high frequency stimuli design** (2022). Scientific Reports. [Paper link](https://doi.org/10.1038/s41598-022-12733-0)
- **A SSVEP-Based Brain-Computer Interface With Low-Pixel Density of Stimuli** (2023). Meng et al.; IEEE TNSRE. [Paper link](https://doi.org/10.1109/TNSRE.2023.3328917)
- **Fatigue factors and fatigue indices in SSVEP-based brain-computer interfaces: a systematic review and meta-analysis** (2023). Moghadam & Maleki; Frontiers in Human Neuroscience. [Paper link](https://doi.org/10.3389/fnhum.2023.1248474)
- **A subjective and objective fusion visual fatigue assessment system for different hardware and software parameters in SSVEP-based BCI applications** (2024). Tian et al.; Scientific Reports. [Paper link](https://doi.org/10.1038/s41598-024-79401-3)
- **SSVEP-based BCI using ultra-low-frequency and high-frequency peripheral flickers** (2025). Pang et al.; Journal of Neural Engineering. [Paper link](https://doi.org/10.1088/1741-2552/addf82)

---

## Scope and verification notes

- The bibliography is organized by topic; closely related articles appear once rather than being duplicated in multiple categories.
- Links were checked against publisher, PubMed, institutional or scholarly records where possible. Certain earlier broad references lacked a unique exact title and are therefore not treated as verified citations.
- Some papers were first published online in one calendar year and assigned to a journal issue in the following year; both dates are noted in the relevant entry.

**Original entries retained: 40**


## Artifact-category identification and classification: additions from migration

These additions are targeted against the new topic. “Full text reviewed” describes the source inspection in this migration; metadata-only/abstract-only records are identified accordingly. The original 40 entries above are retained unchanged. Newly added sources are additional records; verification depth is stated per entry.

- **A Systematic Review of Techniques for Artifact Detection and Artifact Category Identification in Electroencephalography from Wearable Devices** (2025). Pasquale Arpaia et al.; *Sensors*, 25(18), 5770. DOI: [10.3390/s25185770](https://doi.org/10.3390/s25185770). Relevance: wearable-focused methods, taxonomy and metrics; identified prior category/source studies; search ended 24 April 2025. **Verification: publisher/PMC full text reviewed.**
- **Recording and Characterization of EEGs by Using Wearable EEG Device** (2019). Ryo Goto, Ryo Inoue et al.; 2019 19th International Conference on Control, Automation and Systems, 194–197. DOI: [10.23919/ICCAS47443.2019.8971564](https://doi.org/10.23919/ICCAS47443.2019.8971564). Relevance: wearable blink, lateral eye movement and EMG detection. **Verification: bibliographic/abstract record reviewed; full text not reviewed.**
- **Automatic Removal of Multiple Artifacts for Single-Channel Electroencephalography** (2022). Chenbei Zhang, Nabil Sabor, Junwen Luo, Yu Pu, Guoxing Wang and Yong Lian; *Journal of Shanghai Jiao Tong University (Science)*, 27(4), 437–451. DOI: [10.1007/s12204-021-2374-5](https://doi.org/10.1007/s12204-021-2374-5). Relevance: category-aware staged processing for ocular, line/harmonic and muscle artifact in a single channel. **Verification: publisher record and abstract reviewed; full methods not reviewed.**
- **A gated artifact management pipeline for low-density eyewear EEG** (2026). Andrea Costanzo Palmisciano et al.; *Physiological Measurement*, 47(9). DOI: [10.1088/1361-6579/ae99ab](https://doi.org/10.1088/1361-6579/ae99ab). Relevance: direct wearable artifact detection, three-class discrimination and correction competitor. **Verification: PubMed abstract and publisher-indexed sections reviewed; code not audited.**
- **Automatic EEG artifact detection using a local-global feature fusion network in time and time-frequency domains** (2026). Qindong Yu, Chuan Lin, Weibo Wang, Zhanhui Feng et al.; *Acta Epileptologica*, 8, art. 7. DOI: [10.1186/s42494-026-00248-4](https://doi.org/10.1186/s42494-026-00248-4). Relevance: multi-class TUAR clinical artifact classification and cross-dataset clinical evaluation. **Verification: publisher full text and author record reviewed; author list abbreviated.**
- **Temple University EEG Corpus (TUAR v3.0.1) documentation.** Neural Engineering Data Consortium. [Official access page](https://isip.piconepress.com/projects/nedc/html/tuh_eeg/). Relevance: five artifact labels and application-based access. **Verification: official documentation reviewed; corpus contents, license/data-use agreement and class distributions not inspected.**

## Topic groups for prior records

The existing records are retained in their original 40-entry organization to avoid lossy rewriting. For artifact-related material, consult the existing “EEG artifacts, noise, signal quality and wearable reliability” group and the additions above. The calibration-focused group remains as historical background, not the active topic.

## Migration verification note

Targeted search date: 29 October 2026. Queries are recorded in `chapters/chapter1_literature_matrix.md`. Search-result snippets were not treated as final evidence; publisher, PubMed, PMC or official corpus records were opened. This was not a systematic review. Consensus was quota-limited and Zotero local API access unavailable in the prior audit. No claim is made that all 40 original bibliography items were reverified in this migration.
