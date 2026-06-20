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

## Overview

This repository contains Jupyter notebooks for reproducing the analysis presented in *Environmental signals suppress Olig2 during OPC to Schwann cell transdifferentiation during injury in the CNS*. The notebooks cover single-cell RNA-seq preprocessing, cell state annotation, trajectory analysis, RNA velocity, and cell fate mapping.

**For system requirements, installation instructions, and detailed usage guide, see the [GitHub README](https://github.com/izu0421/opc2sc/blob/main/README.md).**

---

### Section 1. Preprocessing of OPCs during injury and in controls

The data was first aligned using cellranger. The count matrices were processed using Scanpy:

1. [Dataset preprocessing and removal of low-quality cells](https://www.yizhouyu.com/opc2sc/scripts/0_1_dataset_formatting_invivo_counts.html)
2. [Regressing out ["total_counts", "pct_counts_mt","pct_counts_ERCC"]](https://www.yizhouyu.com/opc2sc/scripts/1_1_dataset_formatting_regressout.html)

Cell states (also referred to as cell types) were annotated based on the regressed-out dataset.
3. [Cell state annodation](https://www.yizhouyu.com/opc2sc/scripts/1_2_invivo_celltype_annodation_regressoutdataset.html)
4. [Plot gene markers](https://www.yizhouyu.com/opc2sc/scripts/1_3_gene_marker_plotting.html)

### Section 2. Analysis of OPCs during injury and in controls

1. [Cell trajectory analysis via PAGA](https://www.yizhouyu.com/opc2sc/scripts/2_1_invivo_paga_analysis_wholedata.html)
2. [Cell fate mapping via cellrank](https://www.yizhouyu.com/opc2sc/scripts/2_2_invivo_paga_cellrank_wholedata.html)

*Plotting functions*

3. [Enrichment plot](https://www.yizhouyu.com/opc2sc/scripts/4_1_invivo_circle_plot_enrichment.html)
4. [TF plot](https://www.yizhouyu.com/opc2sc/scripts/4_2_invivo_circle_plot_TFs.html)

### Section 3. Preprocessing and analysis of BMP-treated OPCs
1. [Preprocessing and QC](https://www.yizhouyu.com/opc2sc/scripts/0_3_invitro_BMP4_QC.html)
2. [RNA velocity analysis](https://www.yizhouyu.com/opc2sc/scripts/3_1_1_invitro_scvelo_BMP4.html)
3. [Cell fate mapping via cellrank](https://www.yizhouyu.com/scripts/opc2sc/3_3_1_invitro_cellrank_BMP4.html)
4. [Enrichment plot](https://www.yizhouyu.com/opc2sc/scripts/scripts/4_3_invitro_BMP_circle_plot_enrichment.html)
5. [TF plot](https://www.yizhouyu.com/opc2sc/scripts/4_4_invitro_BMP_circle_plot_TFs.html)

### Section 4. Preprocessing and analysis of OPCs that were infected with the Sox10 overexpression and Olig2 shRNA lentiviruses
1. [Preprocessing and QC](https://www.yizhouyu.com/opc2sc/scripts/0_4_invitro_TF_QC.html)
2. [RNA velocity analysis](https://www.yizhouyu.com/opc2sc/scripts/3_1_2_invitro_scvelo_TF.html)
3. [Cell fate mapping via cellrank](https://www.yizhouyu.com/opc2sc/scripts/3_3_2_invitro_cellrank_TF.html)