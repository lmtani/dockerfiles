FROM ubuntu:18.04

# Adicionar LOCALIZER
ENV URL http://localizer.csiro.au/LOCALIZER_1.0.4.tar.gz

RUN apt update && \
    apt install -y wget git build-essential libz-dev gzip ca-certificates curl \
                   libbz2-dev liblzma-dev libncurses5-dev libncursesw5-dev zlib1g-dev \
                   python autoconf libcurl4-gnutls-dev unzip default-jdk python-pip && \
    rm -rf /var/lib/apt/lists/* && \
    pip install biopython

WORKDIR /

RUN curl -o localizer.tar.gz $URL && \
    tar -xf localizer.tar.gz && \
    cd LOCALIZER_1.0.4/Scripts && \
    tar -xf emboss-latest.tar.gz && \
    cd EMBOSS-6.5.7/ && \
    ./configure --without-x && \
    make && cd .. && \
    unzip weka-3-6-12.zip
