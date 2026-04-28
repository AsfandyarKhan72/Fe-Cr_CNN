# FeCr_CNN

*Simulation-informed deep learning for estimating phase-field model parameters from Fe-Cr spinodal microstructural morphology.*

---

## Overview

This repository contains the code associated with the manuscript:

**Simulation-Informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**  
**Authors:** Asfandyar Khan, Amir Abbas Kazemzadeh, Mahmood Mamivand

> **Note**  
> The associated manuscript is currently **under review** in Computational Materials Science.

This work presents a simulation-informed deep learning framework for estimating phase-field model parameters directly from microstructural morphology. Synthetic Fe–Cr spinodal microstructures are generated using a Cahn–Hilliard phase-field model, and a convolutional neural network based on a frozen **EfficientNetB7** feature extractor with a **multi-task regression head** is trained to predict:

- the **gradient-energy coefficient** (`κ`)
- an **effective mobility parameter** (`M`)

from microstructural images.

This repository is intended to support reproducible research and open scientific dissemination by providing code, input-file expectations, and representative workflow documentation for reuse by other researchers.

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

## Running the code

1. Place the synthetic images and `data.csv` in the expected folders.
2. Update the paths in the script if needed.
3. Run:

```bash
git clone https://github.com/AsfandyarKhan72/Fe-Cr_CNN.git
cd Fe-Cr_CNN

python -m venv venv
source venv/bin/activate

pip install --upgrade pip
pip install -r requirements.txt

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
