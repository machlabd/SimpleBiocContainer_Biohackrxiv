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
  - name:
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
authors_short: First Author \emph{et al.}
---


# Introduction


Containers enhance reproducibility and additionally offer a convenient way to 
share the setup used and needed to run a script. Currently, there is no 
convenient way to create Docker files and containers from R while also 
controlling for the bioconductor release. 

ToDo: mention + cite dockerfiler somehow



# R/Bioconductor package SimpleBiocContainer

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


# conclusion/future work

get list of R packages loaded in session to create a container for those.
add vignettes, further enhacncements.

# Acknowledgements

We thank all participants of the European Bioconductor Hackathon 2026 for
the discussions. We also thank Nicholas Cooley and the organizing committee 
of the EuroBioC2026 conference for organizing this event.





## Meeting information

If you want to submit a preprint to BioHackrXiv, first check if your meeting is registered. You can find a list
of meetings [here](https://index.biohackrxiv.org/meetings). If your meeting is missing, please contact your meeting
organizers. The above list also provides information on the YAML fields with information about the meeting.

The following fields need to be given:

```YAML
biohackathon_name: "BioHackathon Europe 2023"
biohackathon_url:   "https://biohackathon-europe.org/"
biohackathon_location: "Barcelona, Spain, 2023"
group: Project 26
git_url: https://github.com/yourOrganization/your_report_repo
```

The [BioHackrXiv meeting pages](https://index.biohackrxiv.org/meetings) provide content to use for the first
three fields. The `git_url:` field must have the link to the GitHub repository with your preprint (draft).

## Author information

Information about the authors is given in the [YAML](https://en.wikipedia.org/wiki/YAML) format at the top of this template.
For authors you provide their names, their affiliations. That is the minimum, but as BioHackrXiv is moving to a situation
where more metadata is shared, and used by, for example, EuropePMC, adding additional information ie encouraged.

BioHackathons is about hacking together, and the minimal number of authors for reports is two. This makes a minimal example
look like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
  - name: Last Author
    affiliation: 2
affiliations:
  - name: First Affiliation
    index: 1
  - name: ELIXIR Europe
    index: 2
```

### Author identifiers

Ideally, authors provide their [ORCID](https://orcid.org/) identifier. For affiliations, It is added with the `orcid:` field.
So, and author record would look like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
    orcid: 0000-0000-0000-0000
```

### Research Organization Registry identifiers

Matching the author identifier, the affiliations can be further specified with the
[Research Organization Registry](https://ror.org/) (ROR) identifier.
For example, this is the affiliation identifier can be added with the `ror:` field:

```yaml
affiliations:
  - name: ELIXIR Europe
    ror: 044rwnt51
    index: 2
```

### Contributor Role Taxonomy

A last feature since is minimal support for the Contributor Role Taxonomy (CRediT). You
can specify the role of authors in writing the report with the `role:` field. However,
the authors are responsible for selection the right terms from [CRediT](https://credit.niso.org/).
An example looks like this:

```yaml
authors:
  - name: First Author
    affiliation: 1
    orcid: 0000-0000-0000-0000
    role: Conceptualization, Writing – review & editing
```

### A full examples

A full example then has this structure:

```yaml
authors:
  - name: First Author
    affiliation: 1
    role: Writing – original draft
  - name: Last Author
    orcid: 0000-0000-0000-0000
    affiliation: 2
    role: Conceptualization, Writing – review & editing
affiliations:
  - name: First Affiliation
    index: 1
  - name: ELIXIR Europe
    ror: 044rwnt51
    index: 2
```

# Formatting

This document use Markdown and you can look at [this tutorial](https://www.markdowntutorial.com/).

## Subsection level 2

Please keep sections to a maximum of only two levels.

## Tables

Tables can be added in the following way, though alternatives are possible:

```markdown
Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |
```

This gives:

Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |

## Figures

A figure is added with:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png)
```

This gives:

![Caption for BioHackrXiv logo figure](./biohackrxiv.png)

Figures can be scaled by adding the width or height to the Markdown like this:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png){ width=50px }
```

# Other main section on your manuscript level 1

Lists can be added with:

1. Item 1
2. Item 2

# Citation Typing Ontology annotation

You can use [CiTO](http://purl.org/spar/cito/2018-02-12) annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate _why_ you cite that article, for instance DisGeNET-RDF [@citesAsAuthority:Queralt2016].

The syntax in Markdown is as follows: a single intention annotation looks like
`[@usesMethodIn:Krewinkel2017]`; two or more intentions are separated
with colons, like `[@extends:discusses:Nielsen2017Scholia]`. When you cite two
different articles, you use this syntax: `[@citesAsDataSource:Ammar2022ETL; @citesAsDataSource:Arend2022BioHackEU22]`.

Possible CiTO typing annotation include:

* citesAsDataSource: when you point the reader to a source of data which may explain a claim
* usesDataFrom: when you reuse somehow (and elaborate on) the data in the cited entity
* usesMethodIn
* citesAsAuthority
* citesAsEvidence
* citesAsPotentialSolution
* citesAsRecommendedReading
* citesAsRelated
* citesAsSourceDocument
* citesForInformation
* confirms
* documents
* providesDataFor
* obtainsSupportFrom
* discusses
* extends
* agreesWith
* disagreesWith
* updates
* citation: generic citation


# Results


# Discussion

...

## Acknowledgements

...

## References
