* **FreshQA**
  * **Description:** A dynamic benchmark dataset designed to evaluate language model performance on rapidly changing facts and static knowledge.
  * **Key Features:** Features ~600 questions divided into fast-changing, slow-changing, and static knowledge categories to test recency and temporal robustness.
  * **Primary Use Case:** Assessing how well search-augmented or RAG-based systems handle post-cutoff information retrieval.
  * **Repository / Link:** [https://github.com/freshllms/freshqa](https://github.com/freshllms/freshqa)

* **RealTime QA**
  * **Description:** A dynamic question-answering benchmark updated on a weekly basis using recent news articles and current events.
  * **Key Features:** Evaluates LLMs on instantaneous real-world facts without allowing parametric memorization.
  * **Primary Use Case:** Probing temporal adaptation, zero-shot recency capabilities, and live retrieval pipelines.
  * **Repository / Link:** [https://github.com/realtimeqa/realtimeqa_public](https://github.com/realtimeqa/realtimeqa_public)

* **StreamingQA**
  * **Description:** A chronologically structured QA dataset tracking knowledge adaptation and temporal drift over extended time horizons.
  * **Key Features:** Consists of time-stamped news articles and questions to measure how models update or forget facts as time progresses.
  * **Primary Use Case:** Benchmarking continual learning, temporal knowledge editing, and long-term memory maintenance.
  * **Repository / Link:** [https://github.com/google-deepmind/streamingqa](https://github.com/google-deepmind/streamingqa)

* **REASONS Dataset**
  * **Description:** A benchmark dataset built for evaluating fine-grained attribution, claim verification, and citation entailment in scientific writing.
  * **Key Features:** Maps inline research claims directly to supporting source passages to isolate hallucinated vs. grounded statements.
  * **Primary Use Case:** Evaluating citation verification tools and automated peer-review auditing systems.
  * **Repository / Link:** [https://arxiv.org/abs/2405.02228](https://arxiv.org/abs/2405.02228)

* **AToKe (Automated Temporal Knowledge Editing Benchmark)**
  * **Description:** A dataset specialized in evaluating sequential and continuous knowledge edits over temporal constraints.
  * **Key Features:** Includes pairs of pre-cutoff and post-cutoff state changes to test if editing new facts corrupts related historical knowledge.
  * **Primary Use Case:** Testing model editing methods and measuring parametric consistency after adding post-cutoff updates.
  * **Repository / Link:** [https://arxiv.org/abs/2312.05497](https://arxiv.org/abs/2312.05497)
