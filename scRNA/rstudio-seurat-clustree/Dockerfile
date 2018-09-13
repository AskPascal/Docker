# Based on the rocker rstudio image
# https://github.com/rocker-org/rocker-versioned/tree/master/rstudio
FROM rocker/rstudio:latest

# Install needed packages in Debian
RUN apt-get update --yes && apt-get install --no-install-recommends --yes \
  build-essential \
  cmake \
  git \
  libbamtools-dev \
  libboost-dev \
  libboost-iostreams-dev \
  libboost-log-dev \
  libboost-system-dev \
  libboost-test-dev \
  libssl-dev \
  libssh2-1-dev \
  libcurl4-openssl-dev \
  libz-dev \
  curl \
  libhdf5-cpp-100 \
  libarmadillo7 \
  libarmadillo-dev \
  libxml2-dev

# Install debian packages for Seurat
RUN apt-get update --yes && apt-get install --no-install-recommends --yes \
  default-jre-headless \
  libpng-dev

# Install Seurat
RUN \
    R -e 'install.packages("Seurat", repos="https://ftp.acc.umu.se/mirror/CRAN/")'

# Update rmarkdown and rprojroot
RUN \
    R -e 'install.packages(c("rmarkdown","rprojroot"), repos="https://ftp.acc.umu.se/mirror/CRAN/")'

# Install basic packages
RUN \
    R -e 'install.packages(c("knitr","rmarkdown","dplyr"), repos="https://ftp.acc.umu.se/mirror/CRAN/")'

# More dependencies
RUN apt-get update --yes && apt-get install --no-install-recommends --yes \
  libudunits2-dev

# Install clustree
RUN \
    R -e 'install.packages(c("clustree"), repos="https://ftp.acc.umu.se/mirror/CRAN/")'

# Install MAST
RUN \
    R -e 'source("https://bioconductor.org/biocLite.R"); biocLite(c("MAST"), suppressAutoUpdate=TRUE, ask=FALSE, suppressUpdates=TRUE)'
