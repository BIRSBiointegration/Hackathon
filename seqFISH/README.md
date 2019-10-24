# Background

This study integrates sequencing and imaging-based single-cell transcriptomic profiling methods.
The authors showed that incorportation of scRNAseq data improved cell type mapping over using seqFISH data analysis alone, 
while including the seqFISH data enabled the identification of spatial structure in the scRNAseq data. For our workshop, we focus on a subset of these data that contain matched seqFISH and scRNAseq data for the adult mouse visual cortex.

![Overview of the integration of seqFISH and scRNAseq (from Figure 1 of Zhu et al 2018)](Fig1.jpg)

## Key articles 

Zhu *et al* 2018, reference paper for seqFISH is available at: (https://www.nature.com/articles/nbt.4260)

Tasic *et al* 2016, reference paper for scRNAseq is available at: (https://www.nature.com/articles/nn.4216)

# Data

## Overview

The dataset includes 1,597 single cells from adult mouse visual cortex and 125 genes mapped with seqFISH from Zhu *et al* 2018 and scRNA-seq data for ~1,600 cells from Tasic *et al* 2016 in the primary visual cortex in adult male mice. These combined data enable cell type mapping with spatial information in the adult mouse visual cortex.  

### Main challenge: 

The main goal of the multi-omics analysis for this data in the workshop is methods to enhance the molecular resolution of spatial molecular data by integrating seqFISH and scRNA-seq data. For example, types of questions or challenges that can be addressed computationally include: 

* Can scRNA-seq data be overlaid onto seqFISH for resolution enhancement?
* What is the minimal number of genes needed for data integration?
* Are there signatures of cellular co-localization or spatial coordinates in non-spatial scRNA-seq data?

## Download 

All original and processed data and scripts used to pre-process are available here: (https://www.dropbox.com/sh/avj4nrd4la5i88u/AACafWwBbE-xsLvOGDwRZDpYa?dl=0). The core processed data are described in the **Easy data** section below. 
Extra downloads options available on the spatial data gitHub page (https://bitbucket.org/qzhu/smfish-hmrf/src/master/)
The orginal scRNAseq count matrix can be downloaded from GEO: (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71585)

## Easy data 

Easy data link to find files for this project: (https://www.dropbox.com/sh/avj4nrd4la5i88u/AACafWwBbE-xsLvOGDwRZDpYa?dl=0)

## Data directories

The following files contain cross-platform noramlized expression for 69 genes matched between both datasets used for spatial domain identification and SVM prediction.

#### /tasic_training_b2.txt 

Normalized scRNAseq data Tasic et al

#### /seqfish_cortex_b2_testing.txt 

Normalized seqFISH data

#### /seqfish_cortex_b2.labels 

spatial cluster labels for seqfish

#### /tasic.labels 

cell type labels for scRNAseq

### Additional files 

#### /fcortex.coordinates.txt 

Spatial cell coordinates

#### /hmrf-usage/data/fcortex.gene.ALL.txt 

z-scored matrix incorporating the spatial gene expression of 69 genes
