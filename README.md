## Repository for our manuscript titled *Environmental signals suppress Olig2 during OPC to Schwann cell transdifferentiation during injury in the CNS*

**Authors:** Civia Z Chen, Yizhou Yu, ..., Björn Neumann, Robin Franklin  
**Affiliation:** University of Cambridge / Altos Labs

---

## Contents

This repository contains Jupyter notebooks for the analysis presented in our manuscript, organized into four main sections:

### Section 1: In Vivo OPC Preprocessing
- **0_1_dataset_formatting_invivo_counts.ipynb** - Dataset preprocessing and removal of low-quality cells
- **1_1_dataset_formatting_regressout.ipynb** - Regressing out technical variables (total_counts, pct_counts_mt, pct_counts_ERCC)
- **1_2_invivo_celltype_annodation_regressoutdataset.ipynb** - Cell state annotation
- **1_3_gene_marker_plotting.ipynb** - Visualization of gene markers

### Section 2: In Vivo OPC Analysis
- **2_1_invivo_paga_analysis_wholedata.ipynb** - Cell trajectory analysis via PAGA
- **2_2_invivo_paga_cellrank_wholedata.ipynb** - Cell fate mapping via CellRank
- **4_1_invivo_circle_plot_enrichment.ipynb** - Enrichment visualization
- **4_2_invivo_circle_plot_TFs.ipynb** - Transcription factor visualization

### Section 3: In Vitro BMP4-Treated OPCs
- **0_3_invitro_BMP4_QC.ipynb** - Preprocessing and QC
- **3_1_1_invitro_scvelo_BMP4.ipynb** - RNA velocity analysis
- **3_3_1_invitro_cellrank_BMP4.ipynb** - Cell fate mapping
- **4_3_invitro_BMP_circle_plot_enrichment.ipynb** - Enrichment plots
- **4_4_invitro_BMP_circle_plot_TFs.ipynb** - TF plots

### Section 4: In Vitro TF Manipulation
- **0_4_invitro_TF_QC.ipynb** - Preprocessing and QC
- **3_1_2_invitro_scvelo_TF.ipynb** - RNA velocity analysis
- **3_3_2_invitro_cellrank_TF.ipynb** - Cell fate mapping

---

### Python & Dependencies
- **Python:** 3.9, 3.10, 3.11 (tested on 3.10)
- **jupyter:** ≥1.0.0
- **scanpy:** ≥1.9.0
- **anndata:** ≥0.9.0
- **pandas:** ≥1.5.0
- **numpy:** ≥1.23.0
- **matplotlib:** ≥3.6.0
- **scipy:** ≥1.9.0
- **scikit-learn:** ≥1.2.0
- **seaborn:** ≥0.12.0
- **scvelo:** ≥0.2.4
- **cellrank:** ≥1.4.0

---

## Running the Notebooks

1. Clone the repository
2. Install required dependencies (see individual notebooks for imports)
3. Open notebooks in Jupyter: `jupyter notebook`
4. Run notebooks sequentially as indicated by section numbers

Each notebook contains the complete analysis pipeline and can be run independently after loading the required input data.

---

## Citation

If you use this code or data in your research, please cite our manuscript.
