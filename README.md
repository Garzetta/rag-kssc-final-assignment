# rag-kssc-final-assignment
Final project for Kapita Selekta Sistem Cerdas: analysis of saturation and citation hallucination in Retrieval-Augmented Generation (RAG) on the Indonesian IDK-MRC dataset, across Top-K = 1, 3, 5, 10.

# Group members
- La Tania Nur Tenka (23/511404/PA/21787)*
- Raden Rara Garzetta Aleyda Harimurti (23/511422/PA/21793)*
- Leilani Fitria Salimah Hadiwibowo (23/511451/PA/21798)*

# Saturation & Hallucination Analysis in RAG

Final assignment for **Kapita Selekta Sistem Cerdas**.

We build a Retrieval-Augmented Generation (RAG) pipeline over the Indonesian
**IDK-MRC** dataset and study how performance changes as the number of retrieved
contexts **K** increases (K = 1, 3, 5, 10). For each K we measure answer quality
(ROUGE-L, BLEU, BERTScore), citation accuracy, retrieval recall, and the
hallucination rate on unanswerable questions.

## Pipeline
- **Dataset:** IDK-MRC (answerable + unanswerable questions)
- **Retriever:** multilingual-e5-base embeddings + FAISS (in-memory, cosine)
- **Generator:** Qwen2.5-3B-Instruct, 4-bit quantized (runs on a free Colab T4)

## Experiments
- **Experiment 1 — full paragraphs:** each document is a whole paragraph.
- **Experiment 2 — chunked:** paragraphs are split into ~45-word chunks, so
  retrieval is finer-grained and the saturation curve becomes visible.

## Contents
| File | Description |
|------|-------------|
| `Final_Assignment_KSSC_RAG_experiment_1.ipynb` | Full-paragraph experiment (executed, outputs included) |
| `Final_Assignment_KSSC_RAG_experiment_2_chunked.ipynb` | Chunked experiment (executed, outputs included) |
| `Report.pdf` | Report: Method, Results, Analysis & Discussion, Work Division |
| `metrics_summary.csv`, `plots.png` | Result tables and figures |

## How to run
Open a notebook in Google Colab → Runtime → T4 GPU → Run all.

## Work Division
- La Tania Nur Tenka (23/511404/PA/21787): Retrieval (Recall@K)
- Rr. Garzetta Aleyda Harimurti (23/511422/PA/21793): Generation & citation (Citation Accuracy)
- Leilani Fitria Salimah Hadiwibowo: Evaluation (Answer Quality + Hallucination)
