# Contributed analyses

## Contributions

### scNMTseq

|Contributor|[Title](source repo link)|[Report type](web link)|[Container](web link)|Additional info|
|----|-----------------|-----------|-----------|-----------|
|Al JalalAbadi|[PLS](https://github.com/ajabadi/BIRSBIO2020.scNMTseq.PLS)|[Vignette](https://ajabadi.github.io/BIRSBIO2020.scNMTseq.PLS/articles/index.html)|[Docker](https://hub.docker.com/repository/docker/aljabadi/birs_bio_2020-scnmtseq-pls)| |
|Wancen Mu and Michael Love|[CV-MOFA](https://github.com/ajabadi/BIRSBIO2020.Benchmarking.CVmofa)|[Vigntte](https://ajabadi.github.io/BIRSBIO2020.Benchmarking.CVmofa)|[Docker](https://hub.docker.com/repository/docker/aljabadi/birs_bio_2020-benchmarking-cv_mofa)| |
|Josh Welch|[LIGER analysis of scNMT-seq](https://github.com/jw156605/BIRSBIO2020.scNMTseq.LIGER)|[Vignette](https://jw156605.github.io/BIRSBIO2020.scNMTseq.LIGER/index.html)| |
|Arshi Arora|[MOSAIC analysis of scNMT-seq](https://github.com/arorarshi/BIRSBIO2020.scNMTseq.MOSAIC)|[Vignette](https://arorarshi.github.io/BIRSBIO2020.scNMTseq.MOSAIC/index.html)|[Docker](https://hub.docker.com/repository/docker/arorarshi/birs_bio_2020-scnmtseq-mosaic)| |

----------

### scProteomics

|Contributor|[Title](source repo link)|[Report type](web link)|[Container](web link)|Additional info|
|----|-----------------|-----------|-----------|-----------|
|Lauren Hsu|[Exploratory analyses](https://github.com/laurenhsu1/BIRSBIO2020.scProteomics.exploratory)|[Vignette](https://laurenhsu1.github.io/BIRSBIO2020.scProteomics.exploratory/)|[Docker](https://hub.docker.com/repository/docker/laurenhsu/birsbio2020_scproteomics_exploratory) | |

----------

### scSpatial

|Contributor|[Title](source repo link)|[Report type](web link)|[Container](web link)|Additional info|
|----|-----------------|-----------|-----------|-----------|
|Alexis Coullomb|[Neighbours Aggregtion](https://github.com/AlexCoul/BIRSBIO2020.seqFISH.neighbors_aggregation)|[Vignette](https://alexcoul.github.io/BIRSBIO2020.seqFISH.neighbors_aggregation/spatial%20analysis/transcriptomics/2020/07/15/BIRS_Biointegration-seqFISH_challenge-neighbors_aggregation.html)|
|Joshua Sodicoff|[Utilizing LIGER for the integration of spatial transcriptomic data](https://github.com/jsodicoff/BIRSBIO2020.seqFISH.LIGERintegration)|[Coming soon]()|[Docker](https://hub.docker.com/r/sodicoff/birsbio2020.seqfish.liger_int)|
|Dario Righelli|[SpatialExperiment Analysis](https://github.com/drighelli/BIRSBIO2020.seqFISH.SpatialAnalysis)|[Vignette](https://drighelli.github.io/BIRSBIO2020.seqFISH.SpatialAnalysis/articles/seqFISH.html)|[Docker](https://hub.docker.com/r/drighelli/birsbio2020_seqfish_spatialanalysis)|
|Amrit Singh|[seqFISH+scRNASeq integration using semi-supervised glmnet](https://github.com/singha53/BIRSBIO2020.seqFISH.SSEnet)|[Vignette](https://singha53.github.io/BIRSBIO2020.seqFISH.SSEnet)|[Docker](https://hub.docker.com/repository/docker/singha53/birsbio2020_seqfish_ssenet)|
|Hang Xu|[Cortex seq-FISH + scRNA data - gene selection](https://github.com/gooday23/BIRSBIO2020.seqFISHChallenge.geneSeletction)|[Vignette](https://gooday23.github.io/BIRSBIO2020.seqFISHChallenge.geneSeletction/seqfish/scrna/2020/07/20/BIRS_Biointegration-seqFish_challenge-geneselection.html)|



## How to deploy your own html and containerized report using GitHub Actions

:zero: Choose a name for your package. Recommended convention: `{hackathon_event}.{theme}.{method/topic}`. e.g. `BIRSBIO2020.scNMTseq.Benchmarking`, `BIRSBIO2020.scProteomics.LatentDirichlet`. Ensure that you also have a [Docker](https://hub.docker.com/) account for automatic containerization as well.

:one: Use https://github.com/seandavi/BuildABiocWorkshop2020 as template for your analysis package. You can simply click [here](https://github.com/seandavi/BuildABiocWorkshop2020/generate) to accomplish this. Make it public and include all branches (to keep `master` & `gh-pages`, you can delete the rest).

   :exclamation: For python notebooks also see https://github.com/fastai/fastpages

:two: Follow the steps outlined [here](https://github.com/seandavi/BuildABiocWorkshop2020/blob/master/vignettes/HOWTO_BUILD_WORKSHOP.Rmd) to set up your own workflow and create a package from your analyses. The notebooks should go in `./vignettes` folder and source files in `./R` (or simply include them in notebooks). Include all dependencies in `DESCRIPTION` and ensure it can be installed, Ensure `devtools::build_vignettes()` can successfully create the vignettes locally before testing using GitHub Actions.

   :bulb: If you use R and have python dependencies, [this setup](https://github.com/ajabadi/BIRSBIO2020.scNMTseq.PLS/commit/3155bbab63129e3734e155f9f245c3a386230627#diff-5822d7d51c0024ec80488aa8a41ba9caR5-R20) should help as an example.
      
   :bulb: The docker image name should only include lowercase letters, integers, `_` and `-`.
   
   :bulb: Follow [this article](https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets) to add Docker credentials to GitHub Secrets.
   
:three: Push and ensure the workflow deploys successfully using GitHub Actions (https://github.com/YOUR_GITHUB_USER/REPO/actions)

:four: Add the relevant links and details to the table above through a pull request

:five: Please update these steps through a PR if required

