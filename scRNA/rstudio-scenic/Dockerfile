# Based on the rocker rstudio image
# https://github.com/rocker-org/rocker-versioned/tree/master/rstudio
FROM rocker/rstudio:latest

# Install needed packages in Debian
RUN apt-get update --yes && apt-get install --no-install-recommends --yes \
  libxml2-dev

# Install R dependencies for Scenic
# based on https://htmlpreview.github.io/?https://github.com/aertslab/SCENIC/blob/master/vignettes/SCENIC_Intro.html
RUN \
    R -e 'source("https://bioconductor.org/biocLite.R"); biocLite(c("GENIE3", "RcisTarget", "AUCell","mixtools","NMF", "Rtsne", "R2HTML","doMC", "doRNG"), suppressAutoUpdate=TRUE, ask=FALSE, suppressUpdates=TRUE)'

# Install SCENIC
RUN \
    R -e 'devtools::install_github("aertslab/SCENIC")'

# Download reference DBs
RUN \
    R -e 'devtools::install_github("aertslab/SCENIC")'
