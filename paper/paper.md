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
  - name: Ata Badr Barzegar
    affiliation: 3
  - name: João F. Carrilho
    orcid: 0009-0002-2265-8922
    affiliation: 4
  - name: Michael B. Stadler
    orcid: 0000-0002-2269-4934
    affiliation: 5
affiliations:
  - name: Computational Biology and Bioinformatics, de Duve Institute, UCLouvain, Belgium
    index: 1
  - name: Dept of Biochemistry and Biophysics, National Bioinformatics Infrastructure Sweden, Science for Life Laboratory, Stockholm University, Box 1031, SE-17121 Solna, Sweden
    index: 2
  - name: Information Technology, Åbo Akademi University, Turku, Finland
    index: 3
  - name: Center for Mathematics and Applications (NOVA Math), NOVA School of Science and Technology (NOVA FCT), Caparica, Portugal
    index: 4
  - name: Friedrich Miescher Institute for Biomedical Research, Basel, Switzerland
    index: 5 
date: 2 June 2026
cito-bibliography: paper.bib
event: Eurobioc 2026
biohackathon_name: "EuroBioc 2026 Hackathon, Turku, Finland, 2026"
biohackathon_url: "https://bioconductor.org/developers/bioccommits/"
biohackathon_location: "Turku, Finland"
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
dockerfiler @dockerfilerCRAN offer functions to create and work with Docker
files within `R`. However, currently there is no convenient way to create Docker
files and containers from `R` while also controlling for the bioconductor release. The
aim in this hackathon was to create a minimal set of functions that offer this
possibility, and this work eventually gave rise to the R package 
`SimpleBiocContainer`.

# R package `SimpleBiocContainer`

As part of the European Bioconductor Hackathon 2026, we created an 
R package called `SimpleBiocContainer` which offers a more user 
friendly way to create, build and push Docker containers to 
[Dockerhub](https://hub.docker.com/) from R. A working 
version of the package can be found on GitHub: 
<https://github.com/lgatto/SimpleBiocContainer.git>.

The functions in `SimpleBiocContainer` make use of the existing 
Bioconductor docker containers (see this [link](https://www.bioconductor.org/help/docker/)
for more details), which already contain system dependencies and a few
basic packages. On top of that, we add the user-specified Bioconductor/R packages
using  `BiocManager::install()`. The Bioconductor version, and thus the corresonding
docker container, is automatically determined from the R session. 

Currently, the package has two exported functions:

- [makeSimpleBiocContainer](https://lgatto.github.io/SimpleBiocContainer/reference/makeSimpleBiocContainer.html)
  creates a container directory and populates it with a Dockerfile and optional
  data and script directories.
- [buildPushDocker](https://lgatto.github.io/SimpleBiocContainer/reference/buildPushDocker.html)
  builds and pushes the container to [Dockerhub](https://hub.docker.com/) or
  optionally [Github container registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)
  directly from `R`.

Here is a simple example to illustrate its use:

```
library(SimpleBiocContainer)

container_path <- makeSimpleBiocContainer(
  package = "MsCoreUtils",
  container = "my_container",
  data = "data.rda",
  script = "script.R")

buildPushDocker(
  container = container_path,
  dockerUsername = "docker_username")
```

# Conclusions / Future Work

The current version of the package covers all features that we wanted to include,
but represents a simple first implementation that may require further refinement
in the future.

# Acknowledgements

We thank all participants of the European Bioconductor Hackathon 2026 for
the discussions. We also thank Nicholas Cooley and the organizing committee 
of the EuroBioC2026 conference for organizing this event.

# References

