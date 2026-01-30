[![Project Supported by CyVerse](https://de.cyverse.org/Powered-By-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4527797.svg)](https://doi.org/10.5281/zenodo.4527797) [![license](https://img.shields.io/badge/license-GPLv2-blue.svg?style=flat-square)](https://opensource.org/licenses/GPL-2.0)

# RStudio Verse

RStudio Server with the tidyverse ecosystem and AI development tools for the [CyVerse Discovery Environment](https://learning.cyverse.org/vice/about/).

Based on the [Rocker-Project.org](https://rocker-project.org) Docker [RStudio `verse` container](https://hub.docker.com/r/rocker/verse) with additional configuration for CyVerse Kubernetes orchestration.

[![Harbor Build Status](https://github.com/cyverse-vice/rstudio-verse/actions/workflows/harbor.yml/badge.svg)](https://github.com/cyverse-vice/rstudio-verse/actions) ![GitHub commits since tagged version](https://img.shields.io/github/commits-since/cyverse-vice/rstudio-verse/latest/main?style=flat-square) [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)

## Quick Launch

| Environment | Size |
|-------------|------|
| <a href="https://de.cyverse.org/apps/de/48b6e7ae-8b64-11ec-92dc-008cfa5ae621/launch" target="_blank"><img src="https://img.shields.io/badge/Verse-latest-blue?style=plastic&logo=rstudio"></a> | [![SIZE](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/latest.svg)](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/latest) |

## Features

### AI Development Tools
- **Claude Code** - Anthropic AI coding assistant (`claude`)
- **Gemini CLI** - Google AI CLI (`gemini`)
- **OpenAI Codex** - OpenAI coding assistant (`codex`)
- **Node.js** - JavaScript runtime for AI tools

### Development Tools
- **GitHub CLI (`gh`)** - Command-line tool for GitHub operations
- **RStudio Server** - Full-featured R IDE

### R Packages (tidyverse ecosystem)
- **tidyverse** - dplyr, ggplot2, tidyr, readr, purrr, tibble, stringr, forcats
- **RMarkdown** - Document generation
- **Shiny** - Interactive web applications
- **devtools** - Package development tools

### CyVerse Integration
- **GoCommands (`gocmd`)** - CyVerse data transfer utilities
- **nginx reverse proxy** - Kubernetes compatibility

### System Utilities
- **Monitoring** - htop, glances for system monitoring
- **Build tools** - gcc, development essentials

## Run Locally

```bash
# Pull the container
docker pull harbor.cyverse.org/vice/rstudio/verse:latest

# Run the container
docker run -it --rm -p 8787:80 -e REDIRECT_URL=http://localhost:8787 harbor.cyverse.org/vice/rstudio/verse:latest
```

Access RStudio at: http://localhost:8787

**Default credentials:**
- Username: `rstudio`
- Password: `rstudio1`

To set a custom password:
```bash
docker run -it --rm -p 8787:80 -e PASSWORD=yourpassword -e REDIRECT_URL=http://localhost:8787 harbor.cyverse.org/vice/rstudio/verse:latest
```

## Build Your Own Container

```dockerfile
FROM harbor.cyverse.org/vice/rstudio/verse:latest

# Install additional R packages
RUN R -e "install.packages('your-package', repos='https://cloud.r-project.org/')"

# Install system dependencies
USER root
RUN apt-get update && apt-get install -y your-package
USER rstudio
```

## References

- [An Introduction to Rocker: Docker Containers for R](https://journal.r-project.org/archive/2017/RJ-2017-065/RJ-2017-065.pdf) - Carl Boettiger and Dirk Eddelbuettel, The R Journal (2017) 9:2, pages 527-536. https://doi.org/10.32614/RJ-2017-065

- [The RockerVerse](https://journal.r-project.org/archive/2020/RJ-2020-007/index.html) - Daniel Nüst et al., The R Journal (2020) 12:1, pages 437-461. https://doi.org/10.32614/RJ-2020-007

## Resources

- [CyVerse VICE Documentation](https://learning.cyverse.org/vice/about/)
- [Integrate Your Own Tools](https://learning.cyverse.org/de/create_apps/)
- [Rocker Project](https://rocker-project.org/)
- [GoCommands Documentation](https://learning.cyverse.org/ds/gocommands/)
