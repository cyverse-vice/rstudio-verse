FROM rocker/verse:latest
# This image uses the Rocker-Project verse RStudio image - thanks R OpenSci and Rocker!

# Build-time metadata as defined at http://label-schema.org
ARG BUILD_DATE
ARG VCS_REF
ARG VERSION
LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="CyVerse RStudio verse" \
      org.label-schema.description="Built from Rocker-Project RStudio Verse, additional depends for CyVerse K8s workbench" \
      org.label-schema.url="https://cyverse.org" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.vcs-url="e.g. https://github.com/cyverse-vice/rstudio-verse" \
      org.label-schema.vendor="CyVerse" \
      org.label-schema.version=$VERSION \
      org.label-schema.schema-version="1.0.0"

# Install a few dependencies for iCommands, text editing, and monitoring instances
RUN apt update && apt install -y apt-transport-https \
    apt-utils \
    ca-certificates \
    curl \
    gcc \
    glances \
    gnupg2 \
    htop \
    less \
    libfuse2 \
    lsb-release \  
    nano \
    nginx \
    nodejs \
    software-properties-common \
    supervisor \ 
    wget

RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	clang \
    libv8-dev \
    libudunits2-dev \
    libgdal-dev \
    libgeos-dev \
    libproj-dev \
    libxml2 \
    libxml2-dev \
    libglpk-dev \
    jags

#RUN wget -qO - https://packages.irods.org/irods-signing-key.asc | apt-key add - && \
#    echo "deb [arch=amd64] https://packages.irods.org/apt/ $(lsb_release -sc) main" >> /etc/apt/sources.list.d/renci-irods.list && \
#    apt-get update && \
#    apt install -y irods-icommands 

# Add gomplate
ADD https://github.com/hairyhenderson/gomplate/releases/download/v3.11.5/gomplate_linux-amd64 /usr/bin/gomplate
RUN chmod a+x /usr/bin/gomplate

# provide read and write access to Rstudio users for default R library location
RUN chmod -R 777 /usr/local/lib/R/site-library

# Install Go
# RUN wget -q -c https://dl.google.com/go/go1.20.5.linux-amd64.tar.gz -O - | tar -xz -C /usr/local
# ENV PATH=$PATH:/usr/local/go/bin 

# Install GitHub CLI
#RUN curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | dd of=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg && \
#    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" > /etc/apt/sources.list.d/github-cli.list && \
#    apt update && \
#    apt install gh

ENV PASSWORD "rstudio1"
#RUN bash /etc/cont-init.d/userconf

COPY run.sh /usr/local/bin/run.sh
RUN chmod +x /usr/local/bin/run.sh

COPY nginx.conf.tmpl /nginx.conf.tmpl
COPY rserver.conf /etc/rstudio/rserver.conf
COPY supervisor-nginx.conf /etc/supervisor/conf.d/nginx.conf
COPY supervisor-rstudio.conf /etc/supervisor/conf.d/rstudio.conf

ENV REDIRECT_URL "http://localhost/"

ARG LOCAL_USER=rstudio
ARG PRIV_CMDS='/bin/ch*,/bin/cat,/bin/gunzip,/bin/tar,/bin/mkdir,/bin/ps,/bin/mv,/bin/cp,/usr/bin/apt*,/usr/bin/pip*,/bin/yum,/usr/local/bin,/etc/nginx/nginx*'

RUN apt-get update && \
    apt-get install -y sudo && \
    echo "rstudio ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    rm -rf /var/lib/apt/lists/*

# Install GoCommands
RUN cd /usr/local/bin/ && \
    GOCMD_VER=$(curl -L -s https://raw.githubusercontent.com/cyverse/gocommands/main/VERSION.txt); \
    curl -L -s https://github.com/cyverse/gocommands/releases/download/${GOCMD_VER}/gocmd-${GOCMD_VER}-linux-amd64.tar.gz | tar zxvf -

RUN mkdir -p /var/log/supervisor && \
    touch /var/log/supervisor/supervisord.log && \
    chown -R 1000:1000 /etc/nginx /var/log/supervisor 

RUN setcap 'cap_net_bind_service=+ep' /usr/bin/supervisord

USER rstudio

RUN curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
    && sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
    && sudo apt update \
    && sudo apt install gh -y

RUN echo 'export PS1="[\u@cyverse] \w $ "' >> /home/rstudio/.bashrc

WORKDIR /home/rstudio/data-store

ENTRYPOINT ["/usr/local/bin/run.sh"]
