---
layout: project
title: "Elastomeric Bearing Performance Prediction Using Machine Learning"
description: A peer-reviewed study combining finite element analysis with machine learning to predict how elastomeric bridge bearings deform and degrade under progressive damage; I led the machine learning modeling.
importance: 12
category: Research
stack: ["ANSYS", "Python", "scikit-learn", "ANN"]
paper: https://link.springer.com/article/10.1007/s41939-025-00824-0
summary: >-
  Elastomeric bridge bearings are usually assessed by visual inspection alone, which only catches
  damage that is already visible at the surface, so this paper builds a predictive alternative:
  train machine learning models directly on finite-element simulation data to estimate how a
  bearing deforms and stresses under progressive internal damage. I contributed the machine
  learning side of the pipeline — on FEA-generated data spanning five bearing sizes compressed
  under a 750 kN load with steel shims damaged from 5% to 90% Young's-modulus reduction, I trained
  and compared Polynomial Regression, Gradient Boosting Regression, and Cubic Spline Interpolation
  models to predict deformation and stress from damage percentage, then built an Artificial Neural
  Network that predicted both deformation and directional shear stress from bearing area, damage
  percentage, and normal shear stress, reaching correlation coefficients above 0.99 on validation
  and test data.
---

Elastomeric bridge bearings are usually assessed by visual inspection alone, which can only catch damage that has already reached the surface. This paper builds a predictive alternative: combine finite element simulation with machine learning to estimate how a bearing's deformation and stress change as internal damage accumulates, well before it would be visible from the outside.

Published in *Multiscale and Multidisciplinary Modeling, Experiments and Design* (Springer), Vol. 8, Article 243 (2025), by M. Meghashree, Neethu Urs, B. N. Amith, and Kiran K. Shetty. I contributed the machine learning modeling and evaluation.

---

#### 🏗️ Finite Element Dataset

- **FEA modeling**: Modeled elastomeric bearings across five IRC-83-compliant sizes (250×300 mm up to 500×600 mm), with and without steel shim offsets, under a 750 kN compressive load in ANSYS.
- **Damage simulation**: Simulated real-world degradation by reducing the steel shims' Young's modulus from 5% to 90%, generating deformation, stress, and strain data across progressive damage levels.

---

#### 🤖 Machine Learning Modeling

- **Regression comparison**: Trained and compared Polynomial Regression, Gradient Boosting Regression, and Cubic Spline Interpolation models to predict deformation and stress from damage percentage, evaluated by R² on an 80/20 train-test split.
- **Neural network prediction**: Built an Artificial Neural Network (3 inputs — bearing area, damage percentage, normal shear stress — predicting directional shear stress and deformation) with a 70/15/15 train/validation/test split, reaching correlation coefficients above 0.99 on validation and test data.
- **Model validation**: Used Taylor diagrams and correlation matrices to confirm the models' fidelity against the FEA-simulated ground truth across bearing sizes.

---

#### 📊 Key Findings

- Larger bearings showed up to 37.86% less total deformation and over 80% lower stress than the smallest size, indicating better load distribution.
- Steel shim offsets increased deformation by 10–15% and stress by 5–10%, trading stability for flexibility.
- The trained ML models (GBR, Cubic Spline Interpolation, and ANN) closely tracked FEA results across all damage levels, offering a fast, data-driven alternative to repeated finite element runs.

---

#### 🛠️ Tech Stack

ANSYS (Static Structural FEA), Python, scikit-learn, Polynomial Regression, Gradient Boosting Regression, Cubic Spline Interpolation, Artificial Neural Networks

---

#### 💡 Why It's Relevant

Civil infrastructure maintenance usually trades off between expensive, repeated simulation and visual inspections that miss internal damage. Showing that models trained on FEA data can predict a bearing's mechanical response under unseen damage levels, accurately enough to support real maintenance decisions, was a direct, practical demonstration of how machine learning can extend rather than replace traditional structural analysis.
