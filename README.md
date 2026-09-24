## Extrinsic cues unlock cross-germ layer differentiation potential of CNS stem cells during regeneration

**Authors:**  
Civia Z. Chen<sup>1,2,3</sup>, Yizhou Yu<sup>2,4</sup>, Natalia Murphy<sup>2,5</sup>, Juan F. Cubillos<sup>2,3</sup>, Khalil S. Rawji<sup>1,2,3</sup>, Chao Zhao<sup>1,2,3</sup>, Myfanwy Hill<sup>2,3</sup>, Peter Arthur-Farraj<sup>3,6</sup>, Robin J.M. Franklin<sup>1,2,3*</sup>, Björn Neumann<sup>1,2,3*</sup>

**Affiliations:**
<sup>1</sup> Altos Labs Cambridge Institute, Granta Park, Cambridge UK  
<sup>2</sup> Wellcome-MRC Cambridge Stem Cell Institute, University of Cambridge, UK  
<sup>3</sup> Department of Clinical Neurosciences, University of Cambridge, UK  
<sup>4</sup> Healthspan Biotics Ltd, Milner Therapeutics Institute, Cambridge, UK  
<sup>5</sup> Department of Veterinary Medicine, University of Cambridge, UK  
<sup>6</sup> Blizard Institute, Queen Mary University of London, UK

---

## Contents

This repository contains the Jupyter notebooks used for the computational analyses presented in our manuscript, organized into six sections, plus a `source_data/` folder with the processed tables that the figure legends and methods link out to.

### Section 1: In Vivo OPC Preprocessing (rat, Smart-seq2)
- **0_1_dataset_formatting_invivo_counts.ipynb** - Dataset preprocessing and removal of low-quality cells
- **1_1_dataset_formatting_regressout.ipynb** - Regressing out technical variables (total_counts, pct_counts_mt, pct_counts_ERCC)
- **1_2_invivo_celltype_annodation_regressoutdataset.ipynb** - Cell state annotation
- **1_3_gene_marker_plotting.ipynb** - Visualization of gene markers

### Section 2: In Vivo OPC Analysis (rat, Smart-seq2)
- **1_4_invivo_milo_analysis.ipynb** - Differential abundance analysis (Milo)
- **2_1_invivo_paga_analysis_wholedata.ipynb** - Cell trajectory analysis via PAGA
- **2_2_invivo_paga_cellrank_wholedata.ipynb** - Cell fate mapping via CellRank
- **4_1_invivo_circle_plot_enrichment.ipynb** - Pathway enrichment visualization (STRING)
- **4_2_invivo_circle_plot_TFs.ipynb** - Transcription factor enrichment visualization (ChEA3)
- **8_2_revision_cell_state_markers.ipynb** - Unbiased top marker gene identification per cell state (also covers the human MS, BMP4 and SOX10/OLIG2 datasets below)

### Section 3: Human Multiple Sclerosis snRNA-seq Analysis
Reanalysis of the published human MS snRNA-seq dataset (Lerma-Martin et al., 2024; GEO accession GSE279183), using a CellTypist classifier trained on the rat Smart-seq2 data above to identify a putative oSC (predicted-oSC) population.
- **5_celltypist_training.ipynb** - Training the CellTypist classifier on the rat Smart-seq2 OPC data
- **6_0_MSpatient_QC_celltypist.ipynb** - QC of the human MS OPC nuclei and CellTypist label transfer
- **6_1_scVI_integration.ipynb** - scVI integration of the human MS OPC nuclei
- **6_2_DEG_scVIclusters.ipynb** - Differential gene expression between predicted-oSC and comparator OPC nuclei
- **6_3_MShuman_circle_plot_enrichment.ipynb** - Pathway enrichment visualization (STRING)
- **6_4_MShuman_circle_plot_TFs.ipynb** - Transcription factor enrichment visualization (ChEA3)
- **6_5_marker_gene_plotting_MShuman.ipynb** - OPC/SC/OL gene-score marker plots, stratified by predicted-oSC status and by lesion pathology (Ctrl/CI/CA)
- **7_humanMS_CCC.ipynb** - Cell-cell communication analysis (CellPhoneDB)
- **8_1_revision_cell_fractions.ipynb** - Quantification of predicted-oSC nuclei/donor fractions in the rat and human MS datasets

