FROM cyversevice/rstudio-geospatial:3.6.3

RUN apt update -y && \
    apt install -y default-jre

RUN R -e "install.packages('biomod2', repos='http://cran.us.r-project.org', dependencies=TRUE)"

RUN R -e "devtools::install_github('johnbaums/rmaxent', dependencies=TRUE)"

