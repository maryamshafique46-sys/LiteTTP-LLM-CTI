# LiteTTP-LLM

LiteTTP-LLM is a lightweight research prototype for extracting MITRE ATT&CK Techniques, Tactics, and Procedures (TTPs) from Cyber Threat Intelligence (CTI) reports under resource-constrained environments. The project explores whether simple machine learning models and optimized zero-shot large language models can provide useful CTI insights without relying on heavy transformer fine-tuning.

This repository accompanies the research paper:

**“LiteTTP-LLM: A Lightweight Multi-Label and Zero-Shot LLM Pipeline for ATT&CK-Aligned CTI Extraction”**

---

## 1. Problem Statement

Cyber Threat Intelligence reports are typically written as unstructured natural language text, making it difficult for security analysts to manually identify and map attacker behaviors to the MITRE ATT&CK framework. Existing solutions often rely on large, fine-tuned transformer models that require significant computational resources, which are not always available in academic labs or small organizations.

This project investigates whether lightweight alternatives can still produce meaningful and actionable results for CTI-to-ATT&CK mapping.

---

## 2. Project Overview

The work is based on the TTPXHunter framework and introduces two lightweight improvements:

### Improvement 1: Multi-Label Machine Learning Baseline
- TF-IDF feature extraction
- Logistic Regression classifier
- Multi-label formulation allowing one sentence to be mapped to multiple ATT&CK techniques
- Designed for low compute environments (CPU / Google Colab)

### Improvement 2: Optimized Zero-Shot LLM
- Zero-shot classification using BART-large-MNLI
- Natural Language Inference (NLI) formulation
- Contextualized ATT&CK technique descriptions
- Hyperparameter tuning to balance precision and recall

---

## 3. Dataset

The experiments use a publicly available MITRE ATT&CK-aligned CTI dataset.  
Each sentence is mapped to one or more ATT&CK technique identifiers.

To ensure feasibility in limited environments, a subset of approximately 7,000 samples is used for training and evaluation.

---

## 4. Repository Structure

LiteTTP-LLM/
├── README.md
├── requirements.txt
│
├── notebooks/
│ ├── data_preprocessing.ipynb
│ ├── multilabel_baseline.ipynb
│ └── zero_shot_llm.ipynb
│
├── data/
│ └── sample_data.csv

---

## 5. How to Run the Code

1. Clone the repository:
```bash
git clone https://github.com/maryamshafique46-sys/LiteTTP-LLM-CTI.git
cd LiteTTP-LLM-CTI

pip install -r requirements.txt

Run the notebooks in the following order:

data_preprocessing.ipynb

multilabel_baseline.ipynb

zero_shot_llm.ipynb
