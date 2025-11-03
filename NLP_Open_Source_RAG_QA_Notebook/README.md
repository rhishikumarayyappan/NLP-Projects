# NLP Open Source RAG QA Notebook

## Overview

This project demonstrates a fully open-source **Retrieval-Augmented Generation (RAG) pipeline** for document-based question answering, optimized for free Google Colab T4 GPUs. It leverages quantized LLMs and lightweight embedding models for fast, cost-efficient natural language search over large document stores. The workflow is scalable, reproducible, and easy to adapt for new data sources.

**Stack:**
- Generator: `mistralai/Mistral-7B-Instruct-v0.2` (4-bit quantized)
- Retriever: `sentence-transformers/all-MiniLM-L6-v2`
- Vector Store: `faiss-cpu`
- Framework: `LangChain`
- Dataset: Sherlock Holmes (Project Gutenberg)
- Visualization: t-SNE

---

## Business Impact

- **Automated Answers:** Enterprise-ready QA from internal docs, reducing support overhead.
- **Knowledge Discovery:** Researchers get instant answers to domain-specific questions.
- **Customer Support:** Automates FAQ/helpdesk, reducing costs and improving response time.
- **Scalability:** Runs on free hardware (Colab T4), making it accessible for startups and academia.

---

## Metrics

| Metric                 | Value                         |
|------------------------|------------------------------|
| Answer Accuracy        | High (contextually grounded)  |
| Retrieval Precision    | Context from top-3 chunks     |
| Speed                  | 3.3 – 11.8 seconds per query  |
| Robustness             | PASSED (out-of-context test)  |
| Fidelity               | PASSED (answers from genuine context) |
| Chunk Count            | 580 text chunks               |
| Visualization Clusters | Semantic clusters visible     |

**Example Metrics:**
- **Standard question:** "Who was Irene Adler and what was her relationship with Sherlock Holmes?"
    - **Speed:** 5.35s
    - **Fidelity:** PASSED (answer grounded in 3 source chunks)
- **Another grounded question:** "Describe the events at the Red-Headed League."
    - **Speed:** 11.76s
    - **Fidelity:** PASSED (answer grounded in 3 source chunks)
- **Robustness test:** "What is Sherlock Holmes's opinion on machine learning?"
    - **Speed:** 3.31s
    - **Robustness:** PASSED (out-of-context correctly identified)

---

## Visualizations

t-SNE plot showing semantic clustering of document chunk embeddings:
<img width="1025" height="743" alt="t-SNE" src="https://github.com/user-attachments/assets/b2039513-7afb-4c76-b085-f8220817ce2d" />



_t-SNE plot shows semantic clusters. Tighter clusters mean the embedding model is effective at separating topics._

---

## Getting Started

1. **Install dependencies:**
pip install -r requirements.
2. **Run notebook:** Open `NLP_Open_Source_RAG_QA_Notebook.ipynb` in Google Colab or Jupyter.
3. **Test with Example Queries:** The notebook demonstrates QA and performance.

---

## License

This project is licensed under the MIT License.
