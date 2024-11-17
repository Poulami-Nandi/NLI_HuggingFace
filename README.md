# NLI_HuggingFace

This repository contains a solution for the Kaggle competition ["Contradictory, My Dear Watson"](https://www.kaggle.com/competitions/contradictory-my-dear-watson). The task involves classifying pairs of sentences into one of three categories: `entailment`, `contradiction`, or `neutral`. The solution uses Hugging Face's transformer models to fine-tune a multilingual pretrained model.

---

## Table of Contents
1. [Problem Description](#problem-description)
2. [Solution Overview](#solution-overview)
3. [Setup and Installation](#setup-and-installation)
4. [Pipeline](#pipeline)
5. [Usage](#usage)
6. [Results](#results)
7. [Future Improvements](#future-improvements)
8. [Acknowledgements](#acknowledgements)

---

## Problem Description

### Task
Natural Language Inference (NLI) involves determining the relationship between a pair of sentences:
1. **Entailment**: The hypothesis logically follows from the premise.
2. **Contradiction**: The hypothesis contradicts the premise.
3. **Neutral**: There is no clear relationship between the premise and hypothesis.

### Example
| Premise                | Hypothesis           | Label       |
|------------------------|----------------------|-------------|
| The dog is sleeping.   | The animal is calm.  | Entailment  |
| The dog is sleeping.   | The dog is running.  | Contradiction |
| The dog is sleeping.   | The dog is hungry.   | Neutral     |

The dataset contains multilingual text, making it essential to use a model capable of handling multiple languages.

---

## Solution Overview

This project uses Hugging Face's transformer library to fine-tune a pretrained model (`bert-base-multilingual-cased`) for the NLI task. The pipeline includes:
- Preprocessing: Tokenization of sentence pairs using the `AutoTokenizer`.
- Training: Fine-tuning the transformer model on the competition dataset using the `Trainer` API.
- Prediction: Generating predictions for the test dataset.
- Submission: Formatting results into a CSV file for submission to Kaggle.

---

## Setup and Installation

### Prerequisites
- Python 3.7 or higher
- Libraries: `transformers`, `datasets`, `torch`, `pandas`, `sklearn`
- A Kaggle account for downloading the dataset

### Installation
Clone the repository and install dependencies:

```bash
git clone https://github.com/Poulami-Nandi/NLI_HuggingFace.git
cd contradictory-my-dear-watson

# Install required Python packages
pip install -r requirements.txt
```

## Kaggle Authentication

```bash
mkdir ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```
