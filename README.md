[![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3246932.svg)](https://doi.org/10.5281/zenodo.3246932) [![license](https://img.shields.io/badge/license-GPLv2-blue.svg)](https://opensource.org/licenses/GPL-2.0)

# rstudio-verse

RStudio with `verse` dependencies, based on [Rocker RStudio Docker container](https://hub.docker.com/r/rocker/verse) for CyVerse VICE. VICE requires additional configuration files (e.g. `nginx`) to be compatible with our Condor and Kubernetes orchestration. 

[![CircleCI](https://circleci.com/gh/cyverse-vice/rstudio-verse.svg?style=svg)](https://circleci.com/gh/cyverse-vice/rstudio-verse)[![DockerHub](https://img.shields.io/badge/DockerHub-brightgreen.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/rstudio-base)


quick launch | tag | size | metrics | build | status |  
------------ | --- | ---- | ------- | ------|--------|
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse.svg)](https://microbadger.com/images/cyversevice/shiny-verse) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse.svg)](https://microbadger.com/images/cyversevice/shiny-verse) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.0) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.0) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse:3.5.1.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.1) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.1) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse:3.5.2.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.2) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.2) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse:3.5.3.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.3) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.5.3) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/shiny-verse:3.6.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.6.0) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/shiny-verse:3.5.0.svg)](https://microbadger.com/images/cyversevice/shiny-verse:3.6.0) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) | [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)

# Instructions

## Run this Docker locally or on a Virtual Machine

To run these containers, you must first pull them from DockerHub

```
docker pull cyversevice/rstudio-verse:latest
```

```
docker run -it --rm -v /$HOME:/app --workdir /app -p 8787:80 -e REDIRECT_URL=http://localhost:8787 cyversevice/rstudio-verse:latest
```

The default username is `rstudio` and password is `rstudio1`. To reset the password, add the flag `-e PASSWORD=<yourpassword>` in the `docker run` statement.

## Build your own Docker container and deploy on CyVerse VICE

This container is intended to run on the CyVerse data science workbench, called [VICE](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). 

Unless you plan on making changes to this container, you should just use the existing launch button above. 

###### Developer notes

To build your own container with a Dockerfile and additional dependencies, pull the pre-built image from DockerHub:

```
FROM cyversevice/rstudio-verse:latest
```

Follow the instructions in the [VICE manual for integrating your own tools and apps](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/developer_guide/building.html).
