---
title: 'Eurobioc2026 BiocContainer Report'
title_short: 'Project for creating docker containers for R/Bioconductor packages'
tags:
  - Bioconductor
  - bioinformatics
  - R
  - Docker
authors:
  - name: Laurent Gatto
    orcid: 0000-0002-1520-2268
    affiliation: 1
  - name: Dania Machlab
    orcid: 0000-0002-2578-6930
    affiliation: 2
  - name: João F. Carrilho
    orcid: 0009-0002-2265-8922
    affiliation: 3
  - name: Michael B. Stadler
    orcid: 0000-0002-2269-4934
    affiliation: 4
  - name: Ata Badr Barzegar
    orcid: Information Technology, Åbo Akademi University, Turku, Finland
    affiliation: 5
affiliations:
  - name: Computational Biology and Bioinformatics, de Duve Institute, UCLouvain, Belgium
    index: 1
  - name: Dept of Biochemistry and Biophysics, National Bioinformatics Infrastructure Sweden, Science for Life Laboratory, Stockholm University, Box 1031, SE-17121 Solna, Sweden
    index: 2
  - name: Center for Mathematics and Applications (NOVA Math), NOVA School of Science and Technology (NOVA FCT), Caparica, Portugal
    index: 3
  - name: Friedrich Miescher Institute for Biomedical Research, Basel, Switzerland
    index: 4
  - name: Information Technology, Åbo Akademi University, Turku, Finland
    index: 5 
date: 2 June 2026
cito-bibliography: paper.bib
event: Eurobioc 2026
biohackathon_name: "Eurobioc 2026"
biohackathon_url: "https://bioconductor.org/developers/bioccommits/"
biohackathon_location: "Turku, Finland 2026"
group: ContainerGroup
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/machlabd/SimpleBiocContainer_Biohackrxiv
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Laurent Gatto \emph{et al.}
---


# Introduction

Containers enhance reproducibility and additionally offer a convenient way to 
share the setup used and needed to run a script. Offering a way to create
containers which contain desired `R` packages from within `R` allows users to 
more easily create these containers and work with them. `R` packages like
`dockerfiler` offer functions to create and work with Docker files within `R`.
However, currently there is no convenient way to create Docker files and 
containers from `R` while also controlling for the bioconductor release. The
aim in this hackathon was to create a minimal set of functions that offer this
possibility, and this work eventually gave rise to the R/Bioconductor package 
`SimpleBiocContainer`.



# R/Bioconductor package `SimpleBiocContainer`

As part of the European Bioconductor Hackathon 2026, we created an 
R/Bioconductor package called `SimpleBiocContainer` which offers a more user 
friendly way to create, build and push Docker containers to 
[Dockerhub](https://hub.docker.com/) from R. A working 
version of the package can be found on GitHub: 
(https://github.com/lgatto/SimpleBiocContainer.git).

The functions in `SimpleBiocContainer` make use of the existing 
Bioconductor docker containers which already contain a few packages, and 
additionally add the user-specified Bioconductor/R packages using 
`BiocManager::install()`. The Bioconductor version is inferred from the R 
session and the corresponding docker container matching that release is then 
used. 


ToDo: describe the functions and what they do, maybe illustrate an example run.
link to GH pacge of the package. I avoided naming the `makeSimpleBiocContainer`
function for now, should this be explicitly mentioned or is it better not to 
be too detailed in case things change in the near future.


# Conclusions / Future Work

get list of R packages loaded in session to create a container for those.
add vignettes, further enhacncements.

# Acknowledgements

We thank all participants of the European Bioconductor Hackathon 2026 for
the discussions. We also thank Nicholas Cooley and the organizing committee 
of the EuroBioC2026 conference for organizing this event.


