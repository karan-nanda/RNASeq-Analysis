# RNASeq-Analysis

# Spatial Transcriptomics Analysis: Clustering and Gene Expression Mapping

This project focuses on the **Leiden clustering algorithm** and the visualization of cell clusters and their associated gene expression in spatial transcriptomics data. By leveraging both unsupervised clustering and spatial visualization, we aim to identify distinct cell populations based on gene expression and their spatial distribution across tissue samples.

## Overview

Spatial transcriptomics combines high-throughput gene expression profiling with spatial information. This analysis helps to uncover how cells are organized in a tissue sample and how they function collectively. Here, we apply the **Leiden algorithm** to cluster cells, visualize their spatial distribution, and identify differentially expressed genes that characterize each cluster.

### Key Analysis Steps

1. **Leiden Clustering**:
   The **Leiden algorithm** is used to identify clusters of cells based on similarity in their gene expression profiles. We experiment with different resolution parameters (0.3, 0.6, and 1.0) to identify the optimal level of granularity for the clusters.
   - **Resolution 0.6** is found to provide well-defined clusters for further analysis.
   - Each cell is assigned to a cluster based on shared gene expression patterns.

2. **Visualization of Clusters**:
   We utilize UMAP (Uniform Manifold Approximation and Projection) to project high-dimensional gene expression data into 2D space. The clusters identified by the Leiden algorithm are visualized along with metrics such as:
   - **Total gene counts**: The total number of genes detected per cell.
   - **Number of genes by counts**: The number of genes with non-zero counts per cell.

   These visualizations help understand how different clusters of cells are distributed and what distinguishes them in terms of gene expression.

3. **Spatial Mapping of Clusters**:
   In addition to clustering based on gene expression, the spatial location of cells within the tissue is crucial for understanding how they interact. We visualize clusters directly on the spatial coordinates of the tissue, providing insights into how gene expression and cell clustering relate to physical location in the tissue.
   
   - We explore specific regions of interest by zooming in on smaller areas of the tissue, focusing on clusters of interest. For instance, clusters `0`, `2`, and `5` are spatially examined in selected regions.

4. **Differential Gene Expression Analysis**:
   To understand the biological characteristics of each cluster, we perform differential gene expression analysis using the **t-test** method. This analysis identifies genes that are highly expressed in certain clusters compared to others.
   - The **top 10 genes** for each cluster are extracted, highlighting the key markers that define each group.

### Findings and Interpretation

1. **Cluster Characteristics**:
   Each cluster exhibits distinct gene expression profiles, suggesting functional differences among the cell populations. For example:
   - **Cluster 0** is characterized by genes like *Prkcd*, *Tcf7l2*, and *Rora*, indicating potential roles in neural signaling and development.
   - **Cluster 1** shows high expression of *Slc17a7*, *Nptxr*, and *Enc1*, genes associated with synaptic function and plasticity.
   - **Cluster 2** features genes like *Nap1l5* and *Sparc*, which may be involved in extracellular matrix organization and neural development.

2. **Spatial Gene Expression**:
   By overlaying gene expression on tissue images, we observe how certain genes are spatially restricted to specific regions or clusters. For instance:
   - **Mog** (a marker for oligodendrocytes) is visualized alongside clusters to show its distribution across the tissue, highlighting where these specific cells are located.

3. **Exploration of Regions**:
   Focusing on smaller regions of the tissue allows for a more detailed examination of how certain clusters or cell populations are distributed. This spatial information provides additional context, linking gene expression patterns to physical locations within the tissue.

### Conclusion

This analysis highlights the power of combining **spatial transcriptomics** with **unsupervised clustering** techniques like the Leiden algorithm to uncover cellular heterogeneity and gene expression patterns within tissue samples. The spatial visualization of clusters and the identification of top differentially expressed genes help in understanding the functional roles of specific cell populations in different regions of the tissue.

By integrating both **gene expression data** and **spatial information**, this approach offers a more comprehensive view of tissue architecture and cellular function, paving the way for deeper insights into biological processes in health and disease.
