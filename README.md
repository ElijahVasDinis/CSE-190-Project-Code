# Register Shift in Grounded QA

This repository contains the code and data used for the experiments in the paper:

**“Same Evidence, Different Register: The Effect of Register Shift on Correctness and Abstention in Grounded LLM Question Answering.”**

---

## Files

- `mainExperiment.ipynb`  
  Main notebook used to run the experiments, generate model outputs, and compute evaluation metrics.

- `confiqa_register_eval_cleaned.csv`  
  Evaluation dataset containing grounded QA examples with three register variants (formal, neutral, informal).

---

## Overview

This project studies how changing the **register of a question** (formal, neutral, informal) affects the performance of a large language model in a grounded question answering setting.

The experiment:
- Uses a derived dataset based on ConFiQA
- Expands each example into three register variants
- Evaluates **FLAN-T5-base** under a fixed prompting setup
- Measures:
  - Exact correctness
  - Lenient correctness
  - Abstention rate (“insufficient evidence”)

---

## How to Run

1. Open the notebook:
   `register_shift_grounded_qa_experiment_clean.ipynb`

2. Run all cells in order.

3. The notebook will:
   - Load the dataset
   - Run model inference
   - Compute evaluation metrics
   - Output results used in the paper

---

## Requirements

- Python 3.x
- pandas
- transformers (Hugging Face)
- torch

If running in Google Colab, install dependencies with:

```python
!pip install pandas transformers torch
```

---

## Notes

- The dataset contains **150 base examples expanded to 450 prompts** across three register conditions.
- All experiments were run with **greedy decoding**.
- The model is instructed to answer using only the provided context or abstain with “insufficient evidence”.

