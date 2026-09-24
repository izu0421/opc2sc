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

This repository contains Jupyter notebooks for reproducing the analysis presented in *Extrinsic cues unlock cross-germ layer differentiation potential of CNS stem cells during regeneration*. The notebooks cover single-cell/single-nucleus RNA-seq preprocessing, cell state annotation, differential abundance and expression analysis, trajectory analysis, RNA velocity, cell fate mapping, and cell-cell communication analysis, across the rat in vivo lesion, human multiple sclerosis, and in vitro OPC-to-Schwann-cell induction datasets.

**For system requirements, installation instructions, and detailed usage guide, see the [GitHub README](https://github.com/izu0421/opc2sc/blob/main/README.md).**

---

### Section 1. Preprocessing of OPCs during injury and in controls (rat, Smart-seq2)

The data was first aligned using cellranger. The count matrices were processed using Scanpy:

1. [Dataset preprocessing and removal of low-quality cells](https://www.yizhouyu.com/opc2sc/scripts/0_1_dataset_formatting_invivo_counts.html)
2. [Regressing out ["total_counts", "pct_counts_mt","pct_counts_ERCC"]](https://www.yizhouyu.com/opc2sc/scripts/1_1_dataset_formatting_regressout.html)

Cell states (also referred to as cell types) were annotated based on the regressed-out dataset.

3. [Cell state annotation](https://www.yizhouyu.com/opc2sc/scripts/1_2_invivo_celltype_annodation_regressoutdataset.html)
4. [Plot gene markers](https://www.yizhouyu.com/opc2sc/scripts/1_3_gene_marker_plotting.html)

### Section 2. Analysis of OPCs during injury and in controls (rat, Smart-seq2)

1. [Differential abundance analysis (Milo)](https://www.yizhouyu.com/opc2sc/scripts/1_4_invivo_milo_analysis.html)
2. [Cell trajectory analysis via PAGA](https://www.yizhouyu.com/opc2sc/scripts/2_1_invivo_paga_analysis_wholedata.html)
3. [Cell fate mapping via CellRank](https://www.yizhouyu.com/opc2sc/scripts/2_2_invivo_paga_cellrank_wholedata.html)

*Plotting functions*

4. [Enrichment plot](https://www.yizhouyu.com/opc2sc/scripts/4_1_invivo_circle_plot_enrichment.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/rat_invivo/Fig1f_ED1_pathway_enrichment_STRING.tsv))
5. [TF plot](https://www.yizhouyu.com/opc2sc/scripts/4_2_invivo_circle_plot_TFs.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/rat_invivo/Fig1g_ED1_TF_enrichment_ChEA3.tsv))
6. [Unbiased marker gene identification, all datasets](https://www.yizhouyu.com/opc2sc/scripts/8_2_revision_cell_state_markers.html)

### Section 3. Identification and characterisation of oSCs in human MS lesions

Reanalysis of the published human MS snRNA-seq dataset (Lerma-Martin et al., 2024, GSE279183), using a CellTypist classifier trained on the rat data above to identify a putative oSC (predicted-oSC) population.

1. [Training the CellTypist classifier on rat OPC data](https://www.yizhouyu.com/opc2sc/scripts/5_celltypist_training.html)
2. [QC and CellTypist label transfer onto human MS OPC nuclei](https://www.yizhouyu.com/opc2sc/scripts/6_0_MSpatient_QC_celltypist.html)
3. [scVI integration](https://www.yizhouyu.com/opc2sc/scripts/6_1_scVI_integration.html)
4. [Differential gene expression: predicted-oSC vs. comparator OPCs](https://www.yizhouyu.com/opc2sc/scripts/6_2_DEG_scVIclusters.html) ([DEG table](https://github.com/izu0421/opc2sc/blob/main/source_data/human_MS/Fig2g2h_predictedoSC_vs_OPC_DEG.csv))
5. [Enrichment plot](https://www.yizhouyu.com/opc2sc/scripts/6_3_MShuman_circle_plot_enrichment.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/human_MS/Fig2g_pathway_enrichment_STRING.tsv))
6. [TF plot](https://www.yizhouyu.com/opc2sc/scripts/6_4_MShuman_circle_plot_TFs.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/human_MS/Fig2h_TF_enrichment_ChEA3.tsv))
7. [OPC/SC/OL gene-score marker plots, by predicted-oSC status and by lesion pathology (Ctrl/CI/CA)](https://www.yizhouyu.com/opc2sc/scripts/6_5_marker_gene_plotting_MShuman.html)
8. [Cell-cell communication analysis (CellPhoneDB)](https://www.yizhouyu.com/opc2sc/scripts/7_humanMS_CCC.html) ([extended tables](https://github.com/izu0421/opc2sc/tree/main/source_data/human_MS))
9. [Quantification of predicted-oSC nuclei/donor fractions](https://www.yizhouyu.com/opc2sc/scripts/8_1_revision_cell_fractions.html)

### Section 4. Preprocessing and analysis of BMP4/Vitronectin-treated OPCs

1. [Combined QC/preprocessing](https://www.yizhouyu.com/opc2sc/scripts/0_2_basic_qc_invitro.html)
2. [BMP4-specific preprocessing and QC](https://www.yizhouyu.com/opc2sc/scripts/0_3_invitro_BMP4_QC.html)
3. [RNA velocity analysis](https://www.yizhouyu.com/opc2sc/scripts/3_1_1_invitro_scvelo_BMP4.html)
4. [Cell fate mapping via CellRank](https://www.yizhouyu.com/opc2sc/scripts/3_3_1_invitro_cellrank_BMP4.html)
5. [Enrichment plot](https://www.yizhouyu.com/opc2sc/scripts/4_3_invitro_BMP_circle_plot_enrichment.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/in_vitro_BMP4/ExtDataFig4d_BMP4_pathway_enrichment_STRING.tsv))
6. [TF plot](https://www.yizhouyu.com/opc2sc/scripts/4_4_invitro_BMP_circle_plot_TFs.html) ([extended table](https://github.com/izu0421/opc2sc/blob/main/source_data/in_vitro_BMP4/ExtDataFig4_BMP4_TF_enrichment_ChEA3.tsv))

### Section 5. Preprocessing and analysis of OPCs that were infected with the Sox10 overexpression and Olig2 shRNA lentiviruses

1. [Preprocessing and QC](https://www.yizhouyu.com/opc2sc/scripts/0_4_invitro_TF_QC.html)
2. [RNA velocity analysis](https://www.yizhouyu.com/opc2sc/scripts/3_1_2_invitro_scvelo_TF.html)
3. [Cell fate mapping via CellRank](https://www.yizhouyu.com/opc2sc/scripts/3_3_2_invitro_cellrank_TF.html)

### Section 6. Comparison of BMP4/Vitronectin- and SOX10/OLIG2-induced oSCs

1. [Joint trajectory/pseudotime analysis of the combined dataset](https://www.yizhouyu.com/opc2sc/scripts/3_2_1_invitro_pseudotime_with_allcombined.html)
2. [Comparison of pseudotime and marker expression between the two induction paradigms](https://www.yizhouyu.com/opc2sc/scripts/3_2_2_invitro_pseudotime_comparison.html)
3. [Correlation of cell fate driver genes between the two datasets](https://www.yizhouyu.com/opc2sc/scripts/4_5_invitro_correlation_TF_bmp.html)
