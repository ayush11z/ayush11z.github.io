---
layout: page
title: "UNDERSTAND: Emotion-Regulation Data Pipeline for LLM Alignment"
description: A CERQ-grounded dataset and DPO/LoRA pipeline for training LLMs to recognize and respond to emotionally charged situations.
img:
importance: 1
category: research
---

The UNDERSTAND project investigates whether language models can be trained to recognize and respond appropriately to emotionally charged situations, using CERQ (Cognitive Emotion Regulation Questionnaire) as a psychological framework for categorizing regulated versus dysregulated responses. The core challenge was building a large, labeled dataset of real emotional situations and paired responses that could actually be used to fine-tune a model's sensitivity to human emotional cues — something that doesn't exist off-the-shelf.

This project was part of the [HXI Lab](https://hxi.ucsd.edu/) at UC San Diego, where I worked with [Professor Nadir Weibel](https://hxi.ucsd.edu/author/nadir-weibel/) and PhD mentor [Aaron Broukhim](https://aabroukh.github.io/).

#### What I Worked On

- Built a Reddit-based data collection pipeline, gathering and filtering 110,000+ emotional-situation samples for the training set.
- Used Llama Guard for initial safety filtering, and read through multiple papers on how other researchers separated safe from unsafe/controversial content to inform the filtering approach.
- Applied sentence-transformers embeddings to separate posts by controversy level, using a distribution-based approach to distinguish moderately controversial content from highly controversial content — a similar statistical mindset to the conformal prediction work I used at Myna Voice Labs for robustness evaluation.
- Read through the [CERQ (Cognitive Emotion Regulation Questionnaire)](https://www.carepatron.com/files/cognitive-emotion-regulation-questionnaire-cerq.pdf) framework to define and label regulated vs. dysregulated response categories across all 9 CERQ dimensions.
- Tested multiple open-source LLMs — Qwen, Mistral, LLaMA — locally via Ollama, and evaluated against Gemini to compare response quality across models.
- Fine-tuned transformer models using DPO and LoRA on multi-GPU Nautilus clusters, training on pods of 4x A100 GPUs — using LoRA to reduce trainable parameters and training time compared to full fine-tuning.

#### Tech Stack

Python, Reddit API, Llama Guard, sentence-transformers, Ollama, Qwen, Mistral, LLaMA, Gemini, DPO, LoRA, Nautilus (multi-GPU HPC cluster), Vertex AI / GCP

#### Why It's Relevant

Most LLM alignment work optimizes for helpfulness or harmlessness in the abstract — this project instead grounds alignment in a validated psychological framework, testing whether models can learn something closer to actual emotional intelligence rather than just surface-level politeness. It's directly relevant to my interest in making agentic systems more reliable in human-facing, emotionally sensitive contexts, like health or mental-health-adjacent applications.
