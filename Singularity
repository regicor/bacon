Bootstrap:docker  
From:ubuntu:18.04

%post
    # Installing ubuntu dependencies
    apt-get update
    apt-get install -y libcurl4-gnutls-dev libxml2-dev libssl-dev libmariadb-client-lgpl-dev ibglib2.0-dev libcairo2-dev \
    ghostscript libxt-dev r-base
    apt-get clean
    rm -rf /var/lib/apt/lists/*
    # Installing all R packages
    Rscript -e 'r = getOption("repos"); r["CRAN"] = "https://cran.rstudio.com/"; options(repos = r); install.packages("BiocManager")'
    Rscript -e 'r = getOption("repos"); r["CRAN"] = "https://cran.rstudio.com/"; options(repos = r); BiocManager::install(c("methods","stats","ggplot2","graphics","BiocParallel","ellipse","bacon"))'
    #Rscript -e 'install.packages("BiocManager", repos = "https://cran.rstudio.com/")'
%test
    R --version
