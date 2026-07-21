---
layout: page
title: Speech-Based Parkinson's Disease Detection
description: Using AI to detect early signs of Parkinson's disease from a person's voice.
img: assets/img/myna-parkinsons-project.jpeg
importance: 2
category: work
---

Parkinson's disease often changes the way a person speaks years before other symptoms become obvious. This project explores whether AI models can pick up on those subtle vocal changes, working toward a low-cost, non-invasive way to flag Parkinson's risk from a simple voice recording — with a particular focus on making the models reliable across languages and real-world, noisy audio conditions rather than just clean lab recordings.

This project was a research collaboration with Princeton PhD scholars at [Myna Voice Labs](https://mynapd.com/).

---

#### 🎙️ Dataset & Feature Engineering

- **MFCC extraction**: Extracted **MFCC** (Mel-Frequency Cepstral Coefficients) features to represent the short-term power spectrum of speech, analyzing how well these handcrafted acoustic features aligned with what the **Audio Spectrogram Transformer (AST)** was learning internally from raw spectrograms.
- **Embedding comparison**: Compared **OpenL3** and **Whisper** embeddings as alternative feature representations, evaluating each against **MFCC** and against each other to determine which embedding space carried the strongest signal for detecting Parkinson's-related speech patterns, since each model was trained on different upstream tasks (general audio understanding for **OpenL3**, speech recognition for **Whisper**) and could surface different aspects of the signal.
- **Robustness testing**: Trained the model against a range of audio perturbations — additive background noise, pitch shifting, time-stretching, and reverberation — to evaluate robustness under real-world recording conditions.
- **Multilingual pipeline**: Contributed to a speech accessibility pipeline for multilingual data, extending the detection work toward broader usability across different languages and speech patterns.

---

#### 🧠 Model Architecture & Validation

- **Fine-tuning**: Fine-tuned a pretrained **AST** (86M parameters, originally trained on **AudioSet**) end-to-end for binary Parkinson's vs. non-Parkinson's speech classification on a multilingual, held-out test set.
- **Activation validation**: Validated the model by hooking into its early, middle, and late transformer layers and comparing neuron activation patterns between classes — found consistent, separable differences at every depth (up to **2.5x** in the late layers), confirming it learned real speech patterns rather than dataset artifacts.

---

#### 🎲 Uncertainty Quantification

- **Monte Carlo Dropout**: Built a **Monte Carlo Dropout** CNN (~824K parameters, dropout rate p=0.3) to generate calibrated confidence intervals for predictions, using repeated stochastic forward passes to estimate prediction uncertainty via **conformal** methods.
- **Interval validation**: Validated the approach by testing across multiple confidence levels (80%–95% CIs), finding correctly classified samples produced consistently tight intervals (~0.02–0.04 width) while misclassified samples produced dramatically wider intervals (~0.5–0.75 width) — a **~20–28x** separation that confirmed the method reliably flagged uncertain/incorrect predictions.
- **Robustness signal**: Applied this same **Bayesian** interval framework to evaluate the Parkinson's detection model's robustness under audio perturbations and noise, using prediction interval width as a signal for when the model's outputs should be trusted versus flagged for review.

---

#### ⚙️ Training Infrastructure

- **Multi-GPU training**: Ran multi-GPU training on **Vertex AI**, distributing training across GPUs to handle the compute demands of fine-tuning the AST model at scale.

---

#### 🛠️ Tech Stack

Python, PyTorch, Audio Spectrogram Transformer (AST), MFCC, OpenL3, Whisper, Monte Carlo Dropout, Conformal Prediction, Bayesian Inference, Vertex AI (multi-GPU)
