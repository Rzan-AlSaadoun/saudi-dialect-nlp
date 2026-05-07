# Saudi Dialect NLP: Classification and Translation with AraBERT and QLoRA

A Natural Language Processing project developed as part of CS365 at Imam Mohammad Ibn Saud Islamic University. The project addresses two tasks on the SauDial dataset: classifying Saudi Arabic regional dialects and translating dialect text into Modern Standard Arabic (MSA), comparing full fine-tuning baselines against QLoRA-optimized models.

---

## Project Overview

Saudi Arabic encompasses four major regional dialects — Najdi, Hijazi, Eastern, and Southern — each with distinct vocabulary and morphological patterns. This project investigates how pre-trained Arabic language models can be fine-tuned for these tasks and evaluates the impact of parameter-efficient optimization.

### Task 1: Dialect Classification
Fine-tuning AraBERT v02 to classify input text into one of four Saudi dialect categories.

### Task 2: Dialect-to-MSA Translation
Fine-tuning mT5-small to translate Saudi dialect text into Modern Standard Arabic, comparing full fine-tuning against QLoRA optimization.

---

## Dataset

**SauDial** — a specialized corpus of Saudi Arabic dialectal dialogue lines paired with MSA equivalents.

- ~800 samples after preprocessing
- Balanced across four dialect classes
- Source: SauDial: The Saudi Arabic Dialects Game Localization Dataset

The dataset is not included in this repository. Place the SauDial ZIP file in your Google Drive root before running the notebook.

---

## Models

| Task | Model | Optimization |
|---|---|---|
| Classification | aubmindlab/bert-base-arabertv02 | Full fine-tuning (baseline) |
| Classification | aubmindlab/bert-base-arabertv02 | QLoRA (4-bit, LoRA r=8) |
| Translation | google/mt5-small | Full fine-tuning (baseline) |
| Translation | google/mt5-small | QLoRA (4-bit, LoRA r=16) |

---

## Results

### Classification (AraBERT)

| Metric | Score |
|---|---|
| Accuracy | 0.85 |
| Macro F1 | 0.90 |

### Translation Quality Comparison (mT5-small)

| Metric | Baseline (Full Fine-Tuning) | Optimized (QLoRA) |
|---|---|---|
| BLEU | 0.0 | 0.775 |
| ROUGE-1 | 0.0 | 0.814 |
| ROUGE-2 | 0.0 | 0.758 |
| ROUGE-L | 0.0 | 0.813 |

### Efficiency Comparison

| Metric | Baseline | QLoRA |
|---|---|---|
| Trainable Parameters | 289,840,432 (100%) | 1,707,520 (0.589%) |

---

## Repository Structure
