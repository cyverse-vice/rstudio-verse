FROM harbor.cyverse.org/vice/rstudio/verse:4.3.1

# install reqs
RUN R -e "install.packages(c('pacman', 'data.table', 'lubridate', 'zoo', 'sf', 'raster', 'sp', 'nngeo', 'rgdal', 'prism', 'censReg'), dependencies=TRUE)"

COPY climatedamages /home/rstudio/

WORKDIR /home/rstudio/data-store
