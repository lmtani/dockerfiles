FROM ubuntu:18.04

# Adicionar LOCALIZER
ENV URL http://effectorp.csiro.au/EffectorP_2.0.tar.gz

RUN apt update && \
    apt install -y wget git build-essential libz-dev gzip ca-certificates curl \
                   libbz2-dev liblzma-dev libncurses5-dev libncursesw5-dev zlib1g-dev \
                   python autoconf libcurl4-gnutls-dev unzip default-jdk python-pip && \
    rm -rf /var/lib/apt/lists/* && \
    pip install numpy scipy

WORKDIR /

RUN curl -o effectorp.tar.gz $URL && \
    tar -xf effectorp.tar.gz && \
    cd /EffectorP_2.0/Scripts && \
    tar -xf emboss-latest.tar.gz && \
    cd EMBOSS-6.5.7/ && \
    ./configure --without-x && \
    make && cd .. && \
    unzip weka-3-8-1.zip
