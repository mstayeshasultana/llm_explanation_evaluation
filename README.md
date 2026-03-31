# EuroSAT LLM Explanation Evaluation


**"Evaluating LLM-Generated Natural Language Explanations for Deep 
Learning-Based Satellite Image Land Use Classification"**

University of Turku | Robotics and Autonomous Systems | 2026

---

## Overview

This study evaluates whether LLM-generated natural language explanations 
for satellite image land use classification improve when XAI-derived visual 
information is provided as context, compared to asking the LLM to describe 
images directly without any guidance.

---

## Dataset

- **EuroSAT** — Sentinel-2 satellite imagery
- 6 land use classes: Annual Crop, Forest, Highway, Industrial, 
  Residential, River
- 20 images per class — 120 images total

---

## Model

- **ResNet50** pretrained on ImageNet
- Fine-tuned on EuroSAT
- Validation accuracy: **97.9%**

---

## Experiments

### Experiment 1: XAI-Informed LLM Descriptions
- GradCAM identifies important regions in satellite images
- Region descriptions fed to GPT-4o as context
- **Result: 98.3% accuracy**

### Experiment 2: Direct LLM Image Descriptions
- Satellite image sent directly to GPT-4o
- No XAI guidance provided
- **Result: 75.0% accuracy**

### Experiment 3: Deletion Test
- Important regions identified by GradCAM are masked
- Model confidence measured before and after masking
- **Result: 67.4% average confidence drop**

---

## Key Findings

| Metric | Value |
|--------|-------|
| XAI-Informed Accuracy | 98.3% |
| Direct Description Accuracy | 75.0% |
| Improvement from XAI | +23.3% |
| Avg Confidence Drop | 67.4% |

---

## Repository Structure
```
├── eurosat_llm_explanation_evaluation.ipynb  # Main experiment notebook
├── README.md                                  # This file
```

---

## Requirements
```
torch
torchvision
datasets
pytorch-grad-cam
lime
openai
matplotlib
pandas
numpy
scikit-image
Pillow
```

Install all dependencies:
```
pip install torch torchvision datasets pytorch-grad-cam 
lime openai matplotlib pandas numpy scikit-image Pillow
```

---

## How to Run

### On Google Colab (recommended)
1. Upload notebook to Google Colab
2. Enable GPU — Runtime → Change Runtime Type → GPU
3. Mount Google Drive
4. Update BASE_PATH to your Google Drive folder
5. Add your OpenAI API key
6. Run all cells

### Locally
1. Clone the repository
2. Install dependencies
3. Add your OpenAI API key
4. Run the notebook

---

## Important Note

You need an OpenAI API key to run the LLM experiments.
Get one at: https://platform.openai.com/api-keys

Never share your API key publicly.

---

## Author

Mst Ayesha Sultana
Master's Student — Robotics and Autonomous Systems
University of Turku, Finland
Supervised by Professor Fahimeh Farahnakian
