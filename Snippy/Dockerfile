################## BASE IMAGE ######################

FROM continuumio/miniconda3

################## METADATA ######################

LABEL software="Snippy"
LABEL about.summary="Resistance prediction tool for TB"
LABEL about.home="https://github.com/tseemann/snippy"
LABEL about.documentation="https://github.com/tseemann/snippy"
LABEL license="https://github.com/tseemann/snippy"
LABEL about.tags="Genomics"

################## INSTALL ######################

RUN conda config --add channels defaults
RUN conda config --add channels bioconda
RUN conda config --add channels conda-forge

RUN conda install perl-bioperl

RUN conda install java-jdk=8.0.112
RUN conda install -c conda-forge -c bioconda snippy=4.3.6
RUN conda install -c bioconda samtools bcftools

RUN mkdir /data
WORKDIR /results

