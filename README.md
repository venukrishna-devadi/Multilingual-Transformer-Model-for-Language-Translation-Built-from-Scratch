# Multilingual Transformer Model for Language Translation

## Overview

This project implements a **Multilingual Transformer Model** for translating English sentences into two target languages: **Hindi** and **Telugu**. The model is built from scratch using PyTorch and trained on a custom multilingual dataset, demonstrating the capability of transformers for multilingual sequence-to-sequence tasks.

---

## Features

- **Custom Transformer Architecture**: Built from scratch following the "Attention Is All You Need" paper.
- **Multilingual Translation**: Supports translation from English to Hindi and Telugu.
- **Custom Tokenization**: Utilizes a multilingual tokenizer with special language-specific tokens (`<_hi_>` for Hindi, `<_te_>` for Telugu).
- **Efficient Training**: Trained with a mix of cross-attention, padding, and masked self-attention mechanisms for optimal performance.
- **Inference with Top-k Sampling**: Implements top-k sampling for diverse and probabilistic text generation.

---

## Methodology

1. **Data Preparation**:
   - Custom multilingual dataset with English-Hindi and English-Telugu sentence pairs.
   - Language-specific tokens appended to target sentences for training.

2. **Model Architecture**:
   - **Encoder**: Encodes the source English sentence into latent representations.
   - **Decoder**: Generates the target language sequence using cross-attention and self-attention mechanisms.
   - Includes positional encodings and multi-head attention for enhanced contextual understanding.

3. **Training**:
   - Trained on a dataset of ~45,000 sentences per language for 3 epochs.
   - Optimized using the Adam optimizer with a learning rate of 0.001.

4. **Evaluation**:
   - Tracks both overall and language-specific loss during training.
   - Visualizes training metrics for performance analysis.

5. **Inference**:
   - Allows users to input English sentences and select the desired target language for translation.
   - Uses top-k sampling for token generation and employs a stopping mechanism upon reaching the end-of-sequence token.

---

## Results

- **Training Metrics**:
  - Final Loss after 3 epochs:
    - **Overall Loss**: 0.1546
    - **Hindi Language Loss**: 0.0734
    - **Telugu Language Loss**: 0.0734

- **Inference**:
  - Successfully generates translations in both Hindi and Telugu.
  - Example:
    - Input: `This is a test sentence.`
    - Output (Hindi): `यह एक परीक्षण वाक्य है।`
    - Output (Telugu): `ఇది ఒక పరీక్ష వాక్యం.`

---

## How to Use

### Prerequisites
1. Install Python 3.8+ and PyTorch.
2. Install the required libraries from `requirements.txt`:
   ```bash
   pip install -r requirements.txt

## Training the Model
	1.	Prepare your dataset with English-Hindi and English-Telugu sentence pairs.
	2.	Run the training script:
      python train.py

## Inference
    Use the provided inference script to translate sentences:
    python infer.py --source "Your English sentence here" --target "hindi"

## Future Enhancements
	1.	Incorporate more languages to expand multilingual support.
	2.	Fine-tune the model on larger datasets for improved performance.
	3.	Explore beam search decoding for better translation quality.
	4.	Deploy the model as a REST API for real-time translation.

 ## Acknowledgments
	•	Inspired by the “Attention Is All You Need” paper.
	•	Special thanks to open-source libraries like PyTorch and Hugging Face for enabling the development of this project.
