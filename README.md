# Systems-Level Transcriptomic Analysis of Age-Dependent Molecular Remodelling in Duchenne Muscular Dystrophy

## Project Description
Systems biology-driven transcriptomic analysis of Duchenne Muscular Dystrophy, integrating differential expression and pathway-level interpretation to characterize age-dependent disease progression.

## Overview
This repository documents an in silico transcriptomic analysis of Duchenne Muscular Dystrophy (DMD) aimed at understanding how molecular programs evolve with age and disease progression. Using publicly available skeletal muscle gene expression data, the study adopts a systems biology framework to move beyond individual gene changes and instead characterize coordinated, mechanism-level transitions across disease stages.

The work was originally conducted as an undergraduate research project (PH-391S) and is being reimplemented here in Python and Jupyter notebooks to improve reproducibility, transparency, and extensibility.

---

## Scientific Motivation
Duchenne Muscular Dystrophy is a severe, progressive neuromuscular disorder caused by loss-of-function mutations in the DMD gene, resulting in the absence of dystrophin. While the genetic basis of DMD is well established, disease progression is driven by a complex cascade of secondary molecular events, including chronic inflammation, fibrotic remodelling, metabolic dysfunction, and loss of muscle structural integrity.

Most transcriptomic studies in DMD are cross-sectional, comparing patients and controls at a single time point. However, DMD progression is strongly age-dependent, and understanding how transcriptomic signatures shift across disease stages is critical for identifying stage-specific mechanisms and therapeutic opportunities.

This project was designed to address this gap by modeling DMD as a dynamic, age-dependent molecular process using a modular, systems-level transcriptomic approach.

---

## Dataset
The analysis is based on the following publicly available dataset:

- **GSE38417** – Gene expression data from Duchenne Muscular Dystrophy patients versus controls  
  Platform: Affymetrix Human Genome U133 Plus 2.0 (GPL570)  
  Tissue: Human skeletal muscle  
  Source: NCBI Gene Expression Omnibus (GEO)  
  https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE38417

The dataset contains skeletal muscle biopsies from healthy controls and DMD patients spanning a pediatric age range. Given the rarity of the disease and the invasive nature of muscle biopsies, the cohort size is limited, which is typical for transcriptomic studies in rare neuromuscular disorders.

Accordingly, this work is framed as a **hypothesis-generating systems biology analysis**, emphasizing robust pathway- and mechanism-level trends rather than predictive modeling or population-level inference.

---

## Analytical Framework
The analysis follows a structured, stage-aware workflow:

### 1. Data preprocessing and organization
- Extraction of normalized expression values from GEO series matrix files
- Removal of metadata rows and reorganization into gene-by-sample matrices
- Verification of probe–gene correspondence
- Assignment of samples to disease stages based on age metadata

### 2. Stage-wise transcriptomic profiling
Samples are classified into four groups:
- Control
- Early-stage DMD
- Mid-stage DMD
- Late-stage DMD

Mean expression values are computed for each gene within each stage, and control-centered expression deltas are used to quantify disease-associated changes across the progression timeline.

### 3. Differential expression analysis
- Identification of significantly dysregulated genes between DMD and control samples
- Application of fold-change and false discovery rate (FDR) thresholds
- Visualization using volcano plots

### 4. Mechanism-centric module construction
To enable systems-level interpretation, genes are organized into four biologically coherent functional modules based on prior literature and pathway annotation:

- **Fibrosis / Extracellular Matrix Remodelling**
- **Inflammation / Immune Activation**
- **Oxidative Phosphorylation and Metabolism**
- **Muscle Structural and Contractile Components**

Module assignments are validated using Gene Ontology (GO), KEGG, Reactome, and g:Profiler annotations.

### 5. Age-dependent trajectory analysis
- Calculation of average module activity across disease stages
- Identification of progressive, plateau, and biphasic expression patterns
- Visualization of temporal trends to model molecular progression in DMD

---

## Key Findings (Summary)
- Fibrosis- and inflammation-associated gene programs show progressive activation with disease advancement.
- Oxidative phosphorylation and muscle structural modules display relative preservation in early disease followed by stabilization or decline at later stages.
- The results support a coordinated molecular trajectory in which chronic inflammation and fibrotic remodelling progressively dominate over metabolic and structural maintenance.
- Observed trends align with established histopathological and clinical features of Duchenne Muscular Dystrophy.

---

## Current Status and Ongoing Work
The core transcriptomic framework has been established and is being fully transcribed from spreadsheet-based analysis into Python for reproducibility.

Ongoing and planned extensions include:
- Refinement of mechanism-level progression models
- Cross-dataset qualitative validation where feasible
- Translation of transcriptomically identified fibrotic hub genes into structure-based analysis

---

## Extension Toward Structure-Based Therapeutic Exploration
Exploratory drug–gene reversal approaches highlighted limitations of transcriptomics-only therapeutic inference, particularly for extracellular matrix–driven pathologies. As a result, this project is being extended toward structure-based molecular docking.

High-confidence fibrosis- and signaling-associated targets identified in the transcriptomic analysis (e.g., COL1A1, SPP1, EFEMP1, VEGFA) are being prioritized for protein-level structural evaluation using experimentally resolved or AlphaFold-predicted structures. This extension aims to bridge systems-level discovery with mechanistically interpretable therapeutic hypothesis generation.

---

## Scope and Limitations
- Based on a limited-size, single-cohort transcriptomic dataset
- Bulk tissue expression data does not capture cell-type–specific effects
- Findings are intended to be exploratory and hypothesis-generating

These limitations are explicitly acknowledged and reflect standard practice in systems biology studies of rare diseases.

---

## Tools and Resources
- Python (pandas, NumPy, scikit-learn, matplotlib)
- Public transcriptomic databases (NCBI GEO)
- Functional annotation resources (GO, KEGG, Reactome, g:Profiler)
- Structural databases (RCSB PDB, AlphaFold)

---

## Disclaimer
This repository represents academic research-in-progress and is intended for educational and exploratory purposes. All analyses are conducted using publicly available data.

