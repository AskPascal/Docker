# Based on the rocker rstudio image
# https://github.com/rocker-org/rocker-versioned/tree/master/rstudio
FROM rocker/rstudio:latest

# Install debian packages
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

# Install basic R dependencies packages
RUN \
  R -e 'install.packages(c("devtools", "Rcpp","RcppArmadillo","knitr","rmarkdown","dplyr"), repos="https://ftp.acc.umu.se/mirror/CRAN/")'

# Install minfi
RUN \
    R -e 'source("https://bioconductor.org/biocLite.R"); biocLite(c("minfi"),suppressAutoUpdate=TRUE,ask=FALSE,suppressUpdates=TRUE)'
