# Project Proposal Template

**Team Size:** Maximum of 5 people

## Team Members
- Mathilde Ripart (mathilde.ripart@kcl.ac.uk)
- tbd
- tbd
- tbd
- tbd

## Project Title

**ClinMRI-QC** : a light python package for automated quality check of clinical MRI scans

## Overview

MRI scans collected in clinical practice often contain quality issues that can negatively impact downstream analysis, AI pipelines, and clinical research.
Manual quality control is time-consuming and subjective. 

In this project we propose to build a light python package to automatically quality check different aspects of the MRI scan quality.
E.g.:
- registration quality between MRI modalities (e.g., FLAIR/T2w and T1-weighted images)
- presence of contrast agent enhancement (e.g., post-gadolinium T1-weighted scans)
- field-of-View (FOV) cropping or incomplete brain coverage
- presence and level of imaging artefacts (e.g. motion, noise, intensity abnormalities)
- ... 

## Data

Any open-source MRI dataset that contains clinical multimodalities scans (T1w, T2w, FLAIR, ...).

**E.g. [Multiple Sclerosis Lesion Data](https://github.com/muschellij2/open_ms_data)**

The dataset contains : 
- 30 patients with MS
- cross-sectional and longitudinal scans
- modalities:
  - T1w
  - FLAIR
  - T2w
  - T1w with contrast
  - lesion mask on FLAIR


To download (~7GB): 
```bash
git clone https://github.com/muschellij2/open_ms_data.git
```

## GitHub Repository

[https://github.com/mathrip/ClinMRI-QC](https://github.com/mathrip/ClinMRI-QC)

---
