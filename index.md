## Supplementary Data and script for our OPC to Schwann cell transdifferentiation manuscript 

Civia Z Chen, Yizhou Yu, ..., Björn Neumann, Robin Franklin <br>

University of Cambridge / Altos labs


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