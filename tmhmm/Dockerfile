FROM ubuntu:18.04

RUN apt-get update \
    && apt-get install --no-install-recommends -y perl=5.26.1-6ubuntu0.3 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ADD tmhmm-2.0c.Linux.tar.gz /usr/local/bin/

WORKDIR /usr/local/bin/
RUN mv tmhmm-2.0c tmhmm \
    && ln -s tmhmm/decodeanhmm.Linux_x86_64 tmhmm/decodeanhmm \
    && ln -s  /usr/bin/perl /usr/local/bin/perl

ENV PATH=$PATH:/usr/local/bin/tmhmm/bin
