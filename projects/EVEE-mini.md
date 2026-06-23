# EVEE-Mini Project Proposal

**Team Size:** 2 people

## Team Members

- Saumilya Gupta (saumilya.gupta@kcl.ac.uk)
- Aditya Kumar (aditya.2.kumar@kcl.ac.uk)

## Project Title

EVEE-Mini: Clinical Variant Effect Prediction using Evo 2 Foundation Model Embeddings

## Overview

Interpreting whether a genetic variant causes disease is one of the core challenges in rare disease diagnosis. Traditional methods rely on sequence conservation and homology scores, which often miss functional context and lack interpretability for clinical decision-making.

EVEE-Mini addresses this by building a lightweight, end-to-end variant effect prediction pipeline on top of Evo 2 (7B), a large-scale DNA foundation model. The system extracts bidirectional embedding difference matrices (sense and antisense strands) from Evo 2's layer-27 representations, trains a compressed covariance probe for pathogenicity classification, and ranks disrupted embedding dimensions to surface the most biologically meaningful signal. LLM-generated clinical summaries are appended to each prediction to make results interpretable for downstream users.

The goal is a hackathon MVP covering 10 clinically relevant genes (~1000 ClinVar variants) running on an GPU cluster, with results presented through an interactive Streamlit dashboard.

## Data

**Sources**
- ClinVar VCF database: 765 pathogenic and benign variants filtered for 10 target genes (BRCA1, BRCA2, TP53, LDLR, CFTR, GAA, PAH, FOXN1, MYO7A, RET), with ≥1-star review confidence
- Human Reference Genome (hg38): for extracting 2048 bp genomic context windows around each variant
- Evo 2 embeddings: 1024-dimensional layer-27 vectors per variant, stored as PyTorch `.pt` files (~500 MB total)

**Processing Pipeline**
1. Filter ClinVar VCF for target genes and variant quality
2. Extract sense and antisense sequence windows from hg38
3. Run Evo 2 inference across 8 GPUs; compute alt − ref difference matrices
4. Train covariance probe with gene-holdout cross-validation (9 train, 1 held-out)
5. Precompute pathogenicity scores, disruption rankings, and LLM interpretations as JSON

**Considerations**
- No patient data; ClinVar is fully public
- float16 precision on V100 (bfloat16 not supported); deterministic inference post-training
- MVP AUROC ~0.47 on gene-holdout split; not intended as a clinical diagnostic replacement

## GitHub Repository

[https://github.com/saumilyagupta/EVEE-Mini](https://github.com/saumilyagupta/EVEE-Mini)
