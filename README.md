# Fe–Cr_CNN

*Simulation-informed deep learning for estimating phase-field model parameters from Fe-Cr spinodal microstructural morphology.*

---

## Overview

This repository contains the code associated with the manuscript:

**Simulation-Informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**  
**Authors:** Asfandyar Khan, Amir Abbas Kazemzadeh, Mahmood Mamivand

## Associated Publication

**Simulation-informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**

**Asfandyar Khan**, **Amir Abbas Kazemzadeh**, and **Mahmood Mamivand**

*Computational Materials Science*, 2026

DOI: https://doi.org/10.1016/j.commatsci.2026.114875

## Scientific Scope

This repository implements a simulation-informed deep learning framework for inverse estimation of phase-field parameters from Fe–Cr spinodal microstructures.

The workflow combines:

- Cahn–Hilliard phase-field simulations
- Synthetic microstructure generation
- EfficientNetB7 feature extraction
- Multi-task regression
- Morphology-based inverse parameter estimation

The model predicts:

- Gradient energy coefficient (κ)
- Effective mobility (M)

directly from microstructural images.

---

## Repository Contents

- `src/` — source code for feature extraction, CNN training, evaluation, and inference
- `data/data.csv` — a CSV file containing image filenames and labels `(κ, M)`
- `data/sample_images/` — representative Fe–Cr spinodal microstructure images
- `README.md` — project description and usage notes

## Requirements

Recommended packages:
- TensorFlow
- NumPy
- pandas
- matplotlib
- scikit-learn
- Pillow

## Input data

The script expects:
- a CSV file containing image filenames and labels `(κ, M)`
- synthetic grayscale microstructure images
- an experimental HAADF-STEM-based image for inference

## Sample Input Images

Representative synthetic Fe–Cr spinodal microstructure images from `data/sample_images/`:

<p align="center">
  <img src="data/sample_images/__cap_0.5_moob_0.5.png" width="200"/>
  <img src="data/sample_images/__cap_1.5_moob_2.5.png" width="200"/>
  <img src="data/sample_images/__cap_2.5_moob_10.png" width="200"/>
  <img src="data/sample_images/__cap_9_moob_4.png" width="200"/>
</p>
<p align="center"><em>Representative Fe–Cr spinodal microstructure images at varying κ and M values</em></p>

---

## Quick Start

**1. Clone the repository**
```bash
git clone https://github.com/AsfandyarKhan72/Fe-Cr_CNN.git
cd Fe-Cr_CNN
```

**2. Create environment and install dependencies**
```bash
python -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

**3. Run the training script**
```bash
python src/train_model.py
```

---

## Acknowledgment

The authors appreciate the support of the National Science Foundation grant **DMR-2142935**. We would like to acknowledge the high-performance computing support of the Borah compute cluster(DOI: 10.18122/oit/3/boisestate) provided by Boise State University’s Research Computing Department.

---

## Contact

Asfandyar Khan  
PhD Student, Materials Science and Engineering  
Boise State University  
Email: asfandyarkhan@u.boisestate.edu

---
