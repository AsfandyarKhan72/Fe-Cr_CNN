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
- `data/sample_images/` — representative Fe–Cr spinodal microstructure images
- `README.md` — project description and usage notes

## Requirements

Recommended packages:
- Python 3.9+
- TensorFlow
- NumPy
- pandas
- matplotlib
- scikit-learn

## Input data

The script expects:
- a CSV file containing image filenames and labels `(κ, M)`
- synthetic grayscale microstructure images
- an experimental HAADF-STEM-based image for inference

## Sample Input Images

Representative synthetic Fe–Cr spinodal microstructure images are provided in `data/sample_images/`.

![Sample Input Image](data/sample_images/__cap_1.5_moob_2.5.png)

---

## Running the code

1. Place the synthetic images and `data.csv` in the expected folders.
2. Update the paths in the script if needed.
3. Run:

```bash
python train_model.py