### Section 4: In Vitro BMP4/Vitronectin-Treated OPCs
- **0_2_basic_qc_invitro.ipynb** - Combined QC/preprocessing shared by the BMP4- and SOX10/OLIG2-treated datasets
- **0_3_invitro_BMP4_QC.ipynb** - Preprocessing and QC
- **3_1_1_invitro_scvelo_BMP4.ipynb** - RNA velocity analysis
- **3_3_1_invitro_cellrank_BMP4.ipynb** - Cell fate mapping
- **4_3_invitro_BMP_circle_plot_enrichment.ipynb** - Pathway enrichment visualization (STRING)
- **4_4_invitro_BMP_circle_plot_TFs.ipynb** - Transcription factor enrichment visualization (ChEA3)

### Section 5: In Vitro SOX10 Overexpression / Olig2 Knockdown (TF Manipulation)
- **0_4_invitro_TF_QC.ipynb** - Preprocessing and QC
- **3_1_2_invitro_scvelo_TF.ipynb** - RNA velocity analysis
- **3_3_2_invitro_cellrank_TF.ipynb** - Cell fate mapping

### Section 6: Comparison of BMP4/Vitronectin- and SOX10/OLIG2-Induced oSCs
- **3_2_1_invitro_pseudotime_with_allcombined.ipynb** - Joint trajectory/pseudotime analysis of the combined dataset
- **3_2_2_invitro_pseudotime_comparison.ipynb** - Comparison of pseudotime and marker expression between the two induction paradigms
- **4_5_invitro_correlation_TF_bmp.ipynb** - Correlation of cell fate driver genes between the SOX10/OLIG2- and BMP4/Vitronectin-induced datasets

### `source_data/`
Processed tables underlying the figures and explicitly referenced ("extended table available here") in the manuscript text and figure legends:
- **rat_invivo/** - Full STRING pathway and ChEA3 transcription factor enrichment tables for the rat CellRank fate-driver genes (Fig. 1f, g; Extended Data Fig. 1)
- **in_vitro_BMP4/** - Full enrichment tables for the BMP4/Vitronectin-induced fate-driver genes (Extended Data Fig. 4)
- **human_MS/** - Predicted-oSC vs. comparator OPC differential expression, pathway/TF enrichment tables (Fig. 2g, h), and CellPhoneDB cell-cell communication output (Fig. 2i; Extended Data Fig. 2h)
- **gene_lists/** - Marker gene lists used to calculate the OPC, SC and oligodendrocyte enrichment scores (Extended Data Table 1)

Note: this folder contains the processed analysis tables generated by the notebooks above, not the full per-panel Source Data file (with wet-lab quantifications and statistics) accompanying the published manuscript.

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
- **celltypist:** ≥1.6.0
- **scvi-tools:** ≥1.0.0
- **milopy** (differential abundance analysis)
- **cellphonedb:** ≥5.0.0
- **R** ≥4.2 with **ggplot2** (circle plot visualizations, `4_*`/`6_3`/`6_4`/`4_5`)

---

## Running the Notebooks

1. Clone the repository
2. Install required dependencies (see individual notebooks for imports)
3. Open notebooks in Jupyter: `jupyter notebook`
4. Run notebooks sequentially as indicated by section numbers

Each notebook contains the complete analysis pipeline and can be run independently after loading the required input data. Raw sequencing data are available in GEO (Smart-seq2 rat lesion data: GSE311740; 10x Genomics in vitro data: GSE312112); the human MS snRNA-seq data is from Lerma-Martin et al., 2024 (GSE279183).

---

## Citation

If you use this code or data in your research, please cite our manuscript.
