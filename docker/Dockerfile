FROM biocontainers/biocontainers:latest

LABEL base.image="biocontainers:latest"
LABEL version="1"
LABEL software="Somatic SV Workflow"
LABEL software.version="0.3"
LABEL description="Somatic SV workflow"
LABEL website="https://github.com/ding-lab/SomaticSV"
LABEL documentation="https://github.com/ding-lab/SomaticSV/blob/master/README.md"
LABEL license="https://github.com/ding-lab/SomaticSV/blob/master/LICENSE"
LABEL tags="Genomics"

MAINTAINER Wen-Wei Liao <wen-wei.liao@wustl.edu>
MAINTAINER Matthew Wyczalkowski <m.wyczalkowski@wustl.edu>

USER root
RUN conda install -y manta cyvcf2 
RUN apt-get update && apt-get install -y vim

COPY . /usr/local/SomaticSV

ENV PYTHONPATH=/opt/conda/lib/python2.7/site-packages
COPY docker/vimrc /root/.vimrc
WORKDIR /usr/local/SomaticSV
RUN /bin/bash -c "source activate base"
