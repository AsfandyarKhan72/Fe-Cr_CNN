# Fe–Cr_CNN

*Simulation-informed Deep Learning for Estimating Material Parameters from Microstructural Morphology*

---


## Associated Publication

**Simulation-informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**

Asfandyar Khan, Amir Abbas Kazemzadeh, Mahmood Mamivand

*Computational Materials Science* (2026)

DOI: https://doi.org/10.1016/j.commatsci.2026.114875

## Overview

This repository provides the code, sample data, and trained workflow associated with the published study:

**Simulation-informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**

The framework combines phase-field simulations and deep learning to estimate phase-field model parameters directly from Fe–Cr spinodal microstructures.

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

directly from microstructural images. The framework uses synthetic microstructures generated from Cahn–Hilliard phase-field simulations to train a convolutional neural network for inverse parameter estimation.

## Key Results

The proposed framework demonstrated strong predictive performance on synthetic and unseen data:

| Parameter | Test R² |
|------------|------------|
| κ | 0.995 |
| M | 0.992 |

Additional findings include:

- Accurate interpolation on unseen off-grid parameter combinations
- Robust performance across an extended mobility range
- Successful proof-of-concept application to an experimental Fe–Cr microstructure

---

## Repository Structure

```text
Fe-Cr_CNN/
├── data/
│   ├── data.csv
│   └── sample_images/
├── src/
├── README.md
├── requirements.txt
├── LICENSE
└── CITATION.cff
```

---


## Requirements

Core dependencies:

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
