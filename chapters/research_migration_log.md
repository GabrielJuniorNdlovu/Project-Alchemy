# Definitive live BCI scope migration

Date: 2 November 2026. Authority: ../goal.md. User authorized the project-wide migration plan.

## Scope decision

The final intended system is a wearable eight-channel MI-BCI using the researcher's own repeated-session EEG for live Raspberry Pi 4 robotic-arm and computer interaction. Replay is intermediate. The experimental population is one participant. Public datasets are excluded from development/calibration/evaluation, while eligible literature remains usable.

The previous artifact-category and replay-led directions are superseded. Original assessments remain in backups/live-scope-20261102-142458/ and the existing chapters/archive directory; neither is an active scope authority.

## Preservation and document relationships

Before editing, Git showed an existing modification to chapters/chapter1.md and untracked references, sections and used_literature. A timestamped backup copied chapters, sections, references, literature, used_literature and README.md, including those uncommitted files. Its manifest contains SHA256 values. Validation found zero backup hash failures.

chapters/chapter1.md and chapter1.docx, the DCE template, original proposal, ref1.pdf and ref2.docx are unchanged against the backup. The pre-existing Git modification to chapter1.md was not created by this migration. No commit or push occurred.

sections/ is the canonical draft source. The section index records all new revisions as pending user review; nothing is automatically approved. The assembled chapter and Word file remain unsynchronized legacy copies, identified in the root and section indexes. Original references remain preserved. Their older statements are not active project requirements.

## File inventory

The following files were created or revised:
- goal.md
- AGENTS.md
- sections/1.4 Aim.md
- sections/1.1 Introduction.md
- sections/1.2 Background and Context.md
- sections/1.3 Problem Statement.md
- sections/1.5 Research Objectives.md
- sections/1.6 Scope and Limitations.md
- sections/1.7 Feasibility Study.md
- sections/1.8 Significance and Motivation.md
- sections/1.9 Work Plan.md
- sections/1.10 Conclusion.md
- README.md
- sections/README.md
- sections/1.0 Chapter Opening.md
- sections/alignment_guide.md
- chapters/research_viability.md
- chapters/chapter1_review.md
- chapters/chapter1_gap_analysis.md
- chapters/chapter1_literature_matrix.md
- literature/literature.md
- sections/References.md
- used_literature/citation_ledger.md
- used_literature/used_references.ris
- used_literature/historical_references.ris
- chapters/research_migration_log.md

A dated backup and manifest were also created. No existing archives or original references were deleted or rewritten.

## Section migration

1.1 introduces live wearable operation and previews the chapter. 1.2 supplies subject-specific acquisition and processing context. 1.3 separates the three experimental conditions and limits the research question to the participant. 1.4 removes replay as the defining Aim feature.

Existing later chapter material was corrected and mapped to the DCE template: four objectives (1.5), scope/limitations including ethics (1.6), feasibility and budget (1.7), significance (1.8), conditional work-plan chart (1.9), conclusion (1.10). Detailed methodological requirements are in goal.md and the alignment guide rather than a duplicate Chapter 1 methods section.

The DCE Word template's paragraph sequence was inspected; Word automatic numbering was not reproduced during this Markdown migration. The original proposal and Word chapter were inspected through paragraph extraction and contain superseded scope. ref1.pdf was preserved and not freshly text-extracted; no claim is made that its layout was audited.

## Literature audit

Tangermann (2012) and Pfurtscheller (2006) were removed from active citations and preserved as excluded historical records. Ma (2022) supports the narrower session-evaluation claim; Song (2022) supports small-channel MI and false-positive rejection. Detailed claims without a verified recent replacement were omitted rather than assigned a convenient reference.

The current RIS contains two records and two unique DOIs, matching the two current section citations and APA reference list. The original four-record RIS is preserved as historical_references.ris and in the backup. Banville remains a date-eligible historical candidate; current full-text access was blocked. Human verification remains pending. Named 2026 candidate metadata/methods are unresolved; no comprehensive novelty claim is made.

## Feasibility findings

The manufacturer lists PiEEG-8 at US$350, US$50 above the complete US$300 allowance before accessories, Pi, robot, shipping and import. Vendor stock could not be confirmed because the purchase page returned 403. Hardware specifications and safety limitations are linked in research_viability.md.

Ownership, complete quotations, institutional acceptance, ethics dates and enough usable recording sessions remain unconfirmed. No approved acquisition means no personal EEG; without personal EEG, empirical decoder/gate evaluation is blocked too. The 16-week chart is conditional and requires dates and resource decisions. Hardware choice must remain open until a complete acceptable system is established.

## Consistency audit

- Read back and compared all 23 core specification, section, reference and review files against the intended text: all matched. Every numbered section contains substantive text.
- Introduction body is 157 words, Background 517, Problem Statement 406; counts include hyphenated terms as single whitespace-delimited words. Heading-inclusive counts are 160, 525 and 410.
- The Aim is one sentence (42 body words). Four numbered project objectives appear in the specification and matching section.
- Active requirements preserve live acquisition, personal-data exclusivity, separate calibration/testing, exclusion of unfamiliar classes from novelty-gate training/calibration, separate degradation conditions and bounded control states.
- Independent robotic safeguards, rejected-command behaviour, stale commands and no-command limitations are explicit. No certified safety or completed experiment is asserted.
- Assertions of public-data experiments, artifact-category objectives and replay-only completion remain only in preserved historical files or explicit exclusions, not current requirements.
- Session dependence, one-participant generalization limits and undefined selective error at zero acceptance are explicit.
- Word generation and actual pagination were deferred by agreement. No fewer-than-20-page claim is asserted for the current Word snapshot.

## Open decisions and next step

Review the revised Aim and Sections 1.1–1.4, then review Section 1.5's four migrated objectives. Before freezing the acquisition protocol, resolve equipment access/budget, ethics and safety pathway, montage, session/trial justification, calibration scheme, comparison operating points and interaction mapping. The exact comparative novelty and acceptability of a single-participant contribution require further original-source review and supervisor judgment.

## Subsequent budget correction — 2 November 2026

The researcher subsequently reported PiEEG-8 at US$100 and confirmed that the complete setup, including all equipment, accessories, delivery and import costs, fits within US$200. This supersedes the financial shortfall assessment above; that assessment is retained as migration history.

Section 1.7 now presents four separate feasibility dimensions and economic feasibility based on the researcher's costing. No independently verified quotation, completed integration, approval or validated completion date is asserted. Synchronized current statements in goal.md, README.md, chapters/research_viability.md, chapters/chapter1_review.md, sections/README.md and the budget sentence in sections/1.10 Conclusion.md. The assembled chapter remains unchanged pending section approval. Procurement records, technical validation and the approval/scheduling requirements remain distinct from the supplied budget confirmation.
