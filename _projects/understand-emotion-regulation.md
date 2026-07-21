---
layout: project
title: "UNDERSTAND: Emotion-Regulation Data Pipeline for LLM Alignment"
description: An AI system that recognizes emotional distress on social media and responds supportively.
img: images/projects/understand-project.png
importance: 1
---

The UNDERSTAND project explores building a therapeutic AI system that can recognize when someone on social media is struggling emotionally and respond in a genuinely supportive, regulated way — rather than a generic or dismissive one. Using CERQ (Cognitive Emotion Regulation Questionnaire) as a psychological framework, the project builds a large, labeled dataset of real emotional situations and paired responses to fine-tune a model's sensitivity to human emotional cues, something that doesn't exist off-the-shelf.

This project was part of the [HXI Lab](https://hxi.ucsd.edu/) at UC San Diego, where I worked with [Professor Nadir Weibel](https://hxi.ucsd.edu/author/nadir-weibel/) and PhD mentor [Aaron Broukhim](https://aabroukh.github.io/). A paper on this work is currently in preparation and will be published soon.

---

#### 🔍 What I Worked On

- **Data collection**: Built a Reddit-based data collection pipeline, gathering and filtering **110,000+** emotional-situation samples for the training set.
- **Safety filtering**: Used **Llama Guard** for initial safety filtering, and read through multiple papers on how other researchers separated safe from unsafe/controversial content to inform the filtering approach.
- **Controversy filtering**: Applied **sentence-transformers** embeddings to separate posts by controversy level, using a distribution-based approach to distinguish moderately controversial content from highly controversial content — a similar statistical mindset to the conformal prediction work I used at Myna Voice Labs for robustness evaluation.
- **Labeling framework**: Implemented the [CERQ (Cognitive Emotion Regulation Questionnaire)](https://www.carepatron.com/files/cognitive-emotion-regulation-questionnaire-cerq.pdf) framework to define and label regulated vs. dysregulated response categories across all **9 CERQ dimensions**.
- **Model evaluation**: Tested multiple open-source LLMs — **Qwen**, **Mistral**, **LLaMA** — locally via **Ollama**, and evaluated against **Gemini** to compare response quality across models.
- **Fine-tuning**: Fine-tuned transformer models using **DPO** and **LoRA** on multi-GPU **Nautilus** clusters, training on pods of **4x A100 GPUs** — using LoRA to reduce trainable parameters and training time compared to full fine-tuning.

---

#### 🛠️ Tech Stack

Python, Reddit API, Llama Guard, sentence-transformers, Ollama, Qwen, Mistral, LLaMA, Gemini, DPO, LoRA, Nautilus (multi-GPU HPC cluster), Vertex AI / GCP

---

#### 💡 Why It's Relevant

Social media is often where people first express emotional distress, but platforms aren't built to respond to that in a therapeutic way. This project grounds AI alignment in a validated psychological framework rather than generic helpfulness, working toward systems that can recognize distress and respond with real emotional intelligence. It's directly relevant to my interest in building agentic systems that are reliable in human-facing, emotionally sensitive contexts, especially in health and mental-health-adjacent applications.
