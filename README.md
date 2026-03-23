# NLP Pipeline — Support Ticket Classification & Entity Extraction

## Overview
An NLP system that automatically classifies, prioritizes, and extracts information from customer support tickets. Progresses from classical ML baselines to transformer models with per-category evaluation rigor.

## Architecture
- **Classification Pipeline**: Multi-label classification (category + priority + sentiment)
  - Baseline: TF-IDF + Logistic Regression / SVM
  - Advanced: Fine-tuned DistilBERT with multi-task heads
- **Entity Extraction**: spaCy NER model trained to extract product names, error codes, and problem types
- **Evaluation**: Per-category precision/recall/F1 (a model that fails on critical categories is useless even with high global F1)
- **Processing**: Airflow DAG for daily batch processing of new tickets
- **Tracking**: MLflow logs per-category metrics, confusion matrices, and model artifacts

## Tech Stack
- Python 3.11+, scikit-learn
- Hugging Face Transformers (DistilBERT)
- spaCy (NER)
- MLflow (experiment tracking + model registry)
- Apache Airflow 2.x
- PostgreSQL
- Docker & Docker Compose

## What This Demonstrates
- Classical ML vs transformer comparison methodology
- Multi-task NLP (classification + NER in one pipeline)
- Per-category evaluation rigor
- Fine-tuning pretrained language models
- Named Entity Recognition for domain-specific entities
- Batch NLP processing at scale

## Status
🚧 In Development

## Project Structure
├── dags/
│   └── ticket_processing_dag.py
├── src/
│   ├── preprocessing/
│   ├── classification/
│   ├── ner/
│   └── evaluation/
├── data/
│   └── ner_annotations/
├── notebooks/
├── tests/
├── docker-compose.yml
└── README.md
