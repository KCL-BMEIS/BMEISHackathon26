# Project Proposal Template

## Team Members

 - Himanshu Sharma (himanshusharma14024@gmail.com)
 - Hemish Jain (hemishjain09@gmail.com)
 - Heeral Mandolia (mandoliaheeral@gmail.com)
 - Sakash Srivastava (sakashsrivastava06@gmail.com)



## Project Title

Cross-Domain Coronary Artery Segmentation Using Domain Adaptation on Coronary Angiography

## Overview

Coronary artery disease (CAD) is one of the leading causes of mortality worldwide, and coronary angiography remains the clinical gold standard for assessing coronary vessel anatomy and stenosis. Recent advances in deep learning have shown promising results in automated coronary artery segmentation; however, models trained on data from a single institution often fail to generalize well to images acquired from different hospitals, imaging protocols, and equipment.

This project aims to develop a robust coronary artery segmentation framework that can generalize across datasets through domain adaptation techniques. We will train a deep learning segmentation model on the ARCADE dataset and evaluate its performance on the CADICA dataset to quantify the impact of domain shift. Various domain adaptation and normalization strategies will be investigated to improve cross-dataset performance and model robustness.

The primary objective is to demonstrate that domain adaptation can significantly improve coronary artery segmentation performance when transferring models between different clinical datasets, thereby increasing the practical applicability of AI systems in real-world healthcare settings.

## Data

### Data Sources

* **ARCADE Dataset**

  * Primary dataset used for model training and validation.
  * Contains coronary angiography images with vessel annotations.

* **CADICA Dataset**

  * External dataset used for cross-domain testing and evaluation.
  * Provides coronary angiography images collected under different imaging conditions and clinical settings.

### Data Types

* Coronary angiography images (grayscale X-ray sequences/frames).
* Vessel segmentation masks and annotations.
* Derived vessel morphology measurements for evaluation.

### Data Collection and Processing

1. **Preprocessing**

   * Image normalization and resizing.
   * Contrast enhancement using CLAHE.
   * Data augmentation to improve robustness.

2. **Baseline Segmentation**

   * Train an Attention U-Net or U-Net-based architecture on the ARCADE dataset.
   * Evaluate segmentation performance using Dice Score, IoU, Precision, and Recall.

3. **Domain Adaptation**

   * Investigate techniques such as:

     * Histogram matching.
     * Style augmentation.
     * Feature-space alignment.
     * Test-time adaptation.
   * Compare adapted models against baseline performance on CADICA.

4. **Cross-Dataset Evaluation**

   * Train on ARCADE.
   * Test on CADICA.
   * Analyze performance degradation caused by domain shift.
   * Quantify improvements achieved through adaptation techniques.

### Data Considerations

* Domain shifts may arise due to differences in:

  * Imaging devices.
  * Acquisition protocols.
  * Contrast agent administration.
  * Image resolution and quality.

* Model robustness and generalizability are key evaluation objectives.

* All datasets are anonymized and intended for research purposes.

## GitHub Repository

https://github.com/HemishJain09/BMEISHackathon26.git
