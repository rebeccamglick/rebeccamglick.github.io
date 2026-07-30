# Projects

## Technical Assessment: Hybrid RAG System from Scratch
**2026**

Built a retrieval-augmented generation system from scratch as a timed technical assessment, implementing hybrid retrieval combining BM25 and semantic search via Reciprocal Rank Fusion (RRF), backed by a custom NumPy vector store. Added a hallucination detection layer and a PII short-circuit to block retrieval/generation on sensitive queries. Empirically profiled embedding similarity scores (mistral-embed) to calibrate a retrieval confidence threshold, deliberately biasing the system toward refusal over hallucination when confidence was low.

**Results:** Delivered a working end-to-end hybrid retrieval pipeline with a calibrated 0.70 similarity threshold, favoring "I don't know" responses over fabricated answers when retrieval confidence was insufficient.

**Tools:** Python, BM25, semantic search, Reciprocal Rank Fusion (RRF), NumPy (custom vector store), FastAPI, mistral-embed

**Repo:** [rag-assessment-stackai](https://github.com/rmglick/rag-assessment-stackai)

---

## Active Learning for Rare-Class Text Classification (LLM-as-an-Oracle)
**Jan. 2026 – May 2026**

Extended an active learning pipeline to improve rare-class detection across large-scale, multi-class text classification datasets, combining an iterative LLM-labeling loop, bandit-driven sample selection, and model retraining to reduce annotation costs. Built distributed, GPU-based experimentation infrastructure on Kubernetes to support scalable human-in-the-loop and autonomous evaluation workflows, and developed configurable dataset adapters and automated hyperparameter tuning to improve reproducibility and portability across new domains.

**Results:** Achieved a 0.94 F1 score on rare-class detection while meaningfully reducing manual annotation costs.

**Tools:** Python, PyTorch, Thompson sampling (bandit-based sample selection), LDA clustering, BERT fine-tuning, GPT-4o-mini (LLM-as-oracle pseudo-labeling), Kubernetes, Docker

**Paper:** *[Active Learning Report](papers/LTS_Project.pdf)*

---

## Capstone Project: Assessing Hiring Gender Bias in LLMs
**Sept. 2025 – Dec. 2025** *(a.k.a. "Project Azalea")*

Designed controlled ranking experiments to evaluate demographic parity and consistency in LLM-driven resume ranking under gender-swapped and gender-null prompt conditions. Used Borda count rank-aggregation to combine 50 repeated stochastic rankings per candidate into a stable score, then applied rank-difference statistics to compare outcomes across models and industries.

**Results:** Found small (0–2 rank position) but directionally consistent shifts — removing or switching gender information tended to raise women's average rank slightly and lower men's, with effects more pronounced in fields with stronger existing gender stereotypes (e.g., a 0.6–1 position swing in Healthcare vs. under 0.25 in Computer Software). Claude 4.5-Haiku showed more sensitivity and variability to gender manipulation than GPT-5. Framed as a proof-of-concept bias signal rather than a statistically validated claim, given sample size.

**Tools:** GPT-5, Claude 4.5-Haiku, Python, Borda count rank aggregation, rank-difference statistical analysis

**Paper:** *[Capstone LLM Assessment Report](papers/Capstone_Report.pdf)*

---

## Agentic RAG: Medical Knowledge Graph Integration
**Jan. 2025 – May 2025**

Built a GraphRAG-based AI agent integrating a medical knowledge graph with retrieval-augmented generation to answer healthcare questions, benchmarked against a standard vector-store RAG baseline. Optimized graph queries, retrieval tuning, and prompt engineering to improve accuracy while reducing system latency.

**Results:** Outperformed vector-store RAG baseline on the healthcare QA benchmark, with improved accuracy and reduced latency after tuning.

**Tools:** LangChain, LLaMA 3.2, Neo4j, Cypher, FAISS

**Paper:** *[RAG System Report](papers/KG_RAG_Report.pdf)*

---

## Statistical Analysis and Predictive Modeling of Bias in Higher Education Ratings
**Dec. 2024**

Conducted statistical significance testing (Welch's t-test, KS-test) with confidence intervals and bootstrapping to assess gender bias in higher education ratings data, controlling for confounding variables. Built predictive regression and classification models to further characterize the bias signal.

**Results:** Identified statistically significant rating disparities; optimized predictive models on AUROC, R², and RMSE while addressing collinearity and class imbalance.

**Tools:** Python, hypothesis testing (Welch's t-test, KS-test), bootstrapping, regression and classification modeling

---

## Reinforcement Learning: Qwen2.5-0.5B and Process vs. Outcome Rewards
**Sept. 2025 – Dec. 2025**

Fine-tuned Qwen2.5-0.5B using reinforcement learning to benchmark process-based versus outcome-based reward regimes on mathematical reasoning tasks. Analyzed reasoning trajectories and convergence behavior to surface findings on reward design tradeoffs.

**Results:** Documented convergence performance and reward-design tradeoffs between process- and outcome-based regimes in a technical write-up.

**Tools:** Qwen2.5-0.5B, RL fine-tuning frameworks, Python

**Technical Blog Post:** [RLVR and Qwen2.5-0.5B: Local vs. Meta Rewards](https://quill-reptile-5db.notion.site/RLVR-and-Qwen2-5-0-5B-Local-vs-Meta-Rewards-2c17b396b0088095a4dfc4e4ca9e31a7)

---

## Recommender System Development
**Jan. 2026 – May 2026** *(Big Data Capstone)*

Designed a collaborative filtering model on the MovieLens dataset using Spark, applying Bayesian smoothing to handle rating sparsity at scale. Wrote the distributed data partitioning and preprocessing pipeline (Spark, Parquet), resolving data reliability issues via stratified sampling.

**Results:** Delivered a scalable collaborative filtering recommender with improved handling of sparse rating data through Bayesian smoothing.

**Tools:** Spark, Parquet, collaborative filtering, Bayesian smoothing, stratified sampling

**Paper:** [Recommender System Report](papers/Big_Data_Capstone.pdf)

---

## Deep Learning – Self-Supervised Learning: MoCo v2 Representation Learning
**Fall 2025**

Built a MoCo v2-style contrastive self-supervised learning framework on a ResNet-50 backbone to learn visual representations from ~500K unlabeled images, evaluated via frozen-backbone linear probing across three held-out test sets. Diagnosed and resolved a training collapse failure mode in an initial DINOv2-style distillation approach — tracing it to a mismatch between ResNet's inductive biases and self-distillation objectives (ResNet backbones make augmented views too similar too early, starving self-distillation of signal) — and pivoted to the more stable MoCo-based method under compute and time constraints.

**Results:** Identified that contrastive loss alone was an unreliable predictor of downstream representation quality, informing a more rigorous, evaluation-driven iteration process; successfully diagnosed and resolved training collapse under real constraints.

**Tools:** PyTorch, ResNet-50, MoCo v2, InfoNCE loss, 65K negative queue, contrastive learning, linear probing

**Paper:** [Deep Learning Unsupervised Learning Report](papers/Deep_Learning_Final_Project.pdf)
