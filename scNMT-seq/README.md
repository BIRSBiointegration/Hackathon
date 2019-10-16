# Background 
This study focuses on emerging assays that combine transcriptome and epigenome profiles from the same single cell, as well as the application of data integration methods to uncover the correlation structure between information from these datasets and to understand the coordination between epigenetic and transcriptomics layers in developmental and disease cell biology. Epigenomics sequencing methodologies are still at their infancy for single cells. We will analyse a set of data from the novel technology scNMT- seq to study mouse gastrulation.

![Schematic description of scNMT-seq (from Ricard Argelaguet's gitHub page.)](scnmt-seq.png){#id .class width=50% height=50%}


## Key article

Argelaguet *et al.* 2019 is available at  https://www.biorxiv.org/content/10.1101/519207v1. (A more recent version of the paper is provided). 


# Data description
The study includes 826 cells matching  across all data sets (transcriptome, DNA accessibility and DNA methylation) after quality control and filtering. 

![Top: Schematic of the developing mouse embryo, with stages and lineages considered in this study labeled. Bottom: Dimensionality reduction of DNA chromatin accessibility and DNA methylation using Bayesian Factor analysis  (MOFA see the paper’s Methods section) or RNA expression data using UMAP (from Argelaguet *et al.* 2019)](figure1.png){#id .class width=50% height=50%}


# Easy data link 
Easy data can be downloaded from here in the `output/` folder.

https://cloudstor.aarnet.edu.au/plus/s/Xzf5vCgAEUVgbfQ

# Details about the data
Detailed guidelines are available in scNMT-seq_guidelines in this folder, please have a look as we provide example of code to extract the data, and list several challenges, and give words of caution!


## ./data

input epigentic files before pre-processing:

### ./data/met/parsed

tsv files for each annotation with columns containing:

$ V1 <chr> "E4.5-5.5_new_Plate1_A02", "E4.5-5.…   ## sample annotation id
$ V2 <chr> "ESC_p300_10004", "ESC_p300_10005",…   ## feature id
$ V3 <chr> "ESC_p300", "ESC_p300", "ESC_p300",…   ## annotation
$ V4 <int> 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0,…   ## Number of calls methylated
$ V5 <int> 1, 4, 1, 2, 6, 5, 1, 2, 2, 1, 1, 3,…   ## Total calls
$ V6 <int> 0, 25, 0, 0, 17, 0, 100, 0, 0, 0, 0…   ## Proportion of calls methylated


### ./data/acc/parsed

tsv files for each annotation with columns:

$ V1 <chr> "E4.5-5.5_new_Plate1_A02", "E4.5-5.…   ## sample annotation id
$ V2 <chr> "ESC_p300_10004", "ESC_p300_10005",…   ## feature id
$ V3 <chr> "ESC_p300", "ESC_p300", "ESC_p300",…   ## annotation
$ V4 <int> 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0,…   ## Number of detected accessible loci
$ V5 <int> 1, 4, 1, 2, 6, 5, 1, 2, 2, 1, 1, 3,…   ## Total calls
$ V6 <int> 0, 25, 0, 0, 17, 0, 100, 0, 0, 0, 0…   ## Proportion of loci accessible



## ./output


output epigentic files after preprocessing containing:

### ./met_dt_list

a list of `data.table` class objects containing methylation data - filtered by a minimum of 3 calls per site and cell-detection of >= 400

each dataset contains a data.table with 6 columns. Below is a snapshot:

$ id_met   <chr> : sample id in the dataset matching that of metadata  
$ id       <chr> : feature id  
$ anno     <chr> : annotation (identical for a given annotation)  
$ Nmet     <int> : Number of calls supporting CpG methylation  
$ N        <int> : Total number of calls in the region  
$ rate     <dbl> : Rate of methylation calculated using a binomial model with beta(1, 1) prior  
$ cell_cov <int> : Number of cells having at least 3 calls in the region for the feature id  
$ wij      <dbl> : Weight of observation at feature id for cell j (id_met) calculated using SE(rate)  
$ rbar     <dbl> : weighted mean of methylation rate across all cells for feature id  
$ n_i      <dbl> : weighted sum of observations across all cells for feature id  
$ vhat     <dbl> : weighted variance of methylation rate at feature id for all cells  
$ lci      <dbl> : lower bound of vhat 95% confidence interval  


### ./acc_dt_list

a list of `data.table` class objects containing chromatin accessibility data - filtered by a minimum of 3 calls per site and cell-detection of >= 500


each dataset contains a data.table with 6 columns. Below is a snapshot:

$ id_acc   <chr> : sample id in the dataset matching that of metadata  
$ id       <chr> : feature id  
$ anno     <chr> : annotation (identical for a given annotation)  
$ Nacc     <int> : Number of calls supporting chromatin accessibility  
$ N        <int> : Total number of calls in the region  
$ rate     <dbl> : Rate of accessibility calculated using a binomial model with beta(1, 1) prior  
$ cell_cov <int> : Number of cells having at least 3 calls in the region for the feature id  
$ wij      <dbl> : Weight of observation at feature id for cell j (id_acc) calculated using SE(rate)  
$ rbar     <dbl> : weighted mean of accessibility rate across all cells for feature id  
$ n_i      <dbl> : weighted sum of observations across all cells for feature id  
$ vhat     <dbl> : weighted variance of accessibility rate at feature id for all cells  
$ lci      <dbl> : lower bound of vhat 95% confidence interval  



### ./sample-metadata_matching-cells.txt

sample metadata for matching cells across omics


## ./notebook

In ./notebook/preprocessing.Rmd, a preprocessing file which reproduces `./output` files from `./data` files

## `./src`

Utility functions used for preprocessing



