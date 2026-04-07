# Simulation-Informed Deep Learning for Estimating Material Parameters from Microstructural Morphology

This repository contains the code associated with the paper:

**Simulation-Informed Deep Learning for Estimating Material Parameters from Microstructural Morphology**  
Asfandyar Khan, Amir Abbas Kazemzadeh, Mahmood Mamivand

## Overview

This work presents a simulation-informed deep learning framework for estimating phase-field model parameters directly from microstructural morphology. Synthetic Fe–Cr spinodal microstructures are generated using a Cahn–Hilliard phase-field model, and a convolutional neural network based on an EfficientNetB7 feature extractor with a multi-task regression head is trained to predict:

- the gradient-energy coefficient, **κ**
- an effective mobility parameter, **M**

from microstructural images.

## Repository contents

- `train_model.py` — main script for feature extraction, training, evaluation, and experimental inference
- `data/` — input images and CSV labels
- `results/` — saved weights, plots, metrics, and predictions
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

## Running the code

1. Place the synthetic images and `data.csv` in the expected folders.
2. Update the paths in the script if needed.
3. Run:

```bash
python train_model.py
