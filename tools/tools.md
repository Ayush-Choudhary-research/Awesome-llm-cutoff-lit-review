* **CheckIfExist**
  * **Category:** Citation Verification & Hallucination Detection
  * **Description:** An automated pipeline that cross-references AI-generated bibliographic entries against Crossref, Semantic Scholar, and OpenAlex APIs to flag fabricated papers.
  * **Key Functionality:** Validates DOIs, title similarity scores, and author metadata to calculate paper authenticity metrics.
  * **Primary Use Case:** Auditing generated literature reviews for non-existent citations before publication.

* **CiteCheck**
  * **Category:** Retrieval-Grounded Hallucination Detection
  * **Description:** A retrieval-augmented verification framework designed to evaluate claim-source entailment and detect metadata corruption in scientific prose.
  * **Key Functionality:** Extracts inline citations, retrieves the underlying full-text source, and checks whether the cited passage actually supports the claim.
  * **Primary Use Case:** Automated peer-reviewing and factual consistency checking in AI-assisted academic writing.

* **HalluCiteChecker**
  * **Category:** Lightweight Verification Toolkit
  * **Description:** A fast, open-source toolkit tailored for researchers and reviewers to screen manuscripts for hallucinated references.
  * **Key Functionality:** Offers lightweight Python scripts and command-line interfaces for quick batch-checking of `.bib` and `.md` reference files.
  * **Primary Use Case:** Rapid pre-submission citation auditing for academic manuscripts.

* **Semantic Scholar Graph API**
  * **Category:** Open Scholarly Data Infrastructure
  * **Description:** RESTful API providing programmatic access to metadata, citation graphs, and abstract embeddings for over 200 million academic papers.
  * **Key Functionality:** Enables real-time verification of author lists, publication years, venue details, and paper existence.
  * **Primary Use Case:** Serving as the non-parametric knowledge backbone for literature synthesis and verification tools.

* **Crossref REST API**
  * **Category:** DOI & Metadata Validation Service
  * **Description:** Persistent infrastructure API used to query official publisher metadata associated with Digital Object Identifiers (DOIs).
  * **Key Functionality:** Performs exact DOI lookups and validates publication dates, journal names, and registered persistent links.
  * **Primary Use Case:** Confirming DOI validity and resolving citation metadata discrepancies in generated bibliographies.
