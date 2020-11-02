# targetShop

This repo contains the materials for a workshop on "**Integration of ChIP-seq 
and RNA-seq data in R**" in the format of [Bioconductor workshops](https://github.com/seandavi/BuildABiocWorkshop2020).

The materials in the `vignettes/` direcory divided into three parts:
 
 - `vignettes/workshop_syllabus.Rmd`
 - `vignettes/workshop_code.Rmd`
 - `vignettes/workshop_quiz.Rmd`
 
The contents of these vignettes are reproduced as **Articles** in a `pkgdown` 
 [website](https://mahshaaban.github.io/targetShop/)
 
To run the materials locally, use the docker image 
[mahshaaban/targetshop](https://hub.docker.com/repository/docker/mahshaaban/targetshop/general) and knit the Rmd files from within R studio.
 
 ```bash
 docker pull mahshaaban/targetshop:latest
 docker run -e PASSWORD=<a_password> -p 8787:8787 mahshaaban/targetshop:latest
 ```
 
An Rstudio session will be accessable at 
[https://localhost:8787/](https://localhost:8787/)
in the browser. The login username is always `rstudio` and the password is `<a_password>`.

Alternatively, use an [Rstudio cloud](https://rstudio.cloud/) to creat a 
`New Project from Git Repository` of this link
[https://github.com/MahShaaban/targetShop](https://github.com/MahShaaban/targetShop).
Note, to be able to knit the Rmd documents, the required packages would need to 
be installed manually.
