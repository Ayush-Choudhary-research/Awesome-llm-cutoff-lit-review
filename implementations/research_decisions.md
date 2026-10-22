# Research Decisions Log

This log tracks decisions for converting the review into an implementation-based
research paper. **VERIFIED** means directly observed in a current project file;
it does not mean independently confirmed against the cited publication.
**INFERRED** marks a reasoned but unconfirmed interpretation. **UNKNOWN** marks
information still needed.

## Current Stage

Stage 1 — Review scope and candidate gaps. `prism-uploads/main.tex` and
`prism-uploads/references.bib` are the canonical working sources. The root-level
`main.tex` and `references.bib` are no longer present. No research question,
dataset, model, or baseline has been selected.

## Source Inventory

- `prism-uploads/main.tex` — **VERIFIED**: narrative review titled “Knowledge
  Cutoff Effects on LLM-Generated Literature Reviews in Rapidly Evolving
  Fields.” It covers background, thematic discussion, mitigation approaches,
  limitations, proposed gaps, and a conclusion; it does not define an
  implementation experiment.
- `prism-uploads/references.bib` — **VERIFIED**: 30 BibTeX records. All
  explicit citation keys in the TeX file match bibliography records. The source
  uses `\nocite{*}`, which includes records even if they are not explicitly
  cited in the body.
- Root-level `main.tex` and `references.bib` — **VERIFIED**: absent from the
  current project file listing.
- `prism-uploads/ACM_Formated_literature_paper.pdf` — **VERIFIED**: absent from
  the current project file listing; no PDF comparison is available in this
  pass.

## Scope Summary

- **VERIFIED**: The review concerns knowledge-cutoff effects on LLM-generated
  literature reviews in rapidly evolving fields.
- **VERIFIED**: It organizes the problem around coverage staleness,
  cutoff-boundary/forgetting failures, and fabricated or corrupted citations.
- **VERIFIED**: It discusses retrieval-augmented generation, knowledge editing,
  and citation-verification tooling as mitigations.
- **VERIFIED**: It proposes six candidate directions: temporal-freshness
  metrics, longitudinal benchmarks, testing ex-ante reasoning in review
  generation, joint RAG/editing, discipline-specific verification, and
  editorial norms.
- **INFERRED**: One direction may be operationalized as an experiment, but the
  manuscript alone does not establish novelty or feasibility.

## Decisions

### D-001 — Keep candidate gaps provisional

- **Decision**: Do not yet select a research question, dataset, model, or
  baseline.
- **Reason**: **VERIFIED**: The manuscript proposes multiple broad directions
  but defines no experimental protocol, dataset, operational outcome, or
  project constraints.
- **Source/evidence**: “Research Challenges and Limitations” and “Research
  Gaps and Future Directions” in `prism-uploads/main.tex`.
- **Next action**: Verify the most important claims against primary sources;
  then map one supported gap to a feasible experiment.

### D-002 — Use the surviving uploaded source pair

- **Decision**: Use `prism-uploads/main.tex` and
  `prism-uploads/references.bib` as the canonical pair, per the user's latest
  instruction.
- **Reason**: **VERIFIED**: These are the current TeX and bibliography files;
  the earlier root-level pair is absent.
- **Source/evidence**: Current project file listing.
- **Next action**: Keep future analysis and edits on this pair unless the user
  specifies another source.

### D-003 — Resolve prose attributions before treating claims as evidenced

- **Decision**: Treat author-year claims written as plain prose as unresolved
  until each is matched to a source and checked.
- **Reason**: **VERIFIED**: The text includes TODOs for “Algaba et al. (2026),”
  “Agrawal et al. (2024),” and “Xu et al. (2026).” The bibliography includes
  anonymous-author records, but their identity and relevance cannot be assumed
  from the entry alone.
- **Source/evidence**: Introduction and “Citation and Reference Hallucination”
  in `prism-uploads/main.tex`; `prism-uploads/references.bib`.
- **Next action**: Locate and verify the original sources; connect each claim
  to the correct bibliographic record only after matching evidence.

### D-004 — Audit unused bibliography records

- **Decision**: Do not treat every bibliography entry as evidence used by the
  review's argument.
- **Reason**: **VERIFIED**: Ten records lack explicit citation keys in the
  body, while `\nocite{*}` includes all records: `anon2026bibtex`,
  `anon2026citecheck`, `anon2026constrained`, `anon2026exante`,
  `anon2026hallucitechecker`, `anon2026misconduct`, `anon2026neurons`,
  `anon2026wild`, `mechanistic2026`, and `reasons2024`.
