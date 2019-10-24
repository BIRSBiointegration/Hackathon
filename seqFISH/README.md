# Background

This study integrates sequencing and imaging-based single-cell transcriptomic profiling methods.
The authors showed that incorportation of scRNAseq data improved cell type mapping over using seqFISH data analysis alone, 
while including the seqFISH data enabled the identification of spatial structure in the scRNAseq data.

## Key articles 

Zhu *et al* 2018, reference paper for seqFISH is available at: (https://www.nature.com/articles/nbt.4260)

Tasic *et al* 2016, Reference paper for scRNAseq is available at: (https://www.nature.com/articles/nn.4216)

# Data

## Overview

This study includes 1,597 single cells from adult mouse visual cortex and 125 genes mapped with seqFISH. 
Additionally, scRNA-seq data for ~1,600 cells from the primary visual cortex in adult male mice
is provided rom a previously published study. 

### Outcomes: 

cell type mapping with spatial information in the adult mouse visual cortex

### Main challenge: 

enhancing the molecular resolution of spatial molecular data by integrating seqFISH and scRNA-seq data

### Types of questions / challenges to address:

Can scRNA-seq data be overlaid onto seqFISH for resolution enhancement?

What’s the minimal number of genes needed for data integration?

Are there signatures of cellular co-localization or spatial coordinates in non-spatial scRNA-seq data?

## Download 

All original and processed data and scripts used to pre-process are available in here: (https://www.dropbox.com/sh/avj4nrd4la5i88u/AACafWwBbE-xsLvOGDwRZDpYa?dl=0)

Easy data link to find files for this project: (https://www.dropbox.com/sh/avj4nrd4la5i88u/AACafWwBbE-xsLvOGDwRZDpYa?dl=0)

Extra downloads options available on the spatial data gitHub page (https://bitbucket.org/qzhu/smfish-hmrf/src/master/)

### Tasic scRNA-seq data

#### /GSE71585_RefSeq_counts.csv 

Orginal count matrix downloaded from GEO: (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71585)

#### /cortex_filtered.h5ad 

count matrix after QC filtering

#### /cortex_transformed.h5ad 

count matrix normalized and log-transformed

#### /cortex_high_variance_genes.h5ad 

count matrix normalized and log-transformed, high variance genes annotated

#### /cortex_dim_reduce.h5ad 

count matrix normalized and log-transformed, after dimensional reduction

#### /cortex_dim_reduce_high_variance_subset.h5ad 

count matrix normalized and log -transformed, subset for high variance genes only

### Cortex seqFISH data

69 genes matched between both datasets were ultimately used for spatial domain identification.

#### /fcortex.coordinates.txt 

Spatial cell coordinates

#### /hmrf-usage/data/fcortex.gene.ALL.txt 

matrix incorporating all 69 spatial genes' expression)(z-scored)

SVM prediction data, Cross-platform normalized expression for 69 genes:

#### /tasic_training_b2.txt 

(scRNAseq data Tasic et al)

#### /seqfish_cortex_b2_testing.txt 

(seqFISH data above)

#### /seqfish_cortex_b2.labels 

spatial cluster labels for seqfish

#### /tasic.labels 

cell type labels for scRNAseq
