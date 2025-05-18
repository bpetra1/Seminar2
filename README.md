# MRI Preprocessing Pipeline (ADNI)

This repository contains a Python-based preprocessing pipeline for structural MRI images using **FSL** tools, designed for data from the **Alzheimer’s Disease Neuroimaging Initiative (ADNI)**.

## Overview

The pipeline performs the following steps:

1. **Brain Extraction (BET)** – removes non-brain tissue
2. **Linear Registration (FLIRT)** – aligns images to MNI152 standard space
3. **Tissue Segmentation (FAST)** – segments the brain into gray matter (GM), white matter (WM), and cerebrospinal fluid (CSF)
4. **Visualization** – shows tissue overlays for one example image

## Folder Structure

/project-root
│
├── data_nifti/ # Place raw NIfTI (.nii or .nii.gz) files here
├── output_bet/ # Output of brain extraction
├── output_flirt/ # Output of registration to MNI
├── output_fast/ # Output of segmentation
├── pipeline.ipynb # Main notebook with full pipeline
└── README.md

---

## Requirements

- Python 3.8+
- [FSL installed](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation) and available in your environment (tested in WSL)
- Python packages:
  ```bash
  pip install nibabel matplotlib numpy scikit-image fslpy
  ```

## Data

You must download structural MRI scans from the ADNI database.
Make sure you download files with this preprocessing applied:
MPR; GradWarp; B1 Correction; N3
Place the downloaded .nii or .nii.gz files into the data_nifti/ directory.

## NOtes

FAST overlay visualization is performed only for the first image (for clarity)

All outputs are saved as .nii.gz in their respective folders

The pipeline does not include machine learning — it prepares data for later use
