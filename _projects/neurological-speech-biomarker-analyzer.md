---
layout: project
title: "Neurological Speech Biomarker Analyzer"
description: A research tool that benchmarks speech-to-text accuracy on dysarthric speakers and predicts neurological speech-disorder severity directly from acoustic features of their voice.
importance: 10
category: Health
stack: ["Deepgram", "librosa", "scikit-learn", "Gradio"]
github: https://github.com/ayush11z/Neurological-Speech-Biomarker-Analyzer
summary: >-
  Off-the-shelf speech-to-text systems quietly fail the people who could benefit from them most,
  so I built a pipeline to quantify exactly how much Deepgram's Nova-3 model degrades on
  dysarthria — a motor speech disorder from conditions like ALS, cerebral palsy, Parkinson's, and
  stroke. Using the TORGO corpus of 15 severity-labeled speakers, I benchmarked transcription
  word-error-rate across severity levels, from about 8% for control speakers up to 53% for severe
  cases, extracted 34 acoustic features per utterance with librosa, and trained a 5-fold
  cross-validated MLP that predicts severity from voice alone at 95.7% accuracy. The full pipeline
  is served through an interactive Gradio dashboard for exploring any recording.
---

Speech-to-text systems are usually benchmarked on healthy speech, so their failure modes on people with neurological speech disorders go largely unmeasured. This project quantifies that gap directly: how much does Deepgram's Nova-3 model degrade on dysarthric speech, and can acoustic features alone predict how severe a speaker's disorder is?

---

#### 🎙️ Benchmarking & Dataset

- **TORGO corpus**: Used the TORGO dataset — 9,012 utterances from 15 speakers (7 dysarthric, 7 matched healthy controls) across 4 severity levels, labeled by a speech-language pathologist.
- **Deepgram benchmarking**: Transcribed every utterance with **Deepgram Nova-3** and computed Word Error Rate (WER) against ground-truth prompts, finding WER climbs from ~8% for control speakers to ~53% for severe dysarthria.

---

#### 🔬 Feature Extraction & Modeling

- **Acoustic features**: Extracted 34 acoustic features per utterance with **librosa** — MFCCs, pitch statistics, voice quality (jitter, shimmer, HNR), temporal features, and spectral features.
- **Severity classification**: Trained a 5-fold cross-validated MLP (128→64) and a logistic regression baseline to predict dysarthria severity directly from acoustic features, reaching 95.7% ± 0.5% accuracy with the MLP versus 88.7% ± 0.7% for logistic regression.
- **Interactive dashboard**: Built a **Gradio** dashboard where any recording can be uploaded or recorded live to get a transcript, WER, severity prediction, and acoustic plots in real time.

---

#### 🛠️ Tech Stack

Python, Deepgram Nova-3, librosa, scikit-learn, Gradio, jiwer

---

#### 💡 Why It's Relevant

Speech tools are often evaluated as if every speaker sounds the same, and the people for whom that assumption breaks down the most — those with ALS, Parkinson's, cerebral palsy, or post-stroke speech changes — are exactly the ones who could benefit most from accessible voice interfaces. Measuring that failure quantitatively, rather than assuming it away, is a necessary first step toward building speech systems that actually work for them.
