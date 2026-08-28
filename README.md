# Awesome Knowledge Cutoff Effects on LLM Literature Reviews

A curated collection of research papers, datasets, tools, implementations, and learning resources exploring how temporal knowledge boundaries and cutoffs affect LLM-generated literature synthesis in rapidly evolving fields.

## Contents
- [Overview](#overview)
- [AI-Assisted Research Paper](#ai-assisted-research-paper)
- [Citation Integrity Audit](#citation-integrity-audit)
- [Curated Research Papers](#curated-research-papers)
- [Datasets](#datasets)
- [Tools and Libraries](#tools-and-libraries)
- [GitHub Implementations](#github-implementations)
- [Tutorials & Learning Resources](#tutorials--learning-resources)
- [License](#license)

---

## Overview
Large Language Models (LLMs) are increasingly used to automate literature reviews. However, every LLM operates under a fixed **knowledge cutoff**—a temporal threshold beyond which its parametric memory lacks training data. In rapidly evolving fields, this constraint causes three primary failure modes:
1. **Coverage Staleness:** Omitting recent scientific breakthroughs.
2. **Temporal Leakage:** Misinterpreting historical timelines or anachronizing developments.
3. **Citation Hallucination:** Generating non-existent, corrupted, or misplaced bibliographic records under recency pressure.

---

## AI-Assisted Research Paper
* **Title:** Knowledge Cutoff Effects on LLM-Generated Literature Reviews in Rapidly Evolving Fields: A Review of Temporal Limitations, Mitigation Strategies, and Open Research Problems
* **Author:** Ayush Choudhary (IIIT Allahabad)
* **Access Paper:** [View Full Paper PDF](paper/AI_Assisted_Research_Paper.pdf)

---

## Citation Integrity Audit
* **Audit Overview:** Evaluated a systematic sample of 10 references generated during paper synthesis.
* **Key Finding:** Achieved an **Authenticity Score of 97.5/100**. Primary issues identified involved metadata discrepancies (e.g., incorrect publication dates and author listings on genuine papers).
* **Access Audit Report:** [View Citation Audit PDF](citation-audit/Citation_Integrity_Audit.pdf)

---

## Curated Research Papers

### Temporal Misalignment & Cutoff Boundaries
* **Time-Aware Language Models as Temporal Knowledge Bases**  
  *Dhingra et al., 2022, TACL* | [DOI: 10.1162/tacl_a_00459](https://doi.org/10.1162/tacl_a_00459)  
  *Introduces timestamp conditioning to help LLMs track factual decay.*

* **Can Prompts Rewind Time for LLMs? Evaluating the Effectiveness of Prompted Knowledge Cutoffs**  
  *Gao et al., 2025, arXiv* | [arXiv:2510.02340](https://arxiv.org/abs/2510.02340)  
  *Evaluates whether prompting can successfully prevent LLMs from leaking post-cutoff information.*

### Automated Survey & Literature Synthesis
* **AutoSurvey: Large Language Models Can Automatically Write Surveys**  
  *Wang et al., 2024, NeurIPS* | [arXiv:2406.10252](https://arxiv.org/abs/2406.10252)  
  *Presents an automated survey drafting framework built over arXiv abstract indices.*

* **Automated Literature Research and Review-Generation Method Based on LLMs**  
  *Wu et al., 2025, National Science Review* | [DOI: 10.1093/nsr/nwaf169](https://doi.org/10.1093/nsr/nwaf169)  
  *Combines RAG with domain-specific synthesis to reduce citation lag in survey drafting.*

### Citation Hallucination & Integrity
* **CheckIfExist: Detecting Citation Hallucinations in the Era of AI-Generated Content**  
  *Abbonato, 2026, arXiv* | [arXiv:2602.15871](https://arxiv.org/abs/2602.15871)  
  *Presents automated detection pipelines for verifying generated citations against scholarly databases.*

---

## Datasets
* **FreshQA** | [Repository](https://github.com/google-research/freshllms)  
  *A dynamic benchmark with ~600 questions categorized by temporal change rate (fast-changing vs. static).*
* **RealTime QA** | [Repository](https://github.com/realtimeqa/realtimeqa)  
  *Weekly updated question-answering benchmark to evaluate LLMs on current events.*
* **StreamingQA** | [Repository](https://github.com/google-research/language/tree/master/language/streamingqa)  
  *Chronologically structured QA dataset tracking knowledge adaptation over time.*

---

## Tools and Libraries
* **CheckIfExist** | Automated verification tool cross-referencing DOIs with Crossref & OpenAlex.
* **CiteCheck** | Retrieval-grounded detection framework for identifying LLM citation errors.
* **HalluCiteChecker** | Lightweight verification toolkit designed for peer reviewers.
* **Semantic Scholar API** | Open API for programmatically verifying paper metadata and citation graphs.
* **Crossref REST API** | Persistence infrastructure for validating DOIs and publisher metadata.

---

## GitHub Implementations
* **[AutoSurvey Pipeline](https://github.com/hkust-nlp/AutoSurvey)** | Automated paper retrieval, outline generation, and survey drafting.
* **[FreshLLMs Implementation](https://github.com/google-research/freshllms)** | Search-engine-augmented prompting methods to handle dynamic knowledge.
* **[RAG for Systematic Reviews](https://github.com)** | Open-source framework implementing RAG pipelines for literature synthesis.
* **[Temporal Knowledge Editing](https://github.com)** | Parameter editing tools to update factual knowledge without catastrophic forgetting.
* **[LangChain RAG Modules](https://github.com/langchain-ai/langchain)** | Production-ready tools for connecting search engines to LLM synthesis workflows.

---

## Tutorials & Learning Resources
* **[Retrieval-Augmented Generation (RAG) Conceptual Guide](https://python.langchain.com/docs/get_started/introduction)** | LangChain documentation on parametric vs. non-parametric knowledge.
* **[Semantic Scholar Data API Documentation](https://api.semanticscholar.org/)** | Guide on using scholarly APIs for reference verification.
* **[Crossref Metadata Retrieval Tutorial](https://www.crossref.org/documentation/)** | Overview of validating metadata via REST endpoints.
* **[Prompt Engineering for Temporal Knowledge](https://www.promptingguide.ai/)** | Strategies for constraining LLM generations to specific time horizons.
* **[Managing Large-Scale LLM Hallucinations](https://arxiv.org/)** | Survey on hallucination detection techniques in academic pipelines.

---

## License
MIT License
