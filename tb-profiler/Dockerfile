################## BASE IMAGE ######################

FROM continuumio/miniconda3

################## METADATA ######################

LABEL software="TB-profiler"
LABEL about.summary="Resistance prediction tool for TB"
LABEL about.home="https://github.com/jodyphelan/TBProfiler"
LABEL about.documentation="https://github.com/jodyphelan/TBProfiler"
LABEL license="https://github.com/jodyphelan/TBProfiler"
LABEL about.tags="Genomics"

################## INSTALL ######################

RUN conda config --add channels defaults
RUN conda config --add channels bioconda
RUN conda config --add channels conda-forge

RUN conda install -c bioconda tb-profiler
RUN conda install -c bioconda samtools=1.9=h8ee4bcc_1 openssl=1.0

RUN mkdir /data
WORKDIR /results

ADD tbdb.config.json /opt/conda/share/tbprofiler/
RUN chmod -R a+rw /opt/conda/share/tbprofiler

