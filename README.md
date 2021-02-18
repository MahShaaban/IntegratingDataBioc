![.github/workflows/basic_checks.yaml](https://github.com/MahShaaban/IntegratingDataBioc/workflows/.github/workflows/basic_checks.yaml/badge.svg)

- This workshop is scheduled for February, 27 and is hosted by
[R-Ladies Tunisia](https://rladies.org/tunisia-rladies/) 
as part of the
[R4Bioinfo](R4Bioinfo) series.
- Part of the materials was presented at 
[EuropBioc 2021](https://github.com/MahShaaban/targetShop). 
- The code is organized in a 
[BiocWorkshop](https://github.com/seandavi/BuildABiocWorkshop) format.

# Integrating gene expression and DNA-binding data using R/Bioconductor

## Description

Researchers use ChIP binding data to identify potential transcription factor 
binding sites. They use gene expression data from sequencing or microarrays to
quantify the effect of the factor over-expression or knockdown on 
its targets. The integration of the binding and expression data therefore can be
used to improve the understanding of a transcription factor function. In this
workshop, I present a complete workflow for integrating the gene expression 
(microarray/RNA-seq)
and DNA-binding data (ChIP-seq) to predict the combined function of 
two transcription factors using R/Bioconductor. The example we will be using in 
the workshop is from real datasets of two functionally and evolutionary related
transcription factors YY1 and YY2 in HeLa cells. We will try to identify the
factor-specific and the shared targets of the factors in this particular cell 
line. Then we will use a technique find out the aggregate functions of the 
factors on their individual (inducer or repressor) and common targets 
(cooperative or competitive).

## Pre-requisites

- Basic knowledge of _R_ syntax
- Familiarity with gene expression and DNA-binding data
- Readings:
[Tang et al., 2011](https://pubmed.ncbi.nlm.nih.gov/21940749/),
[Wang et al., 2013](https://pubmed.ncbi.nlm.nih.gov/24263090/), and 
[Ahmed et al., 2020](https://pubmed.ncbi.nlm.nih.gov/32894066/)

## Participation

Participants are expected to walk through the code (rmarkdown document). An 
introduction will be given at the beginning to introduce the motivation of the
analysis and the relevant Bioconductor packages.

There are a few ways to run the code

1. Use [RStudio Cloud](https://rstudio.cloud/) to run a cloud instance of 
RStudio (free). Create a New Project > New Project from Git Repository and paste
this URL in the pop up box 
[MahShaaban/IntegratingDataBioc](https://github.com/MahShaaban/IntegratingDataBioc)

2. Use RStudio locally to install the required packages and run the code after
cloning this repo

```bash
git clone https://github.com/MahShaaban/IntegratingDataBioc
cd IntegratingDataBioc
open -a Rstudio vignette/workshop_code.Rmd 
```

3. Use the docker image 
[mahshaaban/IntegratingDataBioc](https://hub.docker.com/repository/docker/mahshaaban/IntegratingDataBioc/)
and knit the `Rmd` files in `vignettes/` from within Rstudio.
 
```bash
docker pull mahshaaban/target:latest
docker run -e PASSWORD=<a_password> -p 8787:8787 mahshaaban/target:latest
```
 
An Rstudio session will be accessable at 
[https://localhost:8787/](https://localhost:8787/)
in the browser. The login username is always `rstudio` and the password is 
`<a_password>`.

## _R_ / _Bioconductor_ packages used

- target

Data management

- GenomicRanges
- GenomicFeatures
- rtracklayer
- AnnotationDbi
- readr
- dplyr
- tidyr
- purrr

Annotation packages

- TxDb.Hsapiens.UCSC.hg19.knownGene
- org.Hs.eg.db

## Time outline

| Activity                                                  | Time |
|-----------------------------------------------------------|------|
| Bioconductor packages and classes                         | 20m  |
| Introduction to the target package                        | 20m  |
| Code-walkthrough: A use case of YY1 and YY2 in HeLa cells | 20m  |

## Workshop goals and objectives

The workshop aims to teach participants how to use R/Bioconductor packages to 
read in differential expression and binding peaks data, run a 
predictive analysis and explore its output. I hope that by providing a 
complete realistic example, participants would develop an understanding of the 
issues and the importance of integrating those two types of data. Ideally,
participants would be able to adapt this code and the workflow to apply 
this kind of analysis to their own datasets.

## Learning goals

- Learn to read differential expression and binding peaks data into the 
appropriate R objects
- Learn to use Bioconductor packages to extract the genomic annotation
- Learn to prepare the expression and binding data for `target` analysis
- Understand the `target` output through the package visualization and testing 
tools

## Learning objectives

- Read data into R `data.frame`s and Bioconductor `GRanges` objects
- Extract information from Bioconductor annotation packages TxDb and org.db
- Apply the `target` analysis using `associated_peaks` and `direct_targets` 
functions
- Visualize the output using the cumulative distribution functions through
`plot_predicitons`
- Test the results using KS test through `test_predicitons`

This workshop is based on a workflow article: [a draft](https://github.com/MahShaaban/targetFlow)