- **Source/evidence**: Citation-key comparison of the two canonical files.
- **Next action**: Determine which works support the argument; cite in context
  or remove unrelated entries if appropriate.

### D-005 — Add verified identifiers and landing links

- **Decision**: Add DOI and/or URL fields to the four supplied bibliography
  records after checking titles and identifiers against publisher or primary
  repository records.
- **Reason**: **VERIFIED** on 2026-10-22: the Alkaissi and McFarlane title and
  DOI match the Cureus record; StreamingQA's title and arXiv identifier match
  the arXiv record and its ICML/PMLR publication; the Tang et al. title and
  DOI match ACL Anthology record `2025.emnlp-main.83`; and the AutoSurvey title
  and supplied DOI match its arXiv version. The official NeurIPS proceedings
  record lists a different DOI (`10.52202/079017-3655`), which is recorded in
  the BibTeX note alongside the supplied arXiv DOI. These checks verify
  bibliographic identity, not every claim made about the papers in the review.
- **Source/evidence**: `prism-uploads/references.bib` entries `alkaissi2023`,
  `liska2022`, `tang2025`, and `wang2024`; official Cureus, PMLR, ACL
  Anthology, and NeurIPS records; arXiv record `2205.11388`.
- **Next action**: Keep this identifier check separate from the remaining
  source audit; verify each manuscript claim against the relevant paper before
  treating it as evidence.

### D-006 — Add resolver URLs for every DOI

- **Decision**: Ensure every BibTeX record with a `doi` field also has a
  direct DOI-resolver `url` field.
- **Reason**: **VERIFIED**: A scan found five DOI-bearing records without URLs;
  DOI-resolver URLs have now been added for `anon2026misconduct`, `cohen2024`,
  `dhingra2022`, `luu2022`, and `wu2025`. The existing DOI-bearing records
  also have URL fields. This adds access links but does not independently
  validate all DOI metadata.
- **Source/evidence**: `prism-uploads/references.bib`; DOI and URL field scan.
- **Next action**: Recheck any DOI/title pair whose metadata is disputed or
  corrected during the claim-level source audit.

### D-007 — Provide a separate ACM manuscript-format TeX source

- **Decision**: Create `prism-uploads/ACM_Formated_literature_paper.tex` from
  the canonical review source, using the ACM `acmart` manuscript/review format with `manuscript`, `screen`, `review`, and `anonymous` options.
- **Reason**: **VERIFIED**: The ACM class is installed locally. The source uses
  anonymous review mode and omits venue-specific publication metadata because
  no ACM venue, author identity, or publication DOI was supplied. Its
  bibliography path remains relative to `prism-uploads/`.
- **Source/evidence**: `prism-uploads/main.tex`, `prism-uploads/references.bib`,
  and the ACM `acmart` template guidance.
- **Build check**: **VERIFIED** on 2026-10-22: `pdflatex` and BibTeX completed successfully using the ACM source and `prism-uploads/references.bib`. After the final LaTeX pass, there are no LaTeX warnings, errors, undefined citations, or undefined references. BibTeX still emits 19 warnings for incomplete publication metadata (such as volume, pages, publisher, address, or author) in existing records. Build artifacts were kept outside the workspace.
- **Next action**: Verify and fill missing metadata only from primary records; do not infer it.

### D-008 — Add provisional ACM CCS descriptors

- **Decision**: Add `Computing methodologies~Natural language generation` and
  `Information systems~Information retrieval` to the ACM TeX draft.
- **Status**: **INFERRED**: These topics match the review generation and
  retrieval focus; the user has not confirmed this ACM CCS categorization.
- **Reason**: The initial `acmart` build warned that CCS concepts are mandatory
  for a paper longer than two pages. ACM submission guidance requires CCS
  concepts for full-length manuscripts.
- **Source/evidence**: `prism-uploads/ACM_Formated_literature_paper.tex` and ACM
  submission-template guidance.
- **Next action**: Confirm or adjust the classifications before submission.

## Evidence Still Needed

- **UNKNOWN**: Independent verification of bibliography metadata and manuscript
  claims against the cited publications.
- **UNKNOWN**: Intended field/corpus, available compute and model/API access,
  project timeline, and data-access or institutional constraints.
- **UNKNOWN**: Whether the study should prioritize freshness, citation
  reliability, cutoff leakage, or another outcome.

## Next Actions

1. Audit high-impact claims and unresolved attributions against primary
   sources; record exactly what each source supports.
2. Choose one gap after this audit and after project constraints are known.
3. Define the task, corpus, baseline, and outcomes before coding.
