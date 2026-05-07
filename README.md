# Saudi Dialect NLP

This project was made for the NLP course (CS365) at IMSIU. It works on Saudi Arabic dialects using two tasks: classifying which dialect a sentence belongs to, and translating dialect text into Modern Standard Arabic (MSA). We compare a normal fine-tuned model against an optimised one using QLoRA.

---

## What This Project Does

Saudi Arabic has four main regional dialects: Najdi, Hijazi, Eastern, and Southern. We trained models to:

1. **Classify** a sentence into one of the four dialects using AraBERT
2. **Translate** dialect sentences into MSA using mT5-small

For both tasks, we built a baseline model first, then applied QLoRA to see how much we can improve efficiency and performance.

---

## Dataset

We used the **SauDial dataset**, which contains short Saudi dialect sentences paired with their MSA translations. After cleaning, we had around 800 samples split as follows:

- 80% for training
- 10% for validation
- 10% for testing

The dataset is not included here. Download it and place the ZIP file in your Google Drive root before running the notebook.

---

## How to Run

1. Open the notebook in Google Colab
2. Make sure your runtime is set to GPU (Runtime > Change runtime type > GPU)
3. Upload the SauDial ZIP to your Google Drive
4. Run all cells from top to bottom — the notebook installs everything it needs automatically

---

## Results

### Dialect Classification (AraBERT)
- Accuracy: 0.85
- F1 Score: 0.90

### Translation (mT5-small)

| Metric | Baseline | QLoRA |
|---|---|---|
| BLEU | 0.0 | 0.775 |
| ROUGE-1 | 0.0 | 0.814 |
| ROUGE-2 | 0.0 | 0.758 |
| ROUGE-L | 0.0 | 0.813 |

QLoRA also reduced trainable parameters from 289M (100%) down to 1.7M (0.589%).

---

## Authors

Munera Alzamil, Shatha Alharbi, Rzan AlSaadoun, Fatima Aldukkan

CS365 — Natural Language Processing | Dr. Amal AlSaif | IMSIU
