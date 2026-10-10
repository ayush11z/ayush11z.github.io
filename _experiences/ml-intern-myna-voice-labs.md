---
layout: experience-detail
title: "Machine Learning Intern"
org: "Myna Voice Labs"
org_url: "https://mynalabs.ai/"
location: "New York, NY (Hybrid)"
date_range: "Aug 2025 – Apr 2026"
highlight: "89% Accuracy"
order: 4
blurb: "Developed Parkinson's disease detection models from speech, reaching 89% accuracy with strong cross-linguistic generalization."
highlights:
  - "Developed Parkinson's detection models from speech using SVMs, CNNs, and Audio Spectrogram Transformers, reaching 89% accuracy."
  - "Confirmed robustness with a 20–28x separation in confidence interval width; LoRA continual learning retained 95.6% of prior-task performance."
stack: ["SVM", "CNN", "OpenL3", "Whisper"]
---

At Myna Voice Labs — a research collaboration with Princeton PhD scholars — I worked on detecting Parkinson's disease from short speech recordings, in a setting where the model needs to generalize across speakers of different languages.

---

#### 🔍 What I Worked On

- **Model development**: Developed Parkinson's disease detection models from speech using SVMs, CNNs, and Audio Spectrogram Transformers (AST), reaching **89% accuracy** with strong cross-linguistic generalization.
- **Robustness evaluation**: Evaluated model robustness under audio perturbations and noise using Bayesian intervals across OpenL3 and Whisper feature representations, confirming a **20–28x separation** in confidence interval width between class predictions.
- **Continual learning**: Integrated LoRA-based continual learning so the model could adapt to new data without forgetting prior tasks, retaining **95.6% of prior-task performance**.

---

#### 💡 Why It's Relevant

A detector that only works on the language and recording conditions it was trained on isn't clinically useful. Most of this work went into stress-testing the model against noise and language shift rather than chasing accuracy on a single clean benchmark — robustness, not just raw accuracy, was the actual constraint.
