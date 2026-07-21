---
layout: page
title: "Skin Lesion Detector"
description: Comparing model architectures to classify skin lesions and help catch skin cancer earlier
img: assets/img/skin-lesion-detector.jpeg
importance: 5
category: work
---

Early detection is one of the biggest levers we have against skin cancer, and a lot of that detection ultimately depends on how well a model can tell dermoscopic images apart. This project started as a simple question: could we build a solid CNN classifier for skin lesions from scratch? It grew into something much bigger — a full comparison of model architectures backed by real training infrastructure, rather than a single notebook experiment.

I contributed to this as part of a 9-person team through CSES Innovate at UC San Diego.

---

#### 📊 Getting the Data Ready

- **Preprocessing**: Every image was sorted by lesion type, resized to a consistent 256×256, and normalized using per-channel statistics computed with **OpenCV**.
- **Live augmentation**: Since some lesion classes had far fewer examples than others, augmentation happened live during training instead of pre-generating a fixed set of images — each epoch effectively saw a fresh set of variations, keeping storage flat while still giving the model more diversity to learn from.
- **Evaluation**: Kept evaluation honest with a 60/20/20 split and an untouched, unaugmented test set.

---

#### 🧪 Trying Different Architectures

Rather than committing to one model, the team tested a progression:

- **Custom CNN**: Built from scratch in **PyTorch**, following the structure of the original reference paper.
- **Transfer learning**: Used **EfficientNet B0** and **ResNet18**, trained with label smoothing and mixed precision.
- **YOLOv8s**: The strongest and most thoroughly trained option, reaching **81.75%** top-1 accuracy and **99.84%** top-5 accuracy on held-out data.

---

#### ⚙️ Making Training Actually Scale

- **Containerized training**: Ran training inside **Docker** containers built on a **CUDA 12.1** base image with PyTorch and Ultralytics installed.
- **Kubernetes orchestration**: Deployed as batch jobs on **Kubernetes** across **A100** GPU nodes, with persistent volumes handling dataset and checkpoint storage and interactive pods enabling mid-run debugging.
- **Training efficiency**: Used multi-GPU support alongside early stopping and learning rate scheduling to keep training efficient rather than wasteful.

---

#### 🛠️ Tech Stack

PyTorch, YOLOv8, Ultralytics, Docker, Kubernetes, OpenCV, EfficientNet, ResNet

---

#### 💡 Why It's Relevant

This project is where I first had to think past just training a model and toward everything around it: reliable data pipelines, fair architecture comparisons, and infrastructure that could actually scale beyond a single GPU. It shaped how I think about building ML systems meant to hold up outside a notebook.
