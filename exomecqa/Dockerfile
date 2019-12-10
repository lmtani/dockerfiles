FROM ubuntu:18.04

RUN apt-get update && apt-get install -y wget build-essential

RUN wget https://sourceforge.net/projects/exomecqa/files/ExomeCQA.tar.gz/download -O exomecqa.tar.gz \
    && tar -xf exomecqa.tar.gz \
    && cd ExomeCQA \
    && make

ENV PATH=$PATH:/ExomeCQA