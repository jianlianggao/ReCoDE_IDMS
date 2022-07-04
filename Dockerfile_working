from rocker/rstudio
MAINTAINER ReCoDE Project ( Bethan Cracknell-Daniels and Liam Gao )

LABEL software.version="1.0"

LABEL version="1.0"

LABEL software="IDMS"

WORKDIR /home/rstudio

RUN apt update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:marutter/rrutter4.0 && \
    add-apt-repository ppa:c2d4u.team/c2d4u4.0+ && \
    apt update && apt install -y r-cran-rstan

RUN R -e "install.packages(c('highr', 'devtools', 'stringr','yaml' ))" && \
    R -e "install.packages('rstan', dependencies = TRUE)" && \
    R -e "install.packages('deSolve', dependencies = TRUE)" && \
    R -e "install.packages('V8', dependencies = TRUE)" && \
    R -e "install.packages(c('dplyr','knitr','bayesplot'))" 

ADD * ./

EXPOSE 8787

CMD ["/init"]

